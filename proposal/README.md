# AI Boutique — Proposal

A graphical, catalogue-style proposal document for **AI Boutique**, built with
LaTeX (article) and XeLaTeX. The design is inspired by the
[INSEEC MSc & MBA brochure](https://issuu.com/inseec/docs/plaquette-inseec-msc-mba)
and the structure follows [yLaTeX](https://github.com/HarveySheppard/yLaTeX):
style files are separated from the document content, and each part of the
proposal lives in its own file.

## Project structure

```
proposal/
├── main.tex                 # Root document — integrates every part
├── Makefile                 # Build with latexmk -xelatex
├── styles/                  # Style / format files — separated from documents
│   ├── aiboutique-proposal.sty   # Catalogue-style format (INSEEC-inspired)
│   ├── aiboutique-banner.sty     # Flat banners  \yBanner  (adapted from yLaTeX)
│   └── aiboutique-cards.sty      # Flat cards    \aiCard   (adapted from yLaTeX)
├── sections/                # One file per proposal part (content only)
│   ├── 00-cover.tex
│   ├── 01-executive-summary.tex
│   ├── 02-company-profile.tex
│   ├── 03-services.tex
│   ├── 04-methodology.tex
│   ├── 05-timeline.tex
│   ├── 06-team.tex
│   ├── 07-pricing.tex
│   └── 08-contact.tex
├── fonts/                   # Fira Sans (body), Oswald (headings), Vazirmatn
├── images/                  # Images
└── experiments/             # Earlier beamer experiments (deprecated)
```

## Build

From the `proposal/` directory:

```sh
make                 # or: latexmk -xelatex main.tex
```

> Requires XeLaTeX. Run the build twice (or use latexmk) so the full-bleed
> overlays and the header marks settle.

## Design (reference: INSEEC brochure)

| Element        | Value                                        |
|----------------|----------------------------------------------|
| Primary colour | Navy `#002D74` (`inNavy`)                    |
| Accents        | Bright blue `#0062E1` / light `#9CBDFF`      |
| Backgrounds    | White, pale blue `#DBEBFF` / `#F0F7FF`       |
| Body font      | Fira Sans                                     |
| Display font   | Oswald                                        |

Graphical building blocks available from the style packages:

- `\proposalpart{kicker}{title}` — full-width navy band that opens each part.
- `\proposalCover` — full-page catalogue cover (reads `\title`, `\subtitle`,
  `\proposalkicker`, `\author`, `\date`).
- `\infobox{title}{body}` — light callout box with navy heading.
- `\stat{number}{label}` — big-number statistic.
- `\yBanner[keys]{text}` — flat banner with angled endings.
- `\aiCard[keys]{content}` — rounded card with shadow; `\aiCardTitle{...}`.
- Styled tables: `\rowcolor{inNavy}` header + `\th{...}` white header cells
  (see `05-timeline.tex` and `07-pricing.tex`).

## Adding / editing a proposal part

1. Create a file in `sections/` (e.g. `09-appendix.tex`).
2. Open it with `\proposalpart{09 · Appendix}{Appendix}`.
3. Add it to `main.tex` with `\input{sections/09-appendix.tex}`.

## Licence

`aiboutique-banner.sty` and `aiboutique-cards.sty` are adaptations of `yBanner`
and `yCards` from [yLaTeX](https://github.com/HarveySheppard/yLaTeX) and are
distributed under the LPPL. The Fira Sans and Oswald fonts are redistributed
with their own open licences (SIL OFL).
