.PHONY: arxiv
all:
	latexmk --pdf paper.tex
clean:
	rm -f *.aux *.bbl *.blg *.fdb_latexmk  *.fls *.log *.out *.maf *.mtc *.mtc0 *.toc *.thm *-eps-converted-to.pdf
diff:
	#git-latexdiff 6b4c16a8a9a53a818a474c3a6864453b7fdad0ce
	latexdiff paper_old.tex paper.tex > paper_diff.tex
	latexmk -interaction=nonstopmode --pdf paper_diff.tex;
arxiv:
	rm -rf arxiv
	mkdir -p arxiv/figures
	cp Makefile arxiv
	cp paper.tex arxiv
	cp paper.bbl arxiv
	cp references.bib arxiv
	cp siamart190516.cls arxiv
	cp siamplain.bst arxiv
	cp figures/*-table.txt arxiv/figures
	cp figures/complexity_plots.tex arxiv/figures
	cp figures/2d_unstructured.png arxiv/figures
	cp figures/*_star.png arxiv/figures
	cp *-eps-converted-to.pdf arxiv/figures
	rename 's/-eps-converted-to//' arxiv/figures/*
	tar -czvf arxiv.tar.gz arxiv
