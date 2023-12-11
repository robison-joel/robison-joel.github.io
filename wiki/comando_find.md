Comando FIND
======================

1 Sintaxe
------------------------------------

Esta é uma sintaxe básica.

`find [local] [opções] [busca]`

Onde:

* [local]: representa o local onde será procurado. O caminho padrão é o diretório atual (recomenda-se utilizar o caminho absoluto);
* [busca]: trata-se do  arquivo ou pasta que vai ser procurado (recomenda-se escrever com aspas);
* [opções]: As opções encontramos nas instruçoes abaixo

2 Manpage (--help)
----------------------------------------

```
Usage: find [-H] [-L] [-P] [-Olevel] [-D debugopts] [path...] [expression]

o caminho padrão é o diretório atual; a expressão padrão é -print
expressões podem consistir de:
operadores, opções, testes e ações:
operadores (precedência decrescente; -and é implícito quando nenhum outro é especificado):
      ( EXPR ) ! EXPR -not EXPR EXPR1 -a EXPR2 EXPR1 -and EXPR2
      EXPR1 -o EXPR2 EXPR1 -or EXPR2 EXPR1, EXPR2
opções posicionais (sempre verdadeiras): -daystart -follow -regextype

opções normais (sempre verdadeiras, especificadas antes de outras expressões):
      -depth --help -maxdepth NÍVEIS -mindepth NÍVEIS -mount -noleaf
      --version -xdev -ignore_readdir_race -noignore_readdir_race
testa (N pode ser +N ou -N ou N): -admin N -anewer ARQUIVO -atime N -cmin N
      -cnewer ARQUIVO -ctime N -empty -false -fstype TIPO -gid N -group NOME
      -ilname PADRÃO -iname PADRÃO -inum N -iwholename PADRÃO -iregex PADRÃO
      -links N -lname PADRÃO -mmin N -mtime N -name PADRÃO -newer ARQUIVO
      -nouser -nogroup -path PATTERN -perm [-/]MODE -regex PATTERN
      -readable -writable -executable
      -wholename PATTERN -size N[bcwkMG] -true -type [bcdpflsD] -uid N
      -used N -user NAME -xtype [bcdpfls]      -context CONTEXTO

actions: -delete -print0 -printf FORMAT -fprintf FILE FORMAT -print 
      -fprint0 FILE -fprint FILE -ls -fls FILE -prune -quit
      -exec COMMAND ; -exec COMMAND {} + -ok COMMAND ;
      -execdir COMMAND ; -execdir COMMAND {} + -okdir COMMAND ;

Valid arguments for -D:
exec, opt, rates, search, stat, time, tree, all, help
Use '-D help' for a description of the options, or see find(1)

Please see also the documentation at https://www.gnu.org/software/findutils/.
You can report (and track progress on fixing) bugs in the "find"
program via the GNU findutils bug-reporting page at
https://savannah.gnu.org/bugs/?group=findutils or, if
you have no web access, by sending email to <bug-findutils@gnu.org>.
```

Fontes
------------------------------------------------

* <https://www.hostinger.com.br/tutoriais/find-locate-comandos-linux?ppc_campaign=google_performance_max&gclid=CjwKCAjw46CVBhB1EiwAgy6M4jznTzEVayT_kpQs-vOfpajQol3wXnJyscT0ACHTLPoun_J-J0HWahoC6nYQAvD_BwE>
