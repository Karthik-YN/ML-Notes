# ML Notes

A personal, browser-based knowledge base I built to organize and maintain my
Machine Learning and AI study notes.

I wanted a simple place where I could keep theory, code, diagrams, screenshots,
and related topics together without depending on a database or a heavy
note-taking platform.

The project is intentionally lightweight: it is a single HTML application,
requires no backend, and stores my notes locally in the browser.

## What I Use It For

I use ML Notes to organize topics that I study across:

- Machine Learning
- Deep Learning
- Computer Vision
- Generative AI
- LLMs
- RAG and retrieval systems
- Python and related technical concepts
- Research and project notes

The structure is based around sections and nested sub-sections so that larger
topics can be broken down into smaller concepts.

## Features

### Notes and Organization

- Unlimited nested sections and sub-sections
- Collapsible sidebar tree
- Text notes with lightweight Markdown-style formatting
- Code blocks with language selection and syntax highlighting
- Image blocks for screenshots, diagrams, and visual explanations
- Tags for organizing topics
- Favorites for frequently referenced notes
- Learning status:
  - Learning
  - Understood
  - Review
- Recently edited notes
- Related notes with two-way linking

### Search and Review

- Search across:
  - Section titles
  - Text content
  - Code
  - Tags
- Matching sections remain visible with their parent sections expanded
- Review queue for topics marked as `Review`
- Last reviewed tracking
- Manual "Mark reviewed" functionality
- Favorites-only filtering

### Export and Backup

- Export individual sections to PDF
- Export the complete notebook to PDF
- Download the complete notebook as JSON
- Restore notes from a JSON backup
- Storage usage indicator
- Save status indicator

### Other

- Light and dark themes
- Mobile-friendly layout
- Fullscreen image viewer
- Quick capture for quickly writing down an idea
- Keyboard shortcuts
- Automatic saving to browser storage

## Google Drive Backup

I later added optional Google Drive support so I can keep an additional copy
of individual notes in my personal Google Drive.

This is currently **Phase 1** of the integration.

Google Drive is not used as the primary database or as a real-time sync
mechanism. The application continues to use browser `localStorage` as its
primary storage.

### Current workflow

```text
ML Notes
   │
   ├── Primary storage
   │      └── Browser localStorage
   │
   └── Optional backup
          └── Google Drive
                 └── ML Notes/
                       └── note.json
