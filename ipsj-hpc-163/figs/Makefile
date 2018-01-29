ALL =	$(patsubst %.png,%.xbb, $(wildcard *.png)) \
	$(patsubst %.pdf,%.xbb, $(wildcard *.pdf)) \
	$(patsubst %.jpg,%.xbb, $(wildcard *.jpg))

.SUFFIXES: .jpg .png .pdf .xbb
.png.xbb:
	ebb -x $<

.pdf.xbb:
	extractbb $<

.jpg.xbb:
	extractbb $<

all: $(ALL)

clean:
	rm -f *.xbb

