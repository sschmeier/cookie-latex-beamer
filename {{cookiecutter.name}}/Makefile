filenamebase=presentation

# list all rules/targets
.PHONY: list
list:
	@$(MAKE) -pRrq -f $(lastword $(MAKEFILE_LIST)) : 2>/dev/null | awk -v RS= -F: '/^# File/,/^# Finished Make data base/ {if ($$1 !~ "^[#.]") {print $$1}}' | sort | egrep -v -e '^[^[:alnum:]]' -e '^$@$$'

.PHONY: help
help:
	@echo "   pdf         Create pdf via latexmk"
	@echo "   pdfview     Create pdf via latexmk and watch for changes"
	@echo "   evince      Open pdf via evince"
	@echo "   prev        Open pdf via Preview"
	@echo "   clean       Remove unwnated stuff from docs"

.PHONY: pdf
pdf:
	latexmk -pdflua ${filenamebase}.tex

.PHONY: pdfview
pdfview:
	latexmk -pdflua -pvc ${filenamebase}.tex

.PHONY: evince
evince:
	evince ${filenamebase}.pdf &

.PHONY: prev
prev:
	open -a Preview ${filenamebase}.pdf &

.PHONY: clean
clean:
	rm -f ${filenamebase}.{ps,pdf,log,aux,out,dvi,bbl,blg,snm,toc,nav,vrb}; latexmk -C
