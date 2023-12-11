LINUX - Permissões
=============================================================================================

Para saber os parâmetros de permissões de um arquivo ou diretório devemos devemos utilizar o comando:

`ls -la`

Abaixo um exemplo de saída do comando `la -la`. A primeira coluna mostra as permissões de acesso dos subdiretórios e arquivos

![Retorno do comando acima](pics/permissoes.png)

As informacoes de permissões aparecerão no inicio da linha como no exemplo a seguir:

```
usuario@userver:~$ ls -la
total 32
drwxr-xr-x 4 usuario grupo 4096 Jan 22 18:00 .
drwxr-xr-x 3 root root 4096 Jul 11  2022 ..
-rw------- 1 usuario grupo  112 Jan 17 23:11 .bash_history
-rw-r--r-- 1 usuario grupo  220 Feb 25  2020 .bash_logout
-rw-r--r-- 1 usuario grupo 3771 Feb 25  2020 .bashrc
drwx------ 2 usuario grupo 4096 Jul 11  2022 .cache
-rw-r--r-- 1 usuario grupo  807 Feb 25  2020 .profile
drwx------ 2 usuario grupo 4096 Jul 11  2022 .ssh
-rw-r--r-- 1 usuario grupo    0 Jul 11  2022 .sudo_as_admin_successful

```

O primeiro caractere diz qual é o tipo do objeto:

![Retorno do comando acima](pics/permissoes_primeiro.png)

* – para arquivo comum;
* b para dispositivos de bloco (oferecem grandes quantidades de dados de cada vez).
* c para dispositivo de caracteres (oferecem dados de um caractere de cada vez);
* d para diretório;
* l para link simbólico;
* p para FIFO ou Named Pipe;
* s para socket mapeado em arquivo;

Permissões de usuários
-------------------------------

Os três caracteres seguintes mostram as permissões do dono (permissão de leitura e escrita).

![Retorno do comando acima](pics/permissoes_usuarios.png)

Permissões para grupos
-------------------------------

O quinto, o sexto e o sétimo caracteres dizem quais as permissões do grupo (permissão de leitura e escrita).
Os três últimos caracteres especificam as permissões dos outros (permissão de leitura).

![Retorno do comando acima](pics/permissoes_grupo.png)

Permissões para outros
-------------------------------

Por sua vez, os últimos três caracteres (8º, 9º e 10º) são os que determinam as permissões para outros (que não são o usuário dono e o grupo corespondente.)

![Retorno do comando acima](pics/permissoes_outros.png)

Fontes
-------------------------------

* <https://canaltech.com.br/linux/entendendo-e-configurando-permissoes-de-arquivos-e-pastas-no-linux/>

* <https://guialinux.uniriotec.br/permissao-de-acesso/>
