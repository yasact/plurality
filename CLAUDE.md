# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Plurality is an open-source collaborative book project about the future of collaborative technology and democracy. The book is written by Audrey Tang, E. Glen Weyl, and a global community of contributors. This is primarily a content/documentation repository, not a software development project.

## Repository Structure

- `contents/` - Main book content in multiple languages
  - `english/` - English version chapters (numbered markdown files)
  - `traditional-mandarin/` - Traditional Chinese version
- `docs/` - Project documentation website (MkDocs)
- `figs/` - Figures, images, and data visualizations for the book
  - `data/` - Jupyter notebooks and datasets for generating figures
- `scripts/` - Build and utility scripts

## Common Commands

### Building the Book

The book is built using Pandoc in a Docker container:

```bash
# Build English PDF and ePub
./scripts/make-book.pl

# Build Traditional Chinese PDF and ePub  
./scripts/make-book-zh-tw.pl
```

### Documentation Website

The documentation site uses MkDocs:

```bash
# Install MkDocs (if not already installed)
pip install mkdocs mkdocs-material

# Serve documentation locally
mkdocs serve

# Build static documentation
mkdocs build
```

### Working with Figures

Data visualizations are generated using Jupyter notebooks in `figs/data/`. Each visualization directory contains:
- A Jupyter notebook (`.ipynb`)
- Data files (`.csv`, `.xlsx`)
- Generated images (`.png`)
- A `readme.md` explaining the visualization

## Key Architectural Concepts

### Content Organization

1. **Chapter Numbering**: Files follow pattern `X-Y-title.md` where X is section number, Y is chapter number
2. **Sections**:
   - 0: Front matter (endorsements, authors, credits)
   - 1: Preface
   - 2: Introduction
   - 3: Plurality concept
   - 4: Digital rights/freedoms
   - 5: Collaborative technologies
   - 6: Real-world applications
   - 7: Policy and conclusion

### Build Process

The Perl scripts in `scripts/` combine markdown files into a single document, then use Pandoc with custom filters (like `emoji_filter.js`) to generate PDF and ePub outputs. The process:
1. Concatenates markdown files in order
2. Processes emoji and special characters
3. Generates PDF via XeLaTeX
4. Adds cover page using pdftk

### Governance Model

The project uses Gov4Git for decentralized governance and plans to transition to full community control after physical publication. Contributors receive recognition tokens (Plural Credits) for various types of contributions.

### Translation Workflow

Translations are maintained as separate GitHub forks. Active translations include Ukrainian, Japanese, German, Korean, and French. Traditional Mandarin is a root language alongside English.

## Important Notes

- All content is CC0 (public domain)
- Avoid creating new files unless necessary - prefer editing existing content
- The project emphasizes collaborative principles it advocates for
- Financial aspects are minimal - focus is on community contribution
- Use the Discord server for coordination with other contributors