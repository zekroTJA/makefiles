# Minimal Makefile for running and building
# angular applications.

#### EXECUTABLES ###########################
NG = ng
#### VARIABLES #############################
SERVE_PORT     	 = 8080
BASE_HREF_PROD 	 = "/"
BASE_HREF_TEST 	 = "/"
EXTRACT_CSS	   	 = true
OPTIMIZATION   	 = true
OUTPUT_PATH_PROD = "$(CURDIR)/dist/prod"
OUTPUT_PATH_TEST = "$(CURDIR)/dist/debug"
############################################

.PHONY: serve run build prod production help lint test

build:
	$(NG) build \
		--baseHref=$(BASE_HREF_TEST) \
		--outputPath=$(OUTPUT_PATH_TEST)

prod: 
	$(NG) build \
		--prod \
		--baseHref=$(BASE_HREF_PROD) \
		--extractCss=$(EXTRACT_CSS) \
		--optimization=$(OPTIMIZATION) \
		--outputPath=$(OUTPUT_PATH_PROD)


production: prod

serve:
	$(NG) serve --port="$(SERVE_PORT)"

run: serve

lint:
	$(NG) lint \
		--typeCheck=true

test:
	$(NG) test \
		--codeCoverage=true

help:
	@echo "Available recipes:"
	@echo "  build       Start debug build"
	@echo "  production  Start production build"
	@echo "  prod        [Alias for production]"
	@echo "  serve       Start live server"
	@echo "  run         [Alias for serve]"
	@echo "  lint        Start linter"
	@echo "  test        Start running tests"
