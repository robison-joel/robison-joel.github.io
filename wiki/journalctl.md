Journalctl
============================================================

Programa para visualizar os logs do linux.

1 Sintaxe
-----------------------------------------------------------

`journalctl [parâmetros]`

1.1 Parâmetros

* `--since ou --until "*tempo*"`
  * datas em padrão internacional: aaaa-mm-dd
  * expressões: 2 hours ago
* `-k`: Somente mensagens do Kernel.
* `-u`: *service*: exibe logs de um service.
* `-f`: fixa nos logs da instrução anterior, tal como o tail -f.
* `-n`: *x*: imprime na tela as últimas x linhas do log.
* `-r`: troca a ordem dos logs posicionando nos mais recentes.
* `-o`: *formato*: Exibe os resultados em um formato especifico, deteminado em *formato*.
* `-p`: *"prioridade"*: exibe logs de uma determinada prioridade.
* `_UID=*uiddeusuario*`: Exibe logs exclusivamente deste usuario, correspondente ao uid.
  * para descobrir o uid de um usuario: `id usuario`

Fonte
-----------------------------------------------------------

* Linux Tips: <https://www.youtube.com/watch?v=jT9yjpUYB-Y>
