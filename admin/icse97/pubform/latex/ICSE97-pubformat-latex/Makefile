####################################################################
#
# RCS: $Id: Makefile,v 1.9 1994/02/24 19:23:43 chiron Exp $ 
#
####################################################################

default:	Makefile icse97-pubform


###################################
## ICSE97 pubform LaTEX example  ##
###################################

icse97-pubform:	pubform.ps

MACROS = icse97.sty 
SECTIONS = pubform.tex

INGREDIENTS = $(MACROS) $(SECTIONS) 

paper.dvi: $(INGREDIENTS) 



####################################################################
## rules
########

%.dvi: %.tex  
	-@latex $*; while fgrep -s 'Rerun to get cross-references right.' $*.log; do latex $*; done

%.ps: %.dvi  
	dvips $* > $@


####################################################################
## useful pseudotargets
#######################

bib::         ; bibtex paper; rm paper.dvi; 
clean::       ; /bin/rm -i *~ paper.aux paper.bbl paper.blg paper.log paper.toc 
preview::     ; xdvi paper
preview_ps::  ; gs paper.ps
print::       ; lpr paper.ps
print_sparc:: ; dvips -q -r -400 paper.dvi | lpr
spell::       ; tspell *.tex *.bbl
####################################################################
