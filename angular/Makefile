# Minimal Makefile for running and building
# angular applications.

#### EXECUTABLES ###########################
NG = ng
#### VARIABLES #############################
SERVE_PORT = 8080
############################################

.PHONY: serve run build prod production

build:
	$(NG) build

prod: 
	$(NG) build --prod

production: prod

serve:
	$(NG) serve $(SERVE_PORT)

run: serve
