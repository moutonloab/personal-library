# CLAUDE.md - Personal Library

This document provides guidance for AI assistants working with this repository.

## Project Overview

A personal library of essays and articles stored as static HTML files. The site is owned by Menno and serves as a curated collection of readings.

## Repository Structure

```
personal-library/
├── index.html              # Main library index with article listings
├── articles/               # Directory containing all article HTML files
│   ├── Nagel-what-is-it-like-to-be-a-bat.html
│   └── how-ai-destroys-institutions.html
├── README.md               # Basic project description
└── CLAUDE.md               # This file
```

## Adding New Articles

### Step 1: Create the Article HTML File

Place the article in `/articles/` with a descriptive filename:
- Use lowercase with hyphens for multi-word titles
- Always include `.html` extension
- Example: `how-ai-destroys-institutions.html`

### Step 2: Update index.html

Add a new `<li class="library-item">` entry to the library list. Copy the template from the HTML comments in index.html:

```html
<li class="library-item">
    <a href="articles/FILENAME.html" class="library-link">
        <div class="article-title">TITLE</div>
        <div class="article-author">AUTHOR</div>
        <div class="article-meta">
            <span class="category-tag">CATEGORY</span>
            SOURCE, YEAR
        </div>
    </a>
</li>
```

## Styling Conventions

### CSS Variables (Theme)

Both `index.html` and article files use consistent CSS variables:

```css
:root {
    --bg: #faf9f6;           /* Background color */
    --text: #2c2c2c;         /* Main text color */
    --accent: #8b4513;       /* Accent/link color (sienna brown) */
    --border: #d4c4b0;       /* Border color */
    --hover: #f5f0e8;        /* Hover background */
}
```

### Typography

- Primary font: Georgia, serif
- Line height: 1.7-1.8
- Max content width: 750-800px
- Text justified in article bodies

### Responsive Design

Articles include media queries for:
- Mobile (max-width: 600px): Reduced padding and font sizes
- Print: Full-width layout

## Article HTML Structure

Articles should follow this structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Meta tags, title, embedded styles -->
</head>
<body>
    <header>
        <h1>Article Title</h1>
        <p class="author">Author Name</p>
        <p class="source">Publication info</p>
    </header>

    <article>
        <!-- Article content with <p> tags -->
        <!-- Footnote references: <a href="#note1" class="footnote-ref">1</a> -->
    </article>

    <section class="notes-section">
        <h2>Notes</h2>
        <!-- Footnotes -->
    </section>

    <footer>
        <p>Publication/copyright info</p>
    </footer>
</body>
</html>
```

## Key Conventions

1. **Self-contained HTML**: Each article includes all CSS inline (no external stylesheets)
2. **Footnotes**: Use `footnote-ref` class for superscript references linking to notes
3. **Categories**: Use short, descriptive category tags (e.g., "Philosophy", "Law & AI")
4. **Language**: Index.html comments are in Dutch; articles may be in any language
5. **No build process**: This is a static site with no compilation or bundling

## Development Workflow

1. Articles are added manually as complete HTML files
2. No package manager or build tools required
3. Test locally by opening `index.html` in a browser
4. Commit changes with descriptive messages

## Common Tasks

### Adding a new article
1. Create HTML file in `/articles/` following the structure above
2. Add entry to `index.html` library list
3. Commit both files together

### Modifying styling
- Update CSS in `index.html` for index page styles
- Update CSS in individual article files for article styles
- Keep CSS variables consistent across files
