PDFLATEX=pdflatex
SKIM = skim_revert.sh
OTT := ott
OTT_FLAGS := -tex_wrap false -tex_show_meta true -picky_multiple_parses false

all : pdf

pdf : main.pdf
	$(SKIM) $(CURDIR)/main.pdf
	$(SKIM) $(CURDIR)/main.pdf

new : new.pdf
	$(SKIM) $(CURDIR)/new.pdf
	$(SKIM) $(CURDIR)/new.pdf

categorical-model-output.tex : categorical-model.tex ott/TCS4.ott
	$(OTT) $(OTT_FLAGS) -i ott/TCS4.ott -o TCS4-ott.tex -tex_name_prefix TLL \
		-tex_filter categorical-model.tex categorical-model-output.tex

proofs-output.tex : proofs.tex ott/TCS4.ott
	$(OTT) $(OTT_FLAGS) -i ott/TCS4.ott -o TCS4-ott.tex -tex_name_prefix TLL \
		-tex_filter proofs.tex proofs-output.tex

term-assignments-output.tex : term-assignments.tex ott/TCS4.ott
	$(OTT) $(OTT_FLAGS) -i ott/TCS4.ott -o TCS4-ott.tex -tex_name_prefix TLL \
		-tex_filter term-assignments.tex term-assignments-output.tex

main.pdf : main.tex appA.tex appB.tex term-assignments-output.tex proofs-output.tex ott/TCS4.ott categorical-model-output.tex
	$(PDFLATEX) main.tex
	bibtex main
	$(PDFLATEX) main.tex
	$(PDFLATEX) main.tex
	$(PDFLATEX) main.tex

clean : 
	rm -f *.aux *.dvi *.ps *.log *~ *.out *.bbl *.blg
