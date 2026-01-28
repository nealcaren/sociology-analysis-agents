# Phase 4: Full Text Acquisition

You are helping the user obtain full text for the corpus papers. Your goal is to maximize full text coverage for deep annotation.

## Why This Phase Matters

Abstract-only annotation is limited. Full text reveals methods details, nuanced findings, and theoretical contributions that abstracts omit. This phase identifies available sources and creates a checklist for the user.

## Prerequisites

- Load `data/screened/included_with_snowball.json` (or `included.json` if no snowballing)

## Your Tasks

### 1. Check OpenAlex Open Access Status

OpenAlex includes OA information:

```python
def check_oa_status(papers):
    """Categorize papers by open access availability."""
    oa_status = {
        "gold_oa": [],      # Published OA
        "green_oa": [],     # Repository version
        "bronze_oa": [],    # Free to read
        "closed": []        # Paywalled
    }

    for paper in papers:
        oa_info = paper.get("open_access", {})
        is_oa = oa_info.get("is_oa", False)
        oa_url = oa_info.get("oa_url")
        oa_status_type = oa_info.get("oa_status", "closed")

        paper_info = {
            "title": paper["title"],
            "doi": paper.get("doi"),
            "year": paper["publication_year"],
            "oa_url": oa_url
        }

        if oa_status_type == "gold":
            oa_status["gold_oa"].append(paper_info)
        elif oa_status_type == "green":
            oa_status["green_oa"].append(paper_info)
        elif oa_status_type == "bronze":
            oa_status["bronze_oa"].append(paper_info)
        else:
            oa_status["closed"].append(paper_info)

    return oa_status
```

### 2. Query Unpaywall for Additional OA Links

Unpaywall may have sources OpenAlex missed:

```python
def check_unpaywall(doi, email):
    """Query Unpaywall API for OA version."""
    if not doi:
        return None

    # Clean DOI
    doi = doi.replace("https://doi.org/", "")

    url = f"https://api.unpaywall.org/v2/{doi}"
    params = {"email": email}

    try:
        response = requests.get(url, params=params)
        if response.status_code == 200:
            data = response.json()
            if data.get("is_oa"):
                best_location = data.get("best_oa_location", {})
                return {
                    "url": best_location.get("url_for_pdf") or best_location.get("url"),
                    "version": best_location.get("version"),
                    "host_type": best_location.get("host_type")
                }
    except:
        pass

    return None
```

### 3. Check for Preprints

Many sociology papers have preprint versions:

```python
def find_preprints(paper):
    """Check common preprint servers."""
    title = paper.get("title", "")
    authors = paper.get("authors", [])

    # Check SocArXiv via OSF API
    # Check SSRN
    # Check author institutional repositories

    # OpenAlex may already have this in alternate_host_venues
    alt_venues = paper.get("locations", [])
    for venue in alt_venues:
        source = venue.get("source", {})
        if source.get("type") == "repository":
            return venue.get("pdf_url") or venue.get("landing_page_url")

    return None
```

### 4. Generate Full Text Status Report

```markdown
## Full Text Availability Report

**Corpus size**: 179 papers

### Open Access Available (direct download)
| Status | Count | Percentage |
|--------|-------|------------|
| Gold OA (publisher) | 34 | 19% |
| Green OA (repository) | 28 | 16% |
| Bronze OA (free read) | 12 | 7% |
| **Total OA** | **74** | **41%** |

### Paywalled Papers
| Status | Count | Percentage |
|--------|-------|------------|
| Requires subscription | 105 | 59% |

### By Journal (Paywalled)
| Journal | Papers | Access Method |
|---------|--------|---------------|
| American Sociological Review | 12 | JSTOR/Institutional |
| American Journal of Sociology | 8 | JSTOR/Institutional |
| Social Forces | 7 | Oxford/Institutional |
```

### 5. Create Download Checklist

Generate an actionable checklist for the user:

```markdown
## Download Checklist

### Direct Downloads (OA - can automate)
These papers have direct PDF links:

1. [ ] [Paper title 1] (2023)
   - URL: https://...
   - Type: Gold OA

2. [ ] [Paper title 2] (2021)
   - URL: https://...
   - Type: Green OA (preprint)

[Continue for all OA papers]

### Requires Institutional Access
You'll need to download these through your library:

**JSTOR** (15 papers):
1. [ ] [Paper title] (2019) - DOI: 10.xxxx
2. [ ] [Paper title] (2018) - DOI: 10.xxxx

**Oxford Academic** (8 papers):
1. [ ] [Paper title] (2020) - DOI: 10.xxxx

**Sage Journals** (12 papers):
1. [ ] [Paper title] (2022) - DOI: 10.xxxx

**Wiley** (5 papers):
...

### Interlibrary Loan Needed
These aren't available through typical subscriptions:

1. [ ] [Book chapter] (2017) - ISBN: xxx
2. [ ] [Conference paper] (2019)
```

### 6. Create Automated Download Script (Optional)

For OA papers, offer a download script:

```python
import os
import requests
from time import sleep

def download_oa_papers(oa_papers, output_dir="fulltext"):
    """Download available OA papers."""
    os.makedirs(output_dir, exist_ok=True)

    for paper in oa_papers:
        if not paper.get("oa_url"):
            continue

        # Create safe filename
        safe_title = "".join(c for c in paper["title"][:50] if c.isalnum() or c in " -_")
        filename = f"{paper['year']}_{safe_title}.pdf"
        filepath = os.path.join(output_dir, filename)

        try:
            response = requests.get(paper["oa_url"], timeout=30)
            if response.status_code == 200 and "pdf" in response.headers.get("content-type", "").lower():
                with open(filepath, "wb") as f:
                    f.write(response.content)
                print(f"Downloaded: {filename}")
            sleep(1)  # Rate limiting
        except Exception as e:
            print(f"Failed: {paper['title']} - {e}")
```

### 7. Track Full Text Status

Create a tracking file:

```python
fulltext_status = []
for paper in papers:
    fulltext_status.append({
        "openalex_id": paper["openalex_id"],
        "title": paper["title"],
        "doi": paper.get("doi"),
        "oa_available": bool(paper.get("open_access", {}).get("oa_url")),
        "fulltext_obtained": False,  # User updates this
        "fulltext_path": None,       # User updates this
        "notes": ""
    })

# Save for user tracking
with open("data/fulltext_status.json", "w") as f:
    json.dump(fulltext_status, f, indent=2)
```

## Output Files

- `output/fulltext_checklist.md` - Human-readable download list
- `data/fulltext_status.json` - Machine-readable tracking
- `fulltext/` - Directory for user to store PDFs

## Guiding Principles

- **Maximize coverage**: Full text enables better annotation
- **Legal sources only**: Use OA, institutional access, or ILL
- **Respect rate limits**: Don't hammer APIs or publishers
- **Track status**: Know what you have and what's missing

## When You're Done

Tell the orchestrator:
> "Phase 4 complete. X/Y papers (Z%) have OA versions available. Download checklist created at output/fulltext_checklist.md. User should obtain remaining papers before annotation phase."

**Do not proceed to Phase 5 until the user has obtained full text for key papers.**

The user may choose to proceed with partial full text coverage, annotating from abstracts where necessary. Confirm this decision before continuing.
