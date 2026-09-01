# AI Boutique

Artificial intelligence consultancy — this repository contains the company's
graphical proposal document (catalogue style), built with LaTeX + XeLaTeX.

## Structure

```
├── README.md                 # This file
├── .gitignore                # Ignores LaTeX intermediate files
└── proposal/                 # AI Boutique proposal document
    ├── main.tex              # Root document (integrates every part)
    ├── Makefile              # Build with latexmk -xelatex
    ├── styles/               # Format files — separated from the documents
    │   ├── aiboutique-proposal.sty   # Catalogue-style format (INSEEC-inspired)
    │   ├── aiboutique-banner.sty     # Flat banners (\yBanner)
    │   └── aiboutique-cards.sty      # Flat cards    (\aiCard)
    ├── sections/             # One file per proposal part (content only)
    ├── fonts/                # Fira Sans + Oswald (+ Vazirmatn)
    ├── images/               # Images
    └── experiments/          # Earlier beamer experiments (deprecated)
```

Full build and customisation guide: [`proposal/README.md`](proposal/README.md).
