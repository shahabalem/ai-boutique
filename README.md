# AI Boutique

Artificial intelligence consultancy — this repository contains the company's
executive strategy document **"Strategic AI Reinvention & Organizational
Transformation"** (graphical, catalogue style), built with LaTeX + XeLaTeX.

## Structure

```
├── README.md                 # This file
├── .gitignore                # Ignores LaTeX intermediate files
└── strategy/                 # Executive strategy document
    ├── main.tex              # Root document (integrates every part)
    ├── Makefile              # Build with latexmk -xelatex
    ├── styles/               # Format files — separated from the documents
    │   ├── aiboutique-strategy.sty   # Catalogue-style format (INSEEC-inspired)
    │   ├── aiboutique-banner.sty     # Flat banners (\yBanner)
    │   └── aiboutique-cards.sty      # Flat cards    (\aiCard)
    ├── sections/             # One file per document part (content only)
    ├── fonts/                # Fira Sans + Oswald
    └── images/               # Images
```

Full build and customisation guide: [`strategy/README.md`](strategy/README.md).
