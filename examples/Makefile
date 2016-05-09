all: example-drafttrue.pdf example-draftfalse.pdf

%.pdf: %.tex ../draft.sty
	TEXINPUTS=../: pdflatex $^

example-drafttrue.tex: example.tex
	sed 's/^\\draftfalse/% \0/' example.tex > example-drafttrue.tex

example-draftfalse.tex: example.tex
	cp example.tex example-draftfalse.tex

clean:
	-rm -f *.aux *.log *.pdf

.PHONY: all clean
