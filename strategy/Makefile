#==============================================================================
#  Makefile — Strategic AI Reinvention & Organizational Transformation
#  Build with XeLaTeX (fontspec, Fira Sans + Oswald fonts)
#==============================================================================
LATEXMK   = latexmk
MAIN      = main.tex
PDF       = main.pdf

# Default: build the PDF
all: $(PDF)

$(PDF): $(MAIN) sections/*.tex styles/*.sty
	$(LATEXMK) -xelatex -interaction=nonstopmode -halt-on-error $(MAIN)

# Remove generated auxiliary files (keeps the PDF)
clean:
	$(LATEXMK) -c

# Remove auxiliary files and the PDF
distclean:
	$(LATEXMK) -C

.PHONY: all clean distclean
