Comando tee
================================

1 O que ele faz?
------------------------------

Ele redireciona a saída padrão de um comando para um arquivo simultâneamente com a saída padrão no terminal. É largamente utilizado para mandar saídas para arquivos de log. Sua sintaxe segue o seguinte padrão

`tee [OPÇÕES]… [ARQUIVO]…`

```
-a, --append              anexa ao(s) ARQUIVO(s) fornecido(s) em vez de
                              sobrescrever
  -i, --ignore-interrupts   ignora os sinais de interrupção
  -p                        diagnostica erros ao tentar escrever para
                              não-redirecionamentos
      --output-error[=MODO] define o comportamento de erros de escrita;
                              veja MODO abaixo
      --help     mostra esta ajuda e sai
      --version  informa a versão e sai

O MODO determina o comportamento com erros de escrita nas saídas:
  'warn'         diagnostica erros de escrita para qualquer saída
  'warn-nopipe'  diagnostica erros de escrita para qualquer saída que
                   não seja redirecionamento
  'exit'         sai ao ocorrer um erro de escrita para qualquer saída
  'exit-nopipe'  sai ao ocorrer um erro de escrita para qualquer saída
                   que não seja redirecionamento
O MODO padrão para a opção -p é 'warn-nopipe'.
A operação padrão quando --output-error não está especificada é sair
imediatamente ao ocorrer um erro de escrita para um redirecionamento,
e diagnosticar erros ao escrever para saídas não redirecionamento.

```

Fonte
------------------------

* Página de ajuda do GNU coreutils: <https://www.gnu.org/software/coreutils/>

* Relate erros de tradução para <https://translationproject.org/team/pt_BR.html>

* Documentação completa em <https://www.gnu.org/software/coreutils/tee> ou disponível localmente via: info "(coreutils) tee invocation"
