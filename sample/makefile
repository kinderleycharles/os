
# We will create variable to ease this process
# Variable storing the different compilers
LEX = flex
YACC = bison -d
CC = cc

all: shell

# The yacc file will generate 2files .h and .c files named y.tab.c and  y.tab.h
parser.tab.c parser.tab.h: parser.y
	$(YACC) -v parser.y

# The lex file will generate a .c file name lex.yy.c
lex.yy.c: tokenizer.l
	$(LEX) tokenizer.l

shell: parser.tab.c lex.yy.c
	$(CC) lex.yy.c parser.tab.c -o shell
