OS := $(shell uname)
SOURCEPATH=.
CC=gcc
CFLAGS=-O2 -Wall 
OSFLAGS= -DOS=$OS
SOURCES=$(SOURCEPATH)/pirate-loader.c

ifeq ($(OS),Linux)
SUFFIX=lnx
endif
ifeq ($(OS),Darwin)
SUFFIX=mac
CFLAGS=-O2 -Wall -force_cpusubtype_ALL -arch i386 -arch x86_64
endif
ifeq ($(OS),FreeBSD)
SUFFIX=fbsd
endif

all: pirate-loader

pirate-loader: $(SOURCES)
	$(CC) $(CFLAGS) $(<) $(OSFLAGS) -o $(@)_${SUFFIX}

.PHONY: clean

clean:
	rm -f *.o *~ core
