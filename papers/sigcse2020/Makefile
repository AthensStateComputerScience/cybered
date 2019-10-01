#
# File:   lecturenotes.mak
# Author: Adam Lewis
# Purpose:
# Build lectures notes for a single module
#
# Tools for building latex
LATEXMK = latexmk -f
RM = rm -f
.PHONY: all mostlyclean clean release

# Rules
%.pdf: %.tex
	$(LATEXMK) -pdf -M -MP -MF $*.d $*

# Targets


all: acmse19_pymine

release: all mostlyclean

acmse19_pymine: acmse19_pymine.pdf

# Clean targets
mostlyclean:
	$(LATEXMK) -silent -c
	$(RM) *.bbl *.aux *.fls *.fdb_latexmk *.out *.log *.toc
	$(RM) *.run.xml *.synctex.gz *.nav *.snm
	$(RM) *.vrb
	$(RM) *.d 

clean: mostlyclean
	$(LATEXMK) -silent -C
	$(RM) *.pdf
# Include auto-genrated dependenies
-include *.d
