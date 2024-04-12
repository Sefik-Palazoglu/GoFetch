CC=clang

SOURCES=$(wildcard ./*.c)
OBJECTS=$(patsubst %.c, %.o, $(SOURCES))

CFLAGS=-O2 -Wall -fPIC -g
LDFLAGS=-lm

all: $(OBJECTS)

%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -rf $(OBJECTS)
