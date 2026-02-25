# cv-fnr

1 page CV for FNR applications with minimal personal information.

Latest PDF can always be found here: [Trefois CV FNR PDF](https://github.com/Trefex/cv-fnr/releases/latest/download/Trefois_CV-FNR.pdf)

## Build locally (macOS)

### 1) Install LaTeX

Both options below include `latexmk` and `xelatex` — no extra installs needed.

Recommended (full TeX Live, no GUI apps — matches GitHub Actions environment closely):

```bash
brew install --cask mactex-no-gui
```

Alternative (smaller download, may need extra packages for complex documents):

```bash
brew install --cask basictex
```

> After install, open a **new terminal** before running the build. TeX binaries are added to `/Library/TeX/texbin` automatically by both casks.

### 2) Compile the CV

```bash
latexmk -xelatex -interaction=nonstopmode -halt-on-error Trefois_CV-FNR.tex
```

Output: `Trefois_CV-FNR.pdf`

To clean up auxiliary files afterwards:

```bash
latexmk -c
```

### 3) (Optional) Verify it is 1 page

```bash
brew install poppler   # one-time install
pdfinfo Trefois_CV-FNR.pdf | grep '^Pages'
```