PDFLATEX = pdflatex
BIBTEX = bibtex
OTT = ott
OTT_FLAGS := -tex_show_meta false
SKIM := skim_revert.sh
SKIMRevinPath := $(shell command -v $(SKIM) 2> /dev/null)

all: pdf
  # This is for my private machine.  It forces my PDF reader to reload.
  # It should not run unless "skim_revert.sh" is in your PATH.
  ifdef SKIMRevinPath	
	@$(SKIM) TCS4.pdf &>/dev/null
	@$(SKIM) TCS4.pdf &>/dev/null
	@$(SKIM) TCS4.pdf &>/dev/null
  endif

pdf : TCS4.pdf

main : TCS4.ott
	cd .. && Make

TCS4.tex : TCS4.ott
	$(OTT) $(OTT_FLAGS) -i TCS4.ott -o TCS4.tex

TCS4.pdf : TCS4.tex Makefile
	$(PDFLATEX) TCS4.tex

clean :
	rm -f *.aux *.dvi *.ps *.log *-ott.tex *-output.tex *.bbl *.blg *.rel *.pdf *~ *.vtc *.out *.spl *-inc.tex
