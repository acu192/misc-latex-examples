
FIGURE_FILES = $(wildcard *.dot)
FIGURE_TARGETS = $(patsubst %.dot,%.eps,$(FIGURE_FILES))

TEX_FILES = $(wildcard *.tex)
TEX_TARGETS = $(patsubst %.tex,%.pdf,$(TEX_FILES))

all : $(FIGURE_TARGETS) $(TEX_TARGETS) auxClean

%.eps : %.dot
	@dot $^ -T eps -o $@

%.pdf : %.tex
	@latex $*
	@latex $*
	@dvipdf $*.dvi

auxClean :
	@rm -f \
		*.aux \
		*.bbl \
		*.blg \
		*.dvi \
		*.log \
		*.out

clean : auxClean
	@rm -f $(FIGURE_TARGETS)
	@rm -f $(TEX_TARGETS)

.PHONY : all auxClean clean
