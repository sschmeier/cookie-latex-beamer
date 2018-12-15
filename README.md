# Cookiecutter latex beamer template



## Setup
Install cookiecutter:

```bash
conda install cookiecutter
```

## New latex project

```bash
# first time
cookiecutter git@gitlab.com:sschmeier/cookie-latex-beamer.git

# subsequent use
cookiecutter cookie-latex
```


## Within the project

### Bibtex
1. Link within article to Dropbox version.
2. Copy your bib-file into the same directory.

```bash
cp ~/Dropbox/configs/latex/library.bib article/references
```

### General command sequence

Makefile is included in each document directory.

```bash
# to create pdf
make pdf

# to continues recompiel on change
make pdfview

# remove artifacts
make clean
```

### Emacs

Add this to `.emacs` to enable pdflatex as default:

```
# .emacs
(setq TeX-PDF-mode t)
```

Use this shortcuts in emacs:

```
# Compile latex
C-c C-c RET

# Revert PDF
C-x C-v RET
```

