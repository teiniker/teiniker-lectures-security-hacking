
OBJECTS = 
CFLAGS = -std=c17 -g -Wall
LDLIBS = 
CC=gcc

all: build/struct 

init:
	mkdir -p build

build/struct: init struct.c
	$(CC) $(CFLAGS) $(LDLIBS) -o build/struct struct.c 
	build/struct 

clean:
	rm -rf build/
