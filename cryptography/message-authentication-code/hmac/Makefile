CC=gcc
UTILS=../../utils
CFLAGS=-std=c17 -g -Wall
INCLUDES=-I/usr/include/openssl/ -I$(UTILS)/
LIBS=-L/usr/lib/x86_64-linux-gnu/ -lcrypto

all: init run

init:
	mkdir -p build

build/hex.o: $(UTILS)/encoding/hex.h $(UTILS)/encoding/hex.c
	$(CC) $(CFLAGS) $(INCLUDES) -c $(UTILS)/encoding/hex.c -o build/hex.o

build/hmac.o: hmac.c
	$(CC) $(CFLAGS) $(INCLUDES) -c hmac.c -o build/hmac.o

build/hmac: build/hex.o build/hmac.o 
	$(CC) $(CFLAGS) build/hmac.o build/hex.o -o build/hmac $(LIBS)

run: build/hmac 
	build/hmac

clean:
	rm -rf build/
