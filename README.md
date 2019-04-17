# makefiles

Here, I collect some makefiles you can use for various languages and envoirements.

# Index

- **[go](go)**
  - [application](go/application)
  - [pakcage](go/package)
  
# Contribution

If you want, you are welcome to contribute your template makefiles or optimize existent makefiles.

Please keep in mind: The Makefile should be build as a template, so users can easily configure them to fit their needs.

In best case, create some variables at the top of the Makefile where the user can enter their own configuration andenvoirement preferences:

Example:
```Makefile
### NAMES AND LOCS ############################
APPNAME  = slms
PACKAGE  = github.com/zekroTJA/$(APPNAME)
LDPAKAGE = static
CONFIG   = $(CURDIR)/config/private.config.yml
###############################################

### EXECUTABLES ###############################
GO     = go
DEP    = dep
GOLINT = golint
GREP   = grep
###############################################

# ...
```
