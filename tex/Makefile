#*******************************************************************************
# Makefile
#-------------------------------------------------------------------------------
##
# \file       	Makefile
# \library    	Documents
# \author     	Chris Ahlstrom
# \date       	2015-04-20
# \update     	2015-07-03
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

# -auxdir=aux to direct .log, .aux, ... files to a separate directory.
# -outdir=out to direct output files to a separate directory.
#
# Both are essentially options of pdflatex.

user: tex-stamp
	latexmk -silent -pdf yoshimi-user-manual

# No longer needed.
#
# outline:
#	latexmk -silent -pdf contrib/yoshimi-outline

tex-stamp:
	touch tex-stamp

# Or -C instead?

clean: clean-dvi clean-pdf
	latexmk -c
	rm -f tex-stamp

clean-dvi:
	-rm -f *.dvi

clean-pdf:
	-rm -f *.pdf

#******************************************************************************
# vim: ts=3 sw=3 noet ft=automake
#------------------------------------------------------------------------------
