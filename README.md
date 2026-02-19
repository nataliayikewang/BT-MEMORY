# BT-MEMORY
TFG Memory – LaTeX source edited in VS Code and compiled on Overleaf.

## Project structure

```
BT-MEMORY/
├── main.tex          # Document entry point
├── bibliography.bib  # BibTeX/Biblatex references
├── figures/          # Image files used in the document
└── .vscode/
    ├── extensions.json   # Recommended VS Code extensions
    └── settings.json     # LaTeX Workshop build configuration
```

## Prerequisites

| Tool | Purpose |
|------|---------|
| [TeX Live](https://www.tug.org/texlive/) / [MiKTeX](https://miktex.org/) | Local LaTeX distribution |
| [latexmk](https://ctan.org/pkg/latexmk) | Build automation (included in TeX Live) |
| [Biber](https://biblatex-biber.sourceforge.net/) | Bibliography processor (included in TeX Live) |
| [VS Code](https://code.visualstudio.com/) | Editor |
| [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) | VS Code LaTeX extension |

## Local setup (VS Code + LaTeX Workshop)

1. **Install a LaTeX distribution** (TeX Live on Linux/macOS, MiKTeX on Windows).
2. **Open the repository in VS Code.**
3. When prompted, install the recommended extensions (`james-yu.latex-workshop`
   and `valentjn.vscode-ltex`), or run
   _Extensions: Show Recommended Extensions_ from the command palette.
4. Open `main.tex`. The document is built automatically every time you save
   (`Ctrl+S` / `Cmd+S`).  
   The compiled PDF is written to `out/main.pdf` and opens in a side panel.
5. Use **SyncTeX** to jump between source and PDF:
   - `Ctrl+Alt+J` (Win/Linux) or `Cmd+Option+J` (macOS) → source to PDF
   - `Ctrl+click` on the PDF → back to source

## Overleaf workflow

### Option A – Git integration (Overleaf Premium)

Overleaf supports syncing a project directly with a GitHub repository:

1. In Overleaf open (or create) your project.
2. Go to **Menu → Git** and link it to this repository.
3. Pull/push changes between Overleaf and GitHub normally.

### Option B – Manual upload

1. Zip the repository contents (exclude the `out/` folder and `.git/`).
2. In Overleaf use **New Project → Upload Project** and upload the zip.
3. Edit on Overleaf, download the source, and commit it back to this
   repository.

## Building from the command line

```bash
# Install dependencies (TeX Live example)
# sudo apt install texlive-full biber   # Debian/Ubuntu

# Compile (PDF will be in out/)
latexmk -pdf -outdir=out main.tex

# Clean auxiliary files
latexmk -c -outdir=out main.tex
```
