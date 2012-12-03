
TEX_FILES = $(wildcard *.tex)
TARGETS = $(patsubst %.tex,%.pdf,$(TEX_FILES))

all : $(TARGETS) auxClean

%.dvi : %.tex
	@latex $*
	@bibtex $*
	@latex $*
	@latex $*

%.pdf : %.dvi
	@dvipdf $*

auxClean :
	@rm -f \
		*.aux \
		*.bbl \
		*.blg \
		*.dvi \
		*.log \
		*.out

clean : auxClean
	@rm -f $(TARGETS)

.PHONY : all auxClean clean
