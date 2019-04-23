### EXECUTABLES ##############################
CC = g++
##############################################

### DIRS AND FILE NAMES ######################
SRCEXT   = cpp
SRCDIR   = src
BUILDDIR = build
TARGET   = bin/fw
##############################################

### ARGS #####################################
INCLUDE  = -Iinclude/ -Ilib/yaml-cpp/include
CFLAGS   = -g --std=c++17
RUNARGS  = -c config/config.yml
##############################################


SRCS   = $(wildcard src/*.$(SRCEXT)) \
		 $(wildcard lib/yaml-cpp/src/*.$(SRCEXT))
OBJS   = $(SRCS:%.$(SRCEXT)=$(BUILDDIR)/%.o)

ifeq ($(OS),Windows_NT)
	TARGET := $(TARGET).exe
endif


all: $(TARGET)

$(BUILDDIR)/%.o: %.$(SRCEXT)
	mkdir -p $(@D)
	$(CC) $(CFLAGS) $(INCLUDE) -o $@ -c $<

$(TARGET): $(OBJS)
	mkdir -p $(@D)
	$(CC) $(CFLAGS) $(INCLUDE) -o $(TARGET) $(OBJS)

run: $(TARGET)
	@echo ----------------------
	@./$(TARGET) $(RUNARGS)

clean-all:
	rm -r -f build/*
	rm -r -f bin/*

clean:
	rm -r -f build/src/*


help:
	@echo "Available targets:"
	@echo "  #         - creates binary in ./bin"
	@echo "  all       - creates objects and linked binary"
	@echo "  clean     - cleans application source objects"
	@echo "  clean-all - cleans all binaries"
	@echo "  run       - compiles binaries and run"
	@echo ""

.PHONY: all clean clean-all run help
