#make file needed for assignment

CC = gcc
CFLAGS = -ansi -Wall -g -O0 -Wwrite-strings -Wshadow -pedantic-errors -fstack-protector-all

PROGS = d8sh
all: $(PROGS)

clean: 
	rm -f *.o d8sh

d8sh: lexer.o parser.tab.o executor.o d8sh.o
	$(CC) -o d8sh lexer.o parser.tab.o executor.o d8sh.o -lreadline

lexer.o: lexer.c lexer.h
	$(CC) $(CFLAGS) -c lexer.c

parser.tab.o: parser.tab.c parser.tab.h command.h
	$(CC) $(CFLAGS) -c parser.tab.c

executor.o: executor.c executor.h command.h
	$(CC) $(CFLAGS) -c executor.c

d8sh.o: d8sh.c executor.h lexer.h
	$(CC) $(CFLAGS) -c d8sh.c 

