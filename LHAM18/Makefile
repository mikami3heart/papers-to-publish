MAIN = PMlib
TEX = platex
BIB = pbibtex
TEXSRC = PMlib.tex PMlib.bib

FIG = $(wildcard figs/*.{pdf,eps,png,jpg})

TEX_PARAM='\input'

all: $(MAIN).pdf

$(MAIN).pdf: $(MAIN).dvi
	dvipdfmx -p a4 -o $(MAIN).pdf $(MAIN).dvi

$(MAIN).dvi: $(MAIN).bbl
	${TEX} $(TEX_PARAM) $(MAIN)

$(MAIN).aux: $(TEXSRC) $(FIG)
	(cd figs; make)
	${TEX} $(TEX_PARAM) $(MAIN)

$(MAIN).bbl : $(MAIN).aux $(MAIN).bib
	${BIB} $(MAIN) 
	${TEX} $(TEX_PARAM) $(MAIN)
	${BIB} $(MAIN) 

clean:
	rm -f *.dvi *.out *.bbl *.aux *.log *.lot *.lof *.blg *.toc $(MAIN).pdf

distclean:
	rm -f *.dvi *.out *.bbl *.aux *.log *.lot *.lof *.blg *.toc $(MAIN).pdf
	rm -f *.fls *.fdb_latexmk
	(cd figs; make clean)

