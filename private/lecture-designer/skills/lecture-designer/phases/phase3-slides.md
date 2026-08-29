# Phase 3: Slide Development (Google Slides via MCP)

You are executing Phase 3 of the lecture design process. Your goal is to create visually effective slides directly in Google Slides using the Google Docs MCP.

## Why This Phase Matters

In a large lecture hall, the slides are the visual anchor. But slides are not the lecture—they're visual aids. The goal is to reduce extraneous cognitive load so students can focus on understanding, not decoding cluttered visuals.

**Key Insight**: Audiences cannot read and listen simultaneously. When you show text-heavy slides, they read instead of listening to you.

> "If a slide contains more than 75 words, it has become a document, not a presentation." — Nancy Duarte

> "No more than 6 words on a slide. EVER." — Seth Godin

## Prerequisites

Before starting this phase, ensure:
1. **Google Docs MCP is installed and configured**: <https://github.com/nealcaren/google-docs-mcp>
2. **OAuth authentication is complete**: You should be able to create and edit Google documents
3. All Phase 0-2 outputs are available

## Inputs

Before starting, read:
1. All Phase 0-2 outputs (learning outcomes, narrative arc, chunk map, activities)
2. **`pedagogy/slide-design-guide.md`** - Comprehensive visual design principles
3. **`mcp/google-docs-mcp-setup.md`** - MCP tools reference

## Your Tasks

### 1. Create the Presentation

Use the Google Docs MCP to create a new presentation:

```
Tool: createPresentation
Parameters:
  title: "[Course Name] - [Lecture Topic]"
```

This returns a presentation ID that you'll use for all subsequent operations.

### 2. Plan the Slide Structure

For a 75-minute lecture, plan approximately 30-40 slides:

```
Slide Structure:
├── Title slide (1)
├── Hook/Opening (2-3 slides)
│   ├── Mystery/problem statement
│   └── Baseline poll
├── Chunk 1 (5-7 slides)
│   ├── Key concept slides
│   └── ConcepTest poll
├── Chunk 2 (5-7 slides)
│   ├── Key concept slides (hardest material)
│   └── State change activity
├── Chunk 3 (4-6 slides)
│   ├── Application slides
│   └── Synthesis activity
├── Summary (2-3 slides)
│   ├── Return to hook
│   └── Key takeaways
└── Closing (2 slides)
    ├── Muddiest point
    └── Next steps
```

### 3. Add Slides with Appropriate Layouts

Use `addSlide` with these layout types:

| Layout | Use For |
|--------|---------|
| `TITLE` | Title slide |
| `SECTION_HEADER` | Chunk/section dividers |
| `TITLE_AND_BODY` | Content slides with bullets |
| `TITLE_AND_TWO_COLUMNS` | Comparison slides |
| `BLANK` | Full-bleed images, custom layouts |
| `BIG_NUMBER` | Statistics, key figures |

**Example: Adding a content slide**
```
Tool: addSlide
Parameters:
  presentationId: "[presentation-id]"
  layoutType: "TITLE_AND_BODY"
```

### 4. Populate Slide Content

Use `insertTextToSlide` to add text to placeholders:

**For title slides:**
```
Tool: insertTextToSlide
Parameters:
  presentationId: "[presentation-id]"
  slideIndex: 0
  shapeId: "[title-placeholder-id]"
  text: "Lecture Title Here"
```

**Content guidelines:**
- **Titles**: 3-6 words, action-oriented
- **Body**: Maximum 3 bullet points, 6 words each
- **Never**: Full sentences, paragraphs, or walls of text

### 5. Apply Mayer's Multimedia Principles

For every slide, apply these evidence-based principles:

| Principle | What It Means | How to Apply |
|-----------|---------------|--------------|
| **Coherence** | Remove extraneous material | No decorative images, minimal text |
| **Signaling** | Highlight key information | Bold key terms, use color strategically |
| **Segmenting** | Break into digestible units | One concept per slide |
| **Redundancy** | Don't duplicate channels | Don't read bullet points aloud |
| **Spatial Contiguity** | Keep related items close | Labels on diagrams, not in legend |
| **Temporal Contiguity** | Narrate with visuals | Speak as visuals appear |

### 6. Design for Accessibility

**Font Sizes (for large lecture halls):**
- Headings: 32pt minimum, prefer 44pt
- Body text: 24pt minimum
- Captions/labels: 20pt minimum

**Contrast:**
- High contrast ratios (dark on light OR light on dark)
- Avoid red/green combinations (colorblindness)
- Test: Can you read it from the back row?

**Visual Descriptions:**
- Plan to describe all images verbally ("As you can see in this graph, the trend...")
- Don't say "As you can see here..." without describing what's there

### 7. Create Slide Types

**Title Slide**
- Layout: `TITLE`
- Content: Lecture title, course name, date
- Keep clean and minimal

**Section Header**
- Layout: `SECTION_HEADER`
- Use for chunk transitions
- Include chunk number and focus

**Content Slide**
- Layout: `TITLE_AND_BODY`
- Maximum 3 bullet points
- Each bullet: 6 words or fewer

**Comparison Slide**
- Layout: `TITLE_AND_TWO_COLUMNS`
- Use for before/after, old/new, theory A/B comparisons

**Poll Slide**
- Layout: `TITLE_AND_BODY`
- Question as title
- Options A-D in body
- Include peer instruction protocol in speaker notes

**Image Slide**
- Layout: `BLANK`
- Instructor will add full-bleed image
- Provide image suggestions with links

### 8. Add Speaker Notes

For each slide, create speaker notes that include:

**Content:**
- What to SAY (not what's on the slide)
- Key points to emphasize
- Examples or stories to tell
- Transitions to next slide

**Logistics:**
- Timing (e.g., "2 minutes on this slide")
- Activity cues (e.g., "Launch poll now")
- Movement cues (e.g., "Move to center stage")

**Example speaker notes format:**
```
**Time:** 2 minutes

**Key point:** Emphasize that this mechanism explains the paradox from the hook.

**Say:** "Remember our opening puzzle about X? This is the answer. The reason Y happens is because..."

**Transition:** After explaining, launch Poll 2.
```

Note: Speaker notes in Google Slides are added through the Notes section below each slide. Document them in the slide-inventory.md for the instructor.

### 9. Visual Design Principles

See **`pedagogy/slide-design-guide.md`** for comprehensive guidance. Key principles:

**The Numbers That Matter:**
- **75-word limit**: More than 75 words = it's a document
- **6-word rule**: Aim for 6 words or fewer per slide (Godin/Reynolds)
- **3-second test**: Audiences must grasp content within 3 seconds
- **28pt minimum font**: Never smaller for keynotes

**CRAP Framework (Reynolds):**
- **Contrast**: Make different things VERY different
- **Repetition**: Consistent style throughout
- **Alignment**: Use invisible grid lines
- **Proximity**: Group related items; separate unrelated

**Simplicity:**
- One idea per slide
- Maximum 6 words per slide (aspiration), 6 lines absolute max
- Use full-bleed images when possible
- Empty space is a design element, not wasted space
- Remove logos from all but first/last slides

**The Picture Superiority Effect:**
- Hear information → remember 10% after 3 days
- Add a picture → remember 65% after 3 days
- **Images = 6x more memorable than words alone**

### 10. Finding Images

The Picture Superiority Effect means images dramatically improve retention. Proactively search for relevant images.

**Search Method:**
1. Use WebSearch with `site:unsplash.com [search terms]` or `site:pexels.com [search terms]`
2. Search for specific concepts, not generic terms (e.g., "elevator people facing forward" not "social norms")
3. Provide collection URLs organized by slide so the instructor can browse and download

**Recommended Sources (free, no attribution required):**
- [Unsplash](https://unsplash.com) — High-quality photos, excellent search
- [Pexels](https://www.pexels.com) — Good variety, includes videos
- [Wikimedia Commons](https://commons.wikimedia.org) — Public domain, historical images

**When to Suggest Images:**
- **Hook slides**: Visual that creates curiosity or emotional connection
- **Concept introduction**: Concrete example of abstract idea
- **Examples/cases**: Real-world photos that ground the concept
- **Full-bleed impact slides**: Single powerful image with minimal text

**Image Suggestion Format:**
```markdown
| Slide | Image Idea | Source |
|-------|------------|--------|
| Folkways | Elevator with people facing forward | [Unsplash elevator collection](https://unsplash.com/s/photos/elevator) |
| Subcultures | Van life interior (#vanlife aesthetic) | [Unsplash van interior](https://unsplash.com/s/photos/van-interior) |
```

**Note:** The instructor adds images themselves via the Google Slides interface—you provide curated suggestions with direct links.

## MCP Tools Reference

### Creating Presentations
```
createPresentation(title) → presentationId
```

### Adding Slides
```
addSlide(presentationId, layoutType)
  layoutType: TITLE | SECTION_HEADER | TITLE_AND_BODY | TITLE_AND_TWO_COLUMNS | BLANK | BIG_NUMBER
```

### Adding Text
```
insertTextToSlide(presentationId, slideIndex, shapeId, text)
```

### Finding and Replacing Text
```
replaceAllTextInPresentation(presentationId, findText, replaceText)
```

For complete MCP documentation, see `mcp/google-docs-mcp-setup.md`.

## Output Files to Create

1. **slides-link.md** - Document containing:
   - Google Slides presentation URL
   - Quick access link for editing
   - Instructions for the instructor

2. **slide-inventory.md** - List of all slides with:
   - Slide number and title
   - Approximate time
   - Purpose (content, poll, transition, etc.)
   - Learning outcome alignment
   - Speaker notes (full text for each slide)

3. **visual-assets.md** - List of needed visuals:
   - Images to add (with source links)
   - Diagrams to create
   - Charts to generate
   - Organized by slide number

4. **phase3-report.md** - Executive summary including:
   - Google Slides presentation link
   - Total slide count
   - Time per section
   - Slides needing instructor review
   - Visual assets the instructor needs to add

## Guiding Principles

1. **Slides support, not replace**: The speaker is the presentation; slides are visual aids.

2. **One idea per slide**: If you need more, make more slides.

3. **No full sentences**: Bullet points are cues, not scripts.

4. **Big enough for the back row**: If in doubt, make it bigger.

5. **Speaker notes are essential**: Document them in slide-inventory.md for reference.

6. **Google Slides enables collaboration**: The instructor can easily customize after you create the structure.

7. **Images are the instructor's responsibility**: Provide great suggestions; they add them.

## When You're Done

Return a summary to the orchestrator that includes:
1. Google Slides presentation URL
2. Total slide count and estimated timing
3. List of visual assets needed (with source links)
4. Any slides that need special attention
5. Questions for the instructor about visual preferences
6. Reminder that the instructor should:
   - Review and customize text
   - Add images from the visual-assets.md suggestions
   - Add their own speaker notes
   - Test the presentation in slideshow mode
