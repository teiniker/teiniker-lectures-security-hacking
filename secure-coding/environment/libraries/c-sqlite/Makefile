BJECTS =
CFLAGS = -std=c11 -g -Wall
LDLIBS = -lsqlite3
CC=gcc
UNITY=../../unity

all: test

init:
	mkdir -p build

unity.o: $(UNITY)/unity.c $(UNITY)/unity.h
	$(CC) $(CFLAGS) -c $(UNITY)/unity.c -o build/unity.o

test.o: test/sqlite_test.c
	$(CC) $(CFLAGS)  -I $(UNITY) -I include -c test/sqlite_test.c $(LDLIBS) -o build/sqlite_test.o

test: init unity.o test.o
	$(CC) $(CFLAGS)  build/unity.o build/sqlite_test.o $(LDLIBS) -o build/sqlite_test
	build/sqlite_test

clean:
	rm -rf build/

