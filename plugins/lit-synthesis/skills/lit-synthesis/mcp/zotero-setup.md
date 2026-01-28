# Zotero MCP Setup Guide

This skill requires the **Zotero MCP** server to access your library, read PDFs, and retrieve annotations.

## Prerequisites

1. **Zotero 7+** installed on your machine
2. **uv** package manager installed
3. Papers imported into Zotero (from lit-search BibTeX or manually)

## Installation

### Step 1: Install the MCP Server

```bash
uv tool install "git+https://github.com/54yyyu/zotero-mcp.git"
```

### Step 2: Run Setup

```bash
zotero-mcp setup
```

This auto-configures for Claude Desktop. Follow the prompts.

### Step 3: Enable Zotero API Access

In Zotero:
1. Go to **Edit → Preferences** (Windows/Linux) or **Zotero → Settings** (Mac)
2. Navigate to **Advanced → General**
3. Enable **"Allow other applications on this computer to communicate with Zotero"**

### Step 4: Restart Claude Desktop

After setup, restart Claude Desktop to load the MCP server.

## Connection Options

### Local API (Recommended)

Uses Zotero's local API for offline access to your desktop library.

**Advantages**:
- Works offline
- Faster access
- Full PDF access

**Requirements**:
- Zotero running on your machine
- "Allow other applications" enabled

### Web API (Alternative)

Uses Zotero's web API for cloud-synced libraries.

**Advantages**:
- Access from anywhere
- Works without Zotero running

**Requirements**:
- Zotero API key (get from zotero.org/settings/keys)
- Library ID
- PDFs must be synced to cloud

## Verifying Setup

After setup, test with:

```
Use the zotero_search_items tool to search for "test"
```

If working, you should see results from your library.

## Available Tools

Once configured, you have access to:

| Tool | What It Does |
|------|--------------|
| `zotero_search_items` | Keyword search across your library |
| `zotero_semantic_search` | AI-powered conceptual similarity search |
| `zotero_advanced_search` | Multi-criteria filtering (author, date, tags, etc.) |
| `zotero_get_item_metadata` | Full metadata for a specific item + BibTeX |
| `zotero_get_annotations` | PDF highlights and comments |
| `zotero_search_notes` | Search your personal notes |

## Workflow Integration

### From lit-search

1. Export BibTeX from lit-search's `references.bib`
2. In Zotero: **File → Import** → select the BibTeX file
3. Papers appear in your library (create a collection for the project)
4. Use **"Find Available PDF"** to auto-download open access versions
5. Manually acquire remaining PDFs via institutional access

### Organizing for Analysis

Create a Zotero collection for your project:
1. Right-click **My Library** → **New Collection**
2. Name it (e.g., "housing-instability-lit-review")
3. Drag papers into the collection
4. Use tags for additional organization (e.g., "priority-read", "theoretical", "empirical")

### Annotating PDFs

As you read in Zotero's PDF viewer:
- **Highlight** key passages (yellow for findings, blue for theory, green for methods)
- **Add notes** to highlights for your interpretation
- These annotations are accessible via `zotero_get_annotations`

## Troubleshooting

### "Zotero not found" Error

- Ensure Zotero is running
- Check that "Allow other applications" is enabled
- Restart both Zotero and Claude Desktop

### "No results" for Known Papers

- Verify the paper is in your Zotero library (not just synced to cloud)
- Check your search terms (try author name or partial title)
- Use `zotero_search_items` with broader terms

### Annotations Not Appearing

- Annotations must be made in Zotero's built-in PDF viewer
- External annotations (from Preview, Acrobat) won't sync
- Ensure the PDF is attached to the Zotero item (not just linked)

### Web API Authentication Errors

- Verify your API key at zotero.org/settings/keys
- Check that the key has read access to your library
- Confirm your Library ID is correct

## Resources

- **Zotero MCP Repository**: https://github.com/54yyyu/zotero-mcp
- **Zotero Documentation**: https://www.zotero.org/support/
- **API Key Management**: https://www.zotero.org/settings/keys
