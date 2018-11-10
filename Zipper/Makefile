NAME ?= GenomKernel


DATE := $(shell date "+%Y%m%d-%I%M")

CODE := MIUI

ZIP := $(NAME)-$(CODE)-$(DATE).zip
CZIP := $(NAME)-$(CODE)-Clang-$(DATE).zip

EXCLUDE := Makefile *.git* *.jar* Dark-Ages* *placeholder*

normal: $(ZIP)
nclang: $(CZIP)

$(ZIP):
	@echo "Creating ZIP: $(ZIP)"
	@zip -r9 "$@" . -x $(EXCLUDE)
	@echo "Generating SHA1..."
	@sha1sum "$@" > "$@.sha1"
	@cat "$@.sha1"
	@echo "Done."

$(CZIP):
	@echo "Creating ZIP: $(CZIP)"
	@zip -r9 "$@" . -x $(EXCLUDE)
	@echo "Generating SHA1..."
	@sha1sum "$@" > "$@.sha1"
	@cat "$@.sha1"
	@echo "Done."


clean:
	@rm -vf "$(NAME)-"*.zip*
	@rm -vf kernel/Image.gz
	@rm -vf kernel/normal/msm8953-qrd-sku3-e7.dtb
	@echo "Done."


