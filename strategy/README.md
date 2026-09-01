# Strategic AI Reinvention & Organizational Transformation

An executive-level, evidence-based strategy document built with LaTeX
(article) and XeLaTeX. The core philosophy:

> *"We do not implement AI for the organization; we solve organizational
> problems using AI."*

Every claim is grounded in published research from McKinsey, Gartner,
Harvard Business Review, MIT Sloan Management Review (with BCG), MIT CISR,
Forbes, Business Insider, Reuters and Kotter — cited inline, e.g.
`[McKinsey 2023]`, `[Gartner 2023]`.

The design is inspired by the
[INSEEC MSc & MBA brochure](https://issuu.com/inseec/docs/plaquette-inseec-msc-mba)
and the structure follows [yLaTeX](https://github.com/HarveySheppard/yLaTeX):
format files are separated from content, and each part of the document lives
in its own file.

## Project structure

```
strategy/
├── main.tex                 # Root document — integrates every part
├── Makefile                 # Build with latexmk -xelatex
├── styles/                  # Format files — separated from the documents
│   ├── aiboutique-strategy.sty   # Catalogue-style format (INSEEC-inspired)
│   ├── aiboutique-banner.sty     # Flat banners  \yBanner  (adapted from yLaTeX)
│   └── aiboutique-cards.sty      # Flat cards    \aiCard   (adapted from yLaTeX)
├── sections/                # One file per document part (content only)
│   ├── 00-cover.tex
│   ├── 01-executive-summary.tex
│   ├── 02-ai-paradigm.tex           # Section 1 — The AI Paradigm
│   ├── 03-value-ladder.tex          # Section 2 — Value Creation Ladder
│   ├── 04-application-categories.tex# Section 3 — Application Categories
│   ├── 05-organizational-readiness.tex # Section 4 — Organizational Readiness
│   ├── 06-why-ai-fails.tex          # Section 5 — Why AI Fails
│   ├── 07-reinvention-roadmap.tex   # Section 6 — Reinvention Roadmap
│   ├── 08-case-studies.tex          # Section 7 — Case Studies
│   └── 09-conclusion.tex            # Section 8 — Conclusion & Call to Action
├── fonts/                   # Fira Sans (body), Oswald (headings)
└── images/                  # Images
```

## Build

From the `strategy/` directory:

```sh
make                 # or: latexmk -xelatex main.tex
```

> Requires XeLaTeX. Run the build twice (or use latexmk) so the full-bleed
> overlays and header marks settle.

## Design (reference: INSEEC brochure)

| Element        | Value                                        |
|----------------|----------------------------------------------|
| Primary colour | Navy `#002D74` (`inNavy`)                    |
| Accents        | Bright blue `#0062E1` / light `#9CBDFF`      |
| Backgrounds    | White, pale blue `#DBEBFF` / `#F0F7FF`       |
| Body font      | Fira Sans                                     |
| Display font   | Oswald                                        |

Graphical building blocks available from the format packages:

- `\strategyPart{kicker}{title}` — full-width navy band that opens each part.
- `\strategyCover` — full-page catalogue cover (reads `\title`, `\subtitle`,
  `\serieskicker`, `\author`, `\date`; neutral, no branding).
- `\serieslabel{text}` — short label shown in the header/footer.
- `\infobox{title}{body}` — light callout box with navy heading.
- `\stat{number}{label}` — big-number statistic.
- `\yBanner[keys]{text}` — flat banner with angled endings.
- `\aiCard[keys]{content}` — rounded card with shadow; `\aiCardTitle{...}`.
- Styled tables: `\rowcolor{inNavy}` header + `\hcell{...}` white header cells.

## Adding / editing a document part

1. Create a file in `sections/` (e.g. `10-appendix.tex`).
2. Open it with `\strategyPart{Appendix}{Title}`.
3. Add it to `main.tex` with `\input{sections/10-appendix.tex}`.

## Licence

`aiboutique-banner.sty` and `aiboutique-cards.sty` are adaptations of `yBanner`
and `yCards` from [yLaTeX](https://github.com/HarveySheppard/yLaTeX) and are
distributed under the LPPL. The Fira Sans and Oswald fonts are redistributed
under their own open licences (SIL OFL).
