CC=clang

SOURCES=$(foreach D, ., $(wildcard $(D)/*.c))
OBJECTS=$(patsubst %.c, %.o, $(SOURCES))

CFLAGS=-O2 -Wall -fPIC -g
LDFLAGS=-lm

all: $(OBJECTS)

%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -rf $(OBJECTS)
