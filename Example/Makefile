MOVE=\mv
REMOVE=\rm -f 

all	: pdfdoc-a4.pdf pdfdoc-screen.pdf

pdfdoc-a4.pdf	: pdfdoc.tex pdfdoc.bib pdfdoc.sty
		echo "\onlinefalse" > switch.tex
		pdflatex pdfdoc
		bibtex pdfdoc
		makeindex pdfdoc.idx
		pdflatex pdfdoc
		pdflatex pdfdoc
		$(MOVE) pdfdoc.pdf pdfdoc-a4.pdf

pdfdoc-screen.pdf	: pdfdoc.tex pdfdoc.bib pdfdoc.sty
		echo "\onlinetrue" > switch.tex
		pdflatex pdfdoc
		bibtex pdfdoc
		makeindex pdfdoc.idx
		pdflatex pdfdoc
		pdflatex pdfdoc
		$(MOVE) pdfdoc.pdf pdfdoc-screen.pdf

clean	:
	$(REMOVE) pdfdoc.{aux,bbl,blg,brf,idx,ilg,ind,log,out,toc}
	$(REMOVE) pdfdoc-a4.pdf
	$(REMOVE) pdfdoc-screen.pdf
	$(REMOVE) switch.tex
