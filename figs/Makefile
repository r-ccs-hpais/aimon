SOURCES := $(wildcard *.tex)
PDFS := $(SOURCES:.tex=.pdf)
PNGS := $(SOURCES:.tex=.png)
PNG_DPI := 300

.PHONY: all clean

all: $(PDFS) $(PNGS)

%.pdf: %.tex
	latexmk -pdf -interaction=nonstopmode -halt-on-error $<

%.png: %.pdf
	pdftoppm -png -r $(PNG_DPI) -singlefile $< $*

clean:
	latexmk -C
	$(RM) $(PNGS)
