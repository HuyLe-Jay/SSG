# Static Site Generator

A Python-based static site generator that converts Markdown content into a fully rendered HTML website. Built as a learning project on [Boot.dev](https://www.boot.dev).

## Features

- Converts Markdown files to HTML pages using a shared HTML template
- Supports inline Markdown: bold, italic, code, links, and images
- Supports block-level Markdown: headings, paragraphs, lists, blockquotes, and code blocks
- Recursively processes nested content directories
- Copies static assets (CSS, images) to the output directory
- Configurable base path for deployment to subdirectory hosts (e.g. GitHub Pages)

## Project Structure
.
├── content/ # Markdown source files
├── static/ # Static assets (CSS, images)
├── docs/ # Generated site output (committed for GitHub Pages)
├── src/ # Python source code
│ ├── main.py
│ ├── gencontent.py
│ ├── copystatic.py
│ ├── htmlnode.py
│ ├── inline_markdown.py
│ ├── markdown_blocks.py
│ └── textnode.py
├── template.html # HTML template used for all pages
├── main.sh # Run local dev server
└── build.sh # Build for production (GitHub Pages)

## Requirements

- Python 3.x

No third-party dependencies required.

### Local Development

Run the generator and start a local server at `http://localhost:8888`:

```bash
bash main.sh
```

### Production Build (GitHub Pages)

Build the site with the correct base path for your GitHub Pages URL:

  bash build.sh

The build.sh script runs:

  python3 src/main.py "/REPO_NAME/"

This replaces all root-relative links (href="/ and src="/) with the correct subdirectory path.

### Deployment

This site is deployed via GitHub Pages from the docs/ directory on the main branch.

  Live URL: https://USERNAME.github.io/REPO_NAME/

To deploy, commit and push the docs/ directory after running build.sh.

### Running Tests

  bash test.sh

Replace `USERNAME` and `REPO_NAME` with your actual GitHub username and repository name. You may also want to personalize the intro line if this is more than just a learning project.



