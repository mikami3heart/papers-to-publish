MAIN = main
TEX = platex
BIB = pbibtex
TEXSRC = main.tex main.bib

FIG = $(wildcard figs/*.{pdf,eps,png,jpg})
XBB = $(patsubst %.pdf,%.xbb, $(wildcard figs/*.pdf)) \
	$(patsubst %.png,%.xbb, $(wildcard figs/*.png)) \
	$(patsubst %.jpg,%.xbb, $(wildcard figs/*.jpg))

all: $(MAIN).pdf

$(XBB) : $(FIG)
	(cd figs; make)

$(MAIN).aux: $(TEXSRC) $(XBB)
	${TEX} $(MAIN)

$(MAIN).bbl : $(MAIN).aux $(MAIN).bib
	${BIB} $(MAIN) 
	${TEX} $(MAIN)
	${BIB} $(MAIN) 

$(MAIN).dvi: $(MAIN).bbl
	${TEX} $(MAIN)

	#	${TEX} '\let\DRAFT=$(DRAFT) \input' $(MAIN)

$(MAIN).pdf: $(MAIN).dvi
	dvipdfmx -p a4 $(MAIN).dvi

clean:
	rm -f $(MAIN).dvi $(MAIN).out $(MAIN).bbl *.aux *.log *.lot *.lof *.blg *.toc
	(cd figs; make clean)

