# Google Docs MCP Setup Guide

This guide covers the installation and configuration of the Google Docs MCP server, which enables Claude to create and edit Google Slides presentations directly.

## Overview

The Google Docs MCP is an enhanced Model Context Protocol server that provides programmatic access to Google's productivity suite, including:
- **Google Slides**: Create presentations, add slides, insert text
- **Google Docs**: Read and edit documents
- **Google Sheets**: Read and write spreadsheet data
- **Google Drive**: Manage files and folders

**Repository**: <https://github.com/nealcaren/google-docs-mcp>

## Installation Steps

### 1. Create Google Cloud Project

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project (or select an existing one)
3. Enable the following APIs:
   - Google Docs API
   - Google Sheets API
   - Google Slides API
   - Google Drive API

### 2. Configure OAuth Consent Screen

1. Navigate to **APIs & Services > OAuth consent screen**
2. Choose **External** user type (or Internal if using Workspace)
3. Fill in the required app information
4. Add the following scopes:
   - `https://www.googleapis.com/auth/documents`
   - `https://www.googleapis.com/auth/spreadsheets`
   - `https://www.googleapis.com/auth/presentations`
   - `https://www.googleapis.com/auth/drive`

### 3. Create OAuth Credentials

1. Navigate to **APIs & Services > Credentials**
2. Click **Create Credentials > OAuth client ID**
3. Select **Desktop app** as the application type
4. Download the credentials JSON file
5. Rename it to `credentials.json`

### 4. Install the MCP Server

```bash
# Clone the repository
git clone https://github.com/nealcaren/google-docs-mcp.git
cd google-docs-mcp

# Place credentials.json in the project root
cp /path/to/downloaded/credentials.json .

# Install dependencies
npm install

# Build the project
npm run build
```

### 5. Authenticate with Google

Run the server once manually to complete OAuth authentication:

```bash
npm start
```

This will open a browser window for Google authentication. After authorizing, a `token.json` file is created.

### 6. Configure Claude Desktop

Add the MCP server to your Claude Desktop configuration (`mcp_config.json`):

```json
{
  "mcpServers": {
    "google-docs": {
      "command": "node",
      "args": ["/absolute/path/to/google-docs-mcp/dist/index.js"]
    }
  }
}
```

**Important**: Use the absolute path to the compiled server.

## Available Tools for Google Slides

### Creating Presentations

**`createPresentation`**
Creates a new Google Slides presentation.

```
Parameters:
  title: string - The title of the presentation

Returns:
  presentationId: string - ID for subsequent operations
  url: string - Direct link to the presentation
```

### Managing Slides

**`addSlide`**
Adds a new slide to an existing presentation.

```
Parameters:
  presentationId: string - The presentation ID
  layoutType: string - One of:
    - TITLE - Title slide
    - SECTION_HEADER - Section divider
    - TITLE_AND_BODY - Standard content slide
    - TITLE_AND_TWO_COLUMNS - Two-column layout
    - BLANK - Empty slide for custom content
    - BIG_NUMBER - Large number/statistic display

Returns:
  slideId: string - ID of the new slide
```

### Adding Content

**`insertTextToSlide`**
Inserts text into a specific placeholder or shape on a slide.

```
Parameters:
  presentationId: string - The presentation ID
  slideIndex: number - Zero-based slide index
  shapeId: string - The placeholder/shape ID to insert into
  text: string - The text content to insert
```

### Bulk Operations

**`replaceAllTextInPresentation`**
Finds and replaces text throughout the entire presentation.

```
Parameters:
  presentationId: string - The presentation ID
  findText: string - Text to search for
  replaceText: string - Replacement text
```

## Workflow for Lecture Slides

### Step 1: Create Presentation
```
Tool: createPresentation
  title: "SOC 101 - Week 5: Social Stratification"
→ Returns: presentationId, url
```

### Step 2: Add Slides
```
Tool: addSlide
  presentationId: [from step 1]
  layoutType: "TITLE"

Tool: addSlide
  presentationId: [from step 1]
  layoutType: "TITLE_AND_BODY"

[Repeat for each slide...]
```

### Step 3: Populate Content
```
Tool: insertTextToSlide
  presentationId: [from step 1]
  slideIndex: 0
  shapeId: [title placeholder]
  text: "Social Stratification"

[Repeat for each content element...]
```

### Step 4: Share the Link
The presentation URL from step 1 can be shared with the instructor for:
- Adding images
- Customizing formatting
- Adding speaker notes
- Final review

## Common Layout Types Explained

| Layout | Description | Use Case |
|--------|-------------|----------|
| `TITLE` | Large centered title with optional subtitle | Opening slide, course info |
| `SECTION_HEADER` | Section divider with large text | Chunk transitions, topic shifts |
| `TITLE_AND_BODY` | Title with bullet point area | Standard content slides |
| `TITLE_AND_TWO_COLUMNS` | Title with two content columns | Comparisons, before/after |
| `BLANK` | Empty slide | Full-bleed images, custom layouts |
| `BIG_NUMBER` | Large number with description | Statistics, key figures |

## Tips for Effective Use

1. **Plan slide structure first**: Map out all slides before creating to minimize API calls

2. **Use consistent layouts**: Stick to 2-3 layout types for visual consistency

3. **Batch similar operations**: Create all slides first, then populate content

4. **Document the URL**: Save the presentation URL in `slides-link.md` immediately

5. **Let instructors add images**: The MCP can add text efficiently; images are easier to add manually in Google Slides

## Troubleshooting

### "Token expired" Error
Delete `token.json` and re-authenticate by running `npm start`.

### "Quota exceeded" Error
Google APIs have rate limits. Wait a few minutes and retry, or reduce the number of rapid API calls.

### "Invalid presentation ID" Error
Ensure you're using the ID returned from `createPresentation`, not the URL.

### "Shape not found" Error
Layout placeholders have specific IDs. Use the Google Slides UI to inspect placeholder IDs if needed.

## Additional Resources

- [Google Slides API Documentation](https://developers.google.com/slides/api)
- [MCP Repository Issues](https://github.com/nealcaren/google-docs-mcp/issues)
- [Google Cloud Console](https://console.cloud.google.com/)
