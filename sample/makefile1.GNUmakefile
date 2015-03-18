
# We will create variable to ease this process
# Variable storing the different compilers
LEX = flex
YACC = bison -d
CC = cc

# Create an object name "shell" from the folowing object files
shell: tokenizer.o parser.o
		$(CC) -o shell lex.yy.c parser.tab.c -ll -lm

lex.yy.o: lex.yy.c y.tab.h
lex.yy.o y.tab.o: parser.h

# The yacc file will generate 2files .h and .c files named y.tab.c and  y.tab.h
y.tab.c y.tab.h: parser.y
	$(YACC) -v parser.y

# The lex file will generate a .c file name lex.yy.c
lex.yy.c: tokenizer.l
	$(LEX) tokenizer.l


# This is just to remove the created file from the directories after execution
clean:
	-rm -f *.o lex.yy.c *.tab.*  shell *.output