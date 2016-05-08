all: readme-example-drafttrue.png readme-example-draftfalse.png

readme-example-drafttrue.pdf readme-example-draftfalse.pdf: readme-example.tex
	TEXINPUTS=../: pdflatex -jobname=$(basename $@) $^

%.cropped.pdf: %.pdf
	pdfcrop $^ $@

%.png: %.cropped.pdf
	convert -units PixelsPerInch -density 300 $^ \
	        -bordercolor white -border 14 -bordercolor gray -border 1 \
	        $@

clean:
	-rm -f *.aux *.log *.pdf *.png

.PHONY: all clean
