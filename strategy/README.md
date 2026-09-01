# Strategic AI Reinvention & Organizational Transformation
# (Organizational Transformation in the Age of AI)

An executive-level, evidence-based **whitepaper / research survey** built with
LaTeX (article) and XeLaTeX. The core philosophy:

> *"We do not implement AI for the organization; we solve organizational
> problems using AI."*

Every claim is grounded in published research from McKinsey, Gartner,
Harvard Business Review, MIT Sloan Management Review (with BCG), MIT CISR,
Stanford HAI, the World Economic Forum, Deloitte AI Institute, NIST, OECD,
Anthropic and Microsoft agent research, OWASP, ISO/IEC, EU AI Act,
Forbes, Business Insider, Reuters and Kotter — cited inline, e.g.
`[McKinsey 2023]`, `[Gartner 2023]`, `[Anthropic]`, `[NIST AI RMF]`.

The document is typeset in **two columns** with continuous flow (no forced
page breaks between parts), like a journal article or professional whitepaper.
Wide tables and diagrams are automatically scaled to the column width.

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
├── sections/                # One file per part — organized in five acts + back matter
│   ├── 00-cover.tex
│   ├── 01-executive-summary.tex       # Act 1 · The Problem
│   ├── 02-introduction.tex
│   ├── 03-definitions.tex             # Act 2 · The Landscape
│   ├── 04-theoretical-foundations.tex
│   ├── 05-ai-paradigm.tex
│   ├── 06-transformation-models.tex
│   ├── 07-value-ladder.tex
│   ├── 08-application-categories.tex
│   ├── 09-how-ai-works.tex
│   ├── 10-ai-by-function.tex
│   ├── 11-data-technology.tex
│   ├── 12-operating-models.tex        # Act 3 · The Organization
│   ├── 13-organizational-readiness.tex
│   ├── 14-work-transformation.tex
│   ├── 15-people-skills-culture.tex
│   ├── 16-ai-capabilities.tex
│   ├── 17-governance.tex
│   ├── 18-why-ai-fails.tex            # Act 4 · The Journey
│   ├── 19-case-studies.tex
│   ├── 20-measurement.tex
│   ├── 21-roadmap.tex
│   ├── 22-comparative-analysis.tex    # Act 5 · The Path Forward
│   ├── 23-predictions.tex
│   ├── 24-conclusion.tex
│   ├── 25-methodology.tex             # Back matter
│   ├── 26-references.tex
│   ├── 27-glossary.tex
│   └── 28-appendix-toolkit.tex
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
