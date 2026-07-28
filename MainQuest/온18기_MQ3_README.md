# An Exploratory Comparison of Scratch Seq2Seq-Style Attention and Pretrained BERT

This repository contains the LaTeX source for an ICLR-inspired graduate course paper on masked-token prediction in a low-resource Korean lyric corpus.

## Author

- **KIM, JEONG MIN**
- AIFFEL, RS 18th, MQ3
- soboro.commit@gmail.com

## Repository structure

```text
.
├── main.tex
├── references.bib
├── MQ_Lyrics_ICLR_Paper_KIM_JEONG_MIN.pdf
├── figures/
├── latexmkrc
├── Makefile
├── CITATION.cff
├── GITHUB_UPLOAD_STEPS.md
├── .gitignore
└── README.md
```

## Compile locally

The bibliography uses `biblatex` with the APA style and the Biber backend.

```bash
make
```

Equivalent command:

```bash
latexmk -pdf main.tex
```

Clean auxiliary files:

```bash
make clean
```

## Compile in Overleaf

1. Upload the repository as a ZIP or upload all files while preserving the `figures/` folder.
2. Set `main.tex` as the main document.
3. Select **pdfLaTeX** as the compiler.
4. Recompile. Overleaf should invoke Biber automatically; compile again if citations initially appear unresolved.

## Data and copyright

The copyrighted lyric text is not included. Public materials are limited to LaTeX source, model settings, aggregate results, anonymized analyses, and figures.
