(new) 
comecei o tutorial com o seguinte sequencia de viceos:
https://youtube.com/playlist?list=PLNmACol6lYY7Dzvg7jKgvMdDaDEDFnNqD&si=j_iaDGIB-5H0tWlU

(old)Ainda nao tenho nenhum tutorial a seguir. O principal objetivo deste repo é aprender a usar makefiles.


Chatgpt, voce mode dar uma introducao doque é o makefile? 
: 
Claro, vou fornecer uma breve introdução ao Makefile!
O que é um Makefile?

O Makefile é um arquivo de configuração usado para automatizar a compilação e a construção de projetos. Ele contém regras e dependências que ajudam a organizar e gerenciar o processo de construção.
Estrutura básica do Makefile:

Um Makefile geralmente consiste em regras, variáveis e comentários. Aqui está uma estrutura básica:

make

# Comentário

# Variáveis
CC = gcc
CFLAGS = -Wall

# Regra padrão (será executada se você apenas chamar 'make' no terminal)
all: meu_programa

# Regras de construção
meu_programa: arquivo1.o arquivo2.o
    $(CC) $(CFLAGS) -o meu_programa arquivo1.o arquivo2.o

arquivo1.o: arquivo1.c
    $(CC) $(CFLAGS) -c arquivo1.c

arquivo2.o: arquivo2.c
    $(CC) $(CFLAGS) -c arquivo2.c

# Regra para limpar arquivos temporários
clean:
    rm -f *.o meu_programa

Explicação:

    Comentários: Linhas que começam com # são comentários.

    Variáveis: São usadas para armazenar valores que serão usados mais tarde no arquivo. No exemplo, CC é o compilador e CFLAGS são as flags para o compilador.

    Regra padrão: Define o que será executado quando você apenas digitar make no terminal. Neste caso, será construído o programa meu_programa.

    Regras de construção: Especificam como os arquivos objeto e o programa final devem ser construídos. Cada regra segue um formato padrão. O alvo (o que será construído) e as dependências (o que é necessário para construir o alvo) são seguidos por um bloco de comandos que indicam como construir o alvo.

    clean: Uma regra especial para limpar (remover) arquivos temporários ou gerados durante a compilação.

Como usar:

Para construir o programa, basta executar make no terminal. Para limpar os arquivos temporários, você pode executar make clean.
Próximos Passos:

    Entender mais sobre Variáveis: Aprenda a usar e definir variáveis de maneira eficiente.

    Explorar Funções Internas: O Makefile possui várias funções internas úteis que podem simplificar suas regras.

    Gerenciar Dependências Automaticamente: O Makefile pode gerenciar dependências automaticamente, economizando esforços de manutenção.

    Estudo Avançado de Sintaxe: Existem muitas outras coisas que você pode fazer com Makefiles, como usar condicionais, loops, etc.

    Integração com Outras Ferramentas: Aprenda a integrar o Makefile com outras ferramentas ou sistemas de construção.

    Prática em Projetos Reais: Nada supera a prática. Tente criar e manter um Makefile para um projeto real.

Lembre-se, o Makefile é poderoso, mas também pode parecer complexo no início. À medida que você trabalha mais com ele, se tornará uma ferramenta valiosa para gerenciar projetos de software.

