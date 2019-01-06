\
FILES = fact.c  fib.c

ASMS = $(FILES:.c=.s) 
OBJS = $(FILES:.c=.o) 
LD = ld -g  -melf_i386 
BINARIES = fact fib

all : $(BINARIES)
asm: $(ASMS)


fib: fib.c
	gcc -m32 -g -o fib  fib.c 
fact: fact.c
	gcc -m32 -g  -o fact  fact.c 


%.s : %.c
#	$(warning NASM=$(NASM) FLAGS=$(ASM_FLAGS))
	gcc  -O2 -m32 -masm=intel -g -S -o $@ $<
	gcc  -O2 -m32 -masm=intel -g -Wa,-adhln -c $< > $@.lst
clean: 
	rm -f $(OBJS) $(BINARIES) $(ASMS)
	rm -f *~ *.lst
