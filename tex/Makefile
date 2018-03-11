
TARGETS := $(patsubst %.tex,%.pdf,$(wildcard rules5.tex) $(wildcard paper.tex))

all: rules5.pdf paper.pdf
	echo $(TARGETS)

# Generalized rule: how to build a .pdf from each .tex
%.pdf: %.tex
	pdflatex -interaction nonstopmode $<

touch:
	touch *.tex

again: touch all

clean:
	rm -f *.aux *.log *.nav *.out *.snm *.toc *.vrb || true

veryclean: clean
	rm -f *.pdf

view: $(TARGETS)
	if [ "Darwin" = "$(shell uname)" ]; then open $(TARGETS) ; else evince $(TARGETS) ; fi

print: $(TARGETS)
	lpr $(TARGETS)

.PHONY: all again touch clean veryclean view print
