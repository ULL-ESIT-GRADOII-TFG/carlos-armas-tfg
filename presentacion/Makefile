all:
	pdflatex presentacion_tfg.tex
	pdflatex presentacion_tfg.tex
	bibtex presentacion_tfg
	pdflatex presentacion_tfg.tex
	dvips -Ppdf -G0 -o presentacion_tfg.ps presentacion_tfg.dvi
	ps2pdf -sPAPERSIZE=a4 -DMaxSubsetPct=100 -dCompatibilityLevel=1.2 -dSubsetFonts=true -dEmbedAllFonts=true presentacion_tfg.ps presentacion_tfg.pdf

clean:
	rm -f *.log *.dvi *.aux *.blg *.ps *.nav *.out *.snm *.toc *.bbl

eps:
	convert  img/versioncontrol1.png img/versioncontrol1.eps

