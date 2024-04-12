CC=clang
CFLAGS:= -O2 -Wall -fPIC -g

BASIC_DIR=./lib/basics
EVSET_DIR=./lib/eviction_set

SUBDIRS=$(BASIC_DIR) $(EVSET_DIR)

BUILD_SUBDIRS=$(SUBDIRS:%=build-%)
CLEAN_SUBDIRS=$(SUBDIRS:%=clean-%)

EXECS=$(wildcard ./*.out)
ASMS=$(wildcard ./*.s)
LDFLAGS=-lm

all: evset_gen.out no_deref.out aop_stream.out \
	addr_sweep.out l2l1_fetch.out quick_check.out

profile: evset_gen.out

noderef: no_deref.out

aopstream: aop_stream.out

4gb: addr_sweep.out

l2l1: l2l1_fetch.out

quick: quick_check.out

%.out: %.o $(BUILD_SUBDIRS)
	$(CC) $(LDFLAGS) -o $@ $< $(foreach D, $(BUILD_SUBDIRS:build-%=%), $(wildcard $(D)/*.o))

%.o: %.c
	$(CC) $(CFLAGS) $^ -c -o $@

$(BUILD_SUBDIRS):
	$(MAKE) -C $(@:build-%=%)

clean: $(CLEAN_SUBDIRS)
	rm -rf $(EXECS) $(ASMS)

$(CLEAN_SUBDIRS):
	$(MAKE) clean -C $(@:clean-%=%)





