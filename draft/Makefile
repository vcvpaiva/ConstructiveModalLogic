PDFLATEX=pdflatex
SKIM = skim_revert.sh

all : pdf

ipad : all
	cp main.pdf ~/Dropbox/ConstructiveTemporalLogic-Draft.pdf

pdf : main.pdf
	$(SKIM) $(CURDIR)/main.pdf
	$(SKIM) $(CURDIR)/main.pdf

new : new.pdf
	$(SKIM) $(CURDIR)/new.pdf
	$(SKIM) $(CURDIR)/new.pdf

main.pdf : main.tex appA.tex appB.tex
	$(PDFLATEX) main.tex
	bibtex main
	$(PDFLATEX) main.tex
	$(PDFLATEX) main.tex
	$(PDFLATEX) main.tex

new.pdf : new.tex appA.tex appB.tex moncat.tex
	$(PDFLATEX) new.tex
	bibtex new
	$(PDFLATEX) new.tex
	$(PDFLATEX) new.tex
	$(PDFLATEX) new.tex

clean : 
	rm -f *.aux *.dvi *.ps *.log *.pdf *~ *.out *.bbl *.blg
