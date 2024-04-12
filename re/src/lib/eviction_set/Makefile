CC=clang

SOURCES=$(wildcard ./*.c)
INCDIRS=.
OBJECTS=$(patsubst %.c, %.o, $(SOURCES))
DEPFILES=$(patsubst %.c, %.d, $(SOURCES))

DEPFLAGS=-MP -MD
CFLAGS=-O2 -Wall -fPIC -g $(foreach D,$(INCDIRS),-I$(D)) $(DEPFLAGS)

all: $(OBJECTS)

%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -rf $(OBJECTS) $(DEPFILES)

-include $(DEPFILES)
