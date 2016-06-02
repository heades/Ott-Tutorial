PDFLATEX=pdflatex
BIBTEX=bibtex
OTT = ott
OTT_FLAGS := -tex_wrap false -tex_show_meta true -picky_multiple_parses false
SKIM = skim_revert.sh

all : pdf
ifeq ($(SKIM), skim_revert.sh)
	$(SKIM) $(CURDIR)/note.pdf
	$(SKIM) $(CURDIR)/note.pdf
	$(SKIM) $(CURDIR)/note.pdf
endif

pdf : note.pdf

note-output.tex : note.tex Makefile F.ott
	$(OTT) $(OTT_FLAGS) -i F.ott  -o F-ott.tex \
		-tex_filter note.tex note-output.tex
note.pdf : note-output.tex 
	$(PDFLATEX) -jobname note note-output.tex

quick : note-output.tex 
	$(PDFLATEX) -jobname note note-output.tex

clean : 
	rm -f *.aux *.dvi *.ps *.log STLC-ott.tex note-output.tex *.bbl *.blg *~
