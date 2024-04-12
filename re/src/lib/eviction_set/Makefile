CC=clang

SOURCES=$(foreach D, ., $(wildcard $(D)/*.c))
OBJECTS=$(patsubst %.c, %.o, $(SOURCES))

CFLAGS=-O2 -g -Wall -fPIC

all: $(OBJECTS)

%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -rf $(OBJECTS)
