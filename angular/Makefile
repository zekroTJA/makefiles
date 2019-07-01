# Minimal Makefile for running and building
# angular applications.


#### EXECUTABLES ###########################

NG       = ng
PRETTIER = prettier

#### VARIABLES #############################

# ng live server
SERVE_PORT     	 = 8080

# ng build
BASE_HREF_PROD 	 = "/"
BASE_HREF_TEST 	 = "/"
EXTRACT_CSS      = true
OPTIMIZATION   	 = true
OUTPUT_PATH_PROD = "$(CURDIR)/dist/prod"
OUTPUT_PATH_TEST = "$(CURDIR)/dist/debug"

# prettier
PRETTIER_CFG     = "$(CURDIR)/.prettierrc.yml"

############################################

.PHONY: serve run build prod production help lint test prettify

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

prettify:
	$(PRETTIER) \
		--config $(PRETTIER_CFG) \
		--write \
		src/**/*.ts

help:
	@printf "\nAvailable recipes:\n"
	@printf "  build       Start debug build\n"
	@printf "  production  Start production build\n"
	@printf "  serve       Start live server\n"
	@printf "  lint        Start linter\n"
	@printf "  test        Start running tests\n"
	@printf "  prettify    Prettify ts code with prettier\n"
	@printf "\nAliases:\n"
	@printf "  prod        -> production\n"
	@printf "  run         -> serve\n"
