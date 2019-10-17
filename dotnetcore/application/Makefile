# TEMPLATE MAKEFILE FOR .NET CORE APPLICATIONS
# https://github.com/zekroTJA/makefiles
#
# Covered by MIT License
#
# Copyright 2019 Ringo Hoffmann (zekro Development)
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

### NAMES AND LOCS ############################
MIGRATION = AppDbContext
# List of RIDs can be found here: 
# https://docs.microsoft.com/en-us/dotnet/core/rid-catalog
RID = linux-x64
###############################################

### EXECUTABLES ###############################
DOTNET = dotnet
###############################################

# ---------------------------------------------


PHONY = _make
_make: deps build cleanup

PHONY += deps
deps:
	$(DOTNET) restore

PHONY += build
build:
	$(DOTNET) build

PHONY += publish
publish:
	$(DOTNET) publish \
		-c Release \
		-r $(RID) \
		--self-contained true

PHONY += test
test:
	$(DOTNET) test

PHONY += run
run:
	$(DOTNET) run

PHONY += cleanup
cleanup:
	$(DOTNET) clean

PHONY += migrations
migrations:
	$(DOTNET) ef migrations add $(MIGRATION)

PHONY += help
help:
	@echo "Available targets:"
	@echo "  #          - creates binary .dll files"
	@echo "  cleanup    - cleans up bin and obj directories"
	@echo "  deps       - ensure dependencies are installed"
	@echo "  migrations - creates migrations using entity framework"
	@echo "  publish    - compiles to self contained binaries"
	@echo "  run        - compiles and runs the application"
	@echo "  test       - run tests"
	@echo ""


.PHONY: $(PHONY)
