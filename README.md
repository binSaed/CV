# [CV - Abdelrahman Saed](https://bnsaed.com/CV/cv.pdf)

[![Regenerate CV PDF](https://github.com/binSaed/CV/actions/workflows/regenerate-cv.yml/badge.svg)](https://github.com/binSaed/CV/actions/workflows/regenerate-cv.yml)


LaTeX-based professional CV/resume.

## Prerequisites

- A LaTeX distribution installed on your system:
  - **macOS:** [BasicTeX](https://www.tug.org/mactex/morepackages.html) or [MacTeX](https://www.tug.org/mactex/)
  - **Windows:** [MiKTeX](https://miktex.org/)
  - **Linux:** `sudo apt install texlive-full`

### Required LaTeX Packages

- `inputenc`, `fontenc`, `lato`, `geometry`, `xcolor`
- `hyperref`, `enumitem`, `paracol`, `titlesec`

## Build

### Quick Build

```bash
pdflatex cv.tex
```

### With Better Output Handling

```bash
pdflatex -interaction=nonstopmode cv.tex
```

Run twice to resolve references and outlines:

```bash
pdflatex -interaction=nonstopmode cv.tex && pdflatex -interaction=nonstopmode cv.tex
```

The output PDF will be generated as `cv.pdf` in the current directory.

### Installing Missing Packages

If you get errors about missing packages (e.g., `lato.sty`, `fontaxes.sty`, etc.):

**macOS (with BasicTeX):**
```bash
sudo tlmgr install lato fontaxes paracol titlesec enumitem
```

**Debian/Ubuntu:**
```bash
sudo apt install texlive-latex-extra texlive-fonts-extra
```

**Windows (MiKTeX):**
Packages are installed automatically on first use, or use MiKTeX Console.

## Preview in VS Code

1. Install the [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) extension.
2. Open `cv.tex` and press `Cmd+Option+V` (macOS) or `Ctrl+Alt+V` (Windows/Linux) to preview.

## Structure

- [cv.tex](cv.tex) - Main CV source file
- [cv.pdf](cv.pdf) - Generated PDF output

## Automation

This repository uses GitHub Actions to automatically regenerate `cv.pdf` whenever `.tex` files are pushed to the `main` branch. The workflow:

1. Triggers on push to `main` when `.tex` files change
2. Installs required LaTeX packages
3. Builds the PDF using `pdflatex`
4. Commits and pushes the updated PDF back to the repository

The workflow definition is in [`.github/workflows/regenerate-cv.yml`](.github/workflows/regenerate-cv.yml).
