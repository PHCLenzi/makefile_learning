

# $@ nome completo do objetivo desta regra
# $? dependências que são mais novas que o objetivo desta regra
# $* string que corresponde ao % no objetivo
# $< primeiro nome na lista de dependências
# $^ lista de todas as dependências, separadas por espaço

CC = gcc
CFLAGS = -Wall -O2

# cria essa depeendencia, que  usa em main.o, para ,qd criar strigs, ver se strings.h foi alterada. 
INCLUDEDIR = ./include

INCL = -I$(INCLUDEDIR)

DEPS = $(INCLUDEDIR)/strings.h

OBJ = main.o strings.o


strings: $(OBJ)
	$(CC) $(CFLAGS) -o strings main.o strings.o

%.o: %.c $(DEPS)
	$(CC) $(CFLAGS) -c -o $@ $< $(INCL)


clean:
	rm -f $(OBJ) core *~ $(INCL)/*~


