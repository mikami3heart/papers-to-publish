TARGET := main

.PHONY: all open clean

all:
	platex $(TARGET)
	platex $(TARGET)
	platex $(TARGET)
	dvipdfmx -V 5 $(TARGET)
#	jbibtex $(TARGET)

open:
	open -a Preview $(TARGET).pdf

clean:
	-rm -f *~
	-rm -f $(TARGET).aux $(TARGET).bbl $(TARGET).blg
	-rm -f $(TARGET).dvi $(TARGET).log
	-rm -f $(TARGET).out
