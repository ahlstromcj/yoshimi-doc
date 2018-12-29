#*******************************************************************************
# Makefile
#-------------------------------------------------------------------------------
##
# \file       	Makefile
# \library    	Documents
# \author     	Chris Ahlstrom
# \date       	2015-04-20
# \update     	2018-12-28
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
	latexmk -g -silent -pdf yoshimi-user-manual

debug:
	latexmk -g -pdf yoshimi-user-manual &> ../make.log

tex-stamp:
	touch tex-stamp

# Or -C instead?

clean: clean-dvi clean-pdf clean-ps
	latexmk -c
	rm -f tex-stamp

clean-dvi:
	-rm -f *.dvi

clean-pdf:
	-rm -f *.pdf

clean-ps:
	-rm -f *.ps

#******************************************************************************
# vim: ts=3 sw=3 noet ft=automake
#------------------------------------------------------------------------------
