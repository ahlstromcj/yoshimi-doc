#*******************************************************************************
# Makefile
#-------------------------------------------------------------------------------
##
# \file       	Makefile
# \library    	Documents
# \author     	Chris Ahlstrom
# \date       	2015-04-20
# \update     	2022-05-15
# \version    	$Revision$
# \license    	$XPC_SUITE_GPL_LICENSE$
#
# 		Makefile for LaTeX-based documentation.  It now uses latexmk (a
# 		well-known Perl script) instead of using pdflatex and makeindex
# 		directly.
#
#-------------------------------------------------------------------------------

.PHONY: clean
.PHONY: docs

all: user

user: tex-stamp
	latexmk -g -silent -pdf yoshimi-advanced-reference-manual

debug:
	latexmk -g -pdf yoshimi-advanced-reference-manual &> ../make.log

tex-stamp:
	touch tex-stamp

# Or -C instead?

clean: clean-dvi clean-pdf clean-ps clean-latexmk
	latexmk -c
	rm -f tex-stamp

clean-dvi:
	-rm -f *.dvi

clean-pdf:
	-rm -f *.pdf

clean-ps:
	-rm -f *.ps

clean-latexmk:
	-rm -f *.aux
	-rm -f *.fdb_latexmk
	-rm -f *.fls
	-rm -f *.idx
	-rm -f *.ilg
	-rm -f *.ind
	-rm -f *.lof
	-rm -f *.log
	-rm -f *.lot
	-rm -f *.out
	-rm -f *.toc

#******************************************************************************
# vim: ts=3 sw=3 noet ft=automake
#------------------------------------------------------------------------------
