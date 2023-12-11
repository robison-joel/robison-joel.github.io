Comando uniq
===============

1 Utilização
----------------------

Filtra linhas correspondentes adjacentes da ENTRADA (ou entrada padrão), escrevendo para a SAÍDA (ou saída padrão).Ao não se informando nenhuma opção, linhas correspondentes são mescladas para a primeira ocorrência.

2 Sintaxe
----------------------

```uniq [OPÇÃO]... [ENTRADA [SAÍDA]]```

3 Argumentos e parâmetros
-----------------------------------

Argumentos obrigatórios para opções longas também o são para opções curtas.

* __-c, --count__ - prefixa as linhas com a quantidade de ocorrências
* __-d, --repeated__ - só emite as linhas duplicadas, um para cada grupo
* __-D__ - emite todas linhas duplicadas
* __--all-repeated[=MÉTODO]__ - similar a -D, mas permite grupos separados com uma linha vazia;
* __-f, --skip-fields=N__ - evita comparação entre os primeiros N campos
* __--group[=MÉTODO]__ - mostra todos itens, separando grupos com linha vazia;
* __-i, --ignore-case__ - ignora diferenças entre maiúsculo e minúsculo ao comparar.
* __-s, --skip-chars=N__ - evita comparação com os primeiros N caracteres
* __-u, --unique__ - emite apenas as linhas únicas
* __-z, --zero-terminated__ - termina linhas com byte 0, e não com nova linha
* __-w, --check-chars=N__ - compara no máximo N caracteres por linha
* __--help__ - mostra esta ajuda e sai
* __--version__ - informa a versão e sai

Um campo é uma sequencia de espaços-brancos (normalmente espaços e/ou tabulações) seguidos por caracteres que não sejam espaços-brancos. Os campos são ignorados antes de caracteres.

Nota: "uniq" não detecta linhas repetidas a menos que sejam adjacentes. Talvez você prefira ordenar a entrada primeiro, ou usar "sort -u" sem "uniq".

Fontes
----------------------

* Página de ajuda do GNU coreutils: <https://www.gnu.org/software/coreutils/>
* Relate erros de tradução para <https://translationproject.org/team/pt_BR.html>
* Documentação completa em <https://www.gnu.org/software/coreutils/uniq> ou disponível localmente via: info "(coreutils) uniq invocation"
