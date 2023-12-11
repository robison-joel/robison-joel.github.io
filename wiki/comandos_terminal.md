
COMANDOS TERMINAL
============

1 Comandos B&aacute;sicos
--------------------------------------------

* `ls` - Lista todos os arquivos do diretório

* `df` - Mostra a quantidade de espaço usada no disco rígido

* `top` - Mostra o uso da memória

* `cd` - Acessa uma determinada pasta (diretório)

* `mkdir` - Cria um diretório

* `rm` - Remove um arquivo/diretório

* `cat` - Abre um arquivo

* `vi` - Abre o editor vi (l&ecirc;-se viai) para editar/criar arquivos

* `echo Data: "$(date "+%d"/"%m"/"%Y")"` - Imprime Data no terminal.

* `echo Hora: "$(date "+%H":"%m")"` - Imprime a hora no terminal

2 Comandos de Controle e Acesso
--------------------------------------------

* `exit` - Terminar a sessão, ou seja, a shell (mais ajuda digitando man sh ou man csh)

* `logout` - Des-logar, ou seja, terminar a sessão atual, mas apenas na C shell e na bash shell.

* `passwd` - Mudar a password do nosso utilizador (usu&aacute;rio logado).

* `rlogin` - Logar de forma segura em outro sistema Unix/Linux.

* `ssh` - Sessão segura, vem de secure shell, e permite-nos logar num servidor remoto através do protocolo ssh.

* `slogin` - Versão segura do rlogin.

* `yppasswd` - Mudar a password do nosso utilizador nas p&aacute;ginas amarelas (yellow pages).

3 Comandos de Comunica&ccedil;&otilde;es
--------------------------------------------

* `mail` - Enviar e receber emails
* `mesg` - Permitir ou negar mensagens de terminal e pedidos de conversa&ccedil;&atilde;o (talk requests)
* `pine` - Outra forma de enviar e receber emails, uma ferramenta r&aacute;pida e pr&aacute;tica
* `talk` - Falar com outros utilizadores que estejam logados no momento
* `write` - Escrever para outros utilizadores que estejam logados no momento

4 Comandos de Ajuda e Documenta&ccedil;&atilde;o
--------------------------------------------

* `apropos` - Localiza comandos por pesquisa de palavra-chave
* `find` - Localizar arquivos, como por exemplo: find . -name *.txt -print, para pesquisa de arquivos de texto do diret&oacute;rio atual
* `info` - Abre o explorador de informa&ccedil;&otilde;es
* `man` - Manual muito completo, pesquisa informa&ccedil;&atilde;o acerca de todos os comandos que necessitemos de saber, como por exemplo man find
* `whatis` - Descreve o que um determinado comando &eacute;/faz
* `whereis` - Localizar a p&aacute;gina de ajuda (man page), c&oacute;digo fonte, ou arquivos bin&aacute;rios, de um determinado programa

5 Comandos de Edi&ccedil;&atilde;o de Texto
--------------------------------------------

* `emacs` - Editor de texto screen-oriented.
* `pico` - Editor de texto screen-oriented, tamb&eacute;m chamado de nano.
* `sed` - Editor de texto stream-oriented.
* `vi` - Editor de texto full-screen.
* `vim` - Editor de texto full-screen melhorado (vi improved).

6 Comandos de Gest&atilde;o de Arquivos e Direct&oacute;rios
--------------------------------------------

* `cd` - Mudar de diret&oacute;rio atual, como por exemplo cd diret&oacute;rio, cd .., cd /
* `chmod` - Mudar a prote&ccedil;&atilde;o de um arquivo ou diret&oacute;rio, como por exemplo chmod 777, parecido com o attrib do MS-DOS
* `chown` - Mudar o dono ou grupo de um arquivo ou diret&oacute;rio, vem de change owner
* `chgrp` - Mudar o grupo de um arquivo ou diret&oacute;rio
* `cmp` - Compara dois arquivos
* `comm` - Seleciona ou rejeita linhas comuns a dois arquivos selecionados
* `cp` - Copia arquivos, como o copy do MS-DOS
* `crypt` - Encripta ou Descripta arquivos (apenas CCWF)
* `diff` - Compara o conte&uacute;do de dois arquivos ASC&Iacute;&Iacute;
* `file` - Determina o tipo de arquivo
* `grep` - Procura um arquivo por um padr&atilde;o, sendo um filtro muito &uacute;til e usado, por exemplo um cat a.txt | grep ola ir&aacute; mostrar-nos apenas as linhas do arquivo a.txt que contenham a palavra “ola”
* `gzip` - Comprime ou expande arquivo
* `ln` - Cria um link a um arquivo
* `ls` - Lista o conte&uacute;do de uma diret&oacute;rio, semelhante ao comando dir no MS-DOS
* `lsof` - Lista os arquivos abertos, vem de list open files
* `mkdir` - Cria uma diret&oacute;rio, vem de make directory”
* `mv` - Move ou renomeia arquivos ou diret&oacute;rios
* `pwd` - Mostra-nos o caminho por inteiro da diret&oacute;rio em que nos encontramos em dado momento, ou seja um pathname
* `quota` - Mostra-nos o uso do disco e os limites
* `rm` - Apaga arquivos, vem de remove, e &eacute; semelhante ao comando del no MS-DOS, &eacute; preciso ter cuidado com o comando rm * pois apaga tudo sem confirma&ccedil;&atilde;o por defeito
* `rmdir` - Apaga diret&oacute;rio, vem de remove directory
* `stat` - Mostra o estado de um arquivo, &uacute;til para saber por exemplo a hora e data do &uacute;ltimo acesso ao mesmo
* `sync` - Faz um flush aos buffers do sistema de arquivos, sincroniza os dados no disco com a mem&oacute;ria, ou seja escreve todos os dados presentes nos buffers da mem&oacute;ria para o disco
* `sort` - Ordena, une ou compara texto, podendo ser usado para extrair informa&ccedil;&otilde;es dos arquivos de texto ou mesmo para ordenar dados de outros comandos como por exemplo listar arquivos ordenados pelo nome
* `tar` - Cria ou extrai arquivos, muito usado como programa de backup ou compress&atilde;o de arquivos
* `tee` - Copia o input para um standard output e outros arquivos
* `tr` - Traduz caracteres
* `umask` - Muda as prote&ccedil;&otilde;es de arquivos
* `uncompress` - Restaura um arquivo comprimido
* `uniq` - Reporta ou apaga linhas repetidas num arquivo
* `wc` - Conta linhas, palavras e mesmo caracteres num arquivo

7 Comandos de Exibi&ccedil;&atilde;o ou Impress&atilde;o de Arquivos
--------------------------------------------

* `cat` - Mostra o conte&uacute;do de um arquivo, como o comando type do MD-DOS, e &eacute; muito usado tamb&eacute;m para concatenar arquivos, como por exemplo fazendo cat a.txt b.txt > c.txt” para juntar o arquivo a.txtb.txt num &uacute;nico de nome c.txt
* `fold` - Encurta, ou seja, faz um fold das linhas longas para caberem no dispositivo de output
* `head` - Mostra as primeiras linhas de um arquivo, como por exemplo com head -10 a.txt, ou usado como filtro para mostrar apenas os primeiros x resultados de outro comando
* `lpq` - Examina a spooling queue da impressora
* `lpr` - &Iacute;mprime um arquivo
* `lprm` - Remove jobs da spooling queue da impressora
* `more` - Mostra o conte&uacute;do de um arquivo, mas apenas um ecr&atilde; de cada vez, ou mesmo output de outros comandos, como por exemplo ls | more
* `less` - Funciona como o more, mas com menos features, menos caracter&iacute;sticas e potenciais usos
* `page` - Funciona de forma parecida com o comando more, mas exibe os ecr&atilde;s de forma invertida ao comando more
* `pr` - Pagina um arquivo para posterior impress&atilde;o
* `tail` - Funciona de forma inversa ao comando head, mostra-nos as &uacute;ltimas linhas de um arquivo ou mesmo do output de outro comando, quando usado como filtro
* `zcat` - Mostra-nos um arquivo comprimido
* `xv` - Serve para exibir, imprimir ou mesmo manipular imagens
* `gv` - Exibe arquivos ps e pdf
* `xpdf` - Exibe arquivos pdf, usa o gv

8 Comandos de Transfer&ecirc;ncia de Arquivos
--------------------------------------------

* `ftp` - Vem de file transfer protocol, e permite-nos, usando o protocolo de transfer&ecirc;ncia de arquivos ftp, transferir arquivos entre v&aacute;rios hosts de uma rede, como a um servidor de ftp para enviar ou puxar arquivos
* `rsync` - Sincroniza de forma r&aacute;pida e flex&iacute;vel dados entre dois computadores
* `scp` - Vers&atilde;o segura do rcp

9 Comandos de Not&iacute;cias ou Rede
--------------------------------------------

* `hostname` - Exibir o nome do sistema.
* `hostname -f` - Exibir o FQDN no computador.
* `cat /etc/hostname` ou `cat /proc/sys/kernel/hostname` - Exibir o hostname do computador.
* `netstat` - Mostra o estado da rede
* `rsh` - Um shell em outros sistemas UN&Iacute;X
* `ssh` - Vers&atilde;o segura do rsh
* `nmap` - Poderoso port-scan, para visualizarmos portas abertas num dado host
* `ifconfig` - Visualizar os ips da nossa m&aacute;quina, entre outras fun&ccedil;&otilde;es relacionadas com ips
* `ping` - Pingar um determinado host, ou seja, enviar pacotes icmp para um determinado host e medir tempos de resposta, entre outras coisas

10 Comandos de Controle de Processos
--------------------------------------------

* `kill` - Mata um processo, como por exemplo kill -kill 100 ou kill -9 100 ou kill -9 %1
* `bg` - Coloca um processo suspenso em background
* `fg` - Ao contr&aacute;rio do comando bg, o fg traz de volta um processo ao foreground
* `jobs` - Permite-nos visualizar jobs em execu&ccedil;&atilde;o, quando corremos uma aplica&ccedil;&atilde;o em background, poderemos ver esse job com este comando, e termina-lo com um comando kill -9 %1, se for o jobn&uacute;mero 1, por exemplo
* `top` - Lista os processos que mais cpu usam, &uacute;til para verificar que processos est&atilde;o a provocar um uso excessivo de mem&oacute;ria, e quanta percentagem decpu cada um usa em dado momento
* `^y` - Suspende o processo no pr&oacute;ximo pedido de input
* `^z` - Suspende o processo actual

11 Comandos de &Iacute;nforma&ccedil;&atilde;o de Estado
--------------------------------------------

* `clock` - Define a hora do processador
* `date` - Exibe a data e hora
* `df` - Exibe um resumo do espa&ccedil;o livre em disco
* `du` - Exibe um resumo do uso do espa&ccedil;o em disco
* `env` - Exibe as vari&aacute;veis de ambiente
* `finger` - Pesquisa informa&ccedil;&otilde;es de utilizadores
* `history` - Lista os &uacute;ltimos comandos usados, muito &uacute;til para lembrar tamb&eacute;m de que comandos foram usados para fazer determinada ac&ccedil;&atilde;o no passado ou o que foi feito em dada altura
* `last` - &Iacute;ndica o &uacute;ltimo login de utilizadores
* `lpq` - Examina a spool queue
* `manpath` - Mostra a path de procura para as p&aacute;ginas do comando man
* `printenv` - &Iacute;mprime as vari&aacute;veis de ambiente
* `ps` - Lista a lista de processos em execu&ccedil;&atilde;o, &uacute;til para saber o pid de um processo para o mandar abaixo com o comando kill, entre outras coisas
* `pwd` - Mostra-nos o caminho por inteiro do diret&oacute;rio em que nos encontramos em dado momento, ou seja um pathname
* `set` - Define vari&aacute;veis da sess&atilde;o, ou seja, da shell, na C shell, na bash ou na ksh
* `spend` - Lista os custos AC&Iacute;TS UN&Iacute;X at&eacute; à data
* `time` -Mede o tempo de execu&ccedil;&atilde;o de programas
* `uptime` - Diz-nos h&aacute; quanto tempo o sistema est&aacute; funcional, quando foi ligado e o seu uptime
* `w` - Mostra-nos quem est&aacute; no sistema ou que comando cada job est&aacute; a executar
* `who` - Mostra-nos quem est&aacute; logado no sistema
* `whois` - Servi&ccedil;o de diret&oacute;rio de dom&iacute;nios da &Iacute;nternet, permite-nos saber informa&ccedil;&otilde;es sobre determinados dom&iacute;nios na &Iacute;nternet, quando um dom&iacute;nio foi registado, quando expira, etc
* `whoami` - Diz-nos quem &eacute; o dono da shell

12 Comandos de Processamento de Texto
--------------------------------------------

* `abiword` - Processador de Texto Open Source
* `addbib` - Cria ou modifica bases de dados bibliogr&aacute;ficas
* `col` - Reverte o filtro a line feeds
* `diction` - &Iacute;dentifica senten&ccedil;as com palavras
* `diffmk` - Marca diferen&ccedil;as entre arquivos
* `dvips` - Converte arquivos TeX DV&Iacute; em arquivos PostScript
* `explain` - Explica frases encontradas pelo programa diction
* `grap` - Preprocessador pic para desenhar gr&aacute;ficos, usado em tarefas elementares de an&aacute;lises de dados
* `hyphen` - Encontra palavras com h&iacute;fens
* `ispell` - Verifica a ortografia de forma interativa
* `latex` - Formata texto em LaTeX, que &eacute; baseado no TeX
* `pdfelatex` - Para documentos LaTeX em formato pdf
* `latex2html` - Converter LaTeX para html
* `lookbib` - Encontra refer&ecirc;ncias bibliogr&aacute;ficas
* `macref` - Cria uma refer&ecirc;ncia cruzada listando arquivos de macros nroff/troff
* `ndx` - Cria uma p&aacute;gina de indexa&ccedil;&atilde;o para um documento
* `neqn` - Formata matem&aacute;ticas com nroff
* `nroff` - Formata texto para exibi&ccedil;&atilde;o simples
* `pic` - Produz simples imagens para troff input
* `psdit` - Filtra um output troff para a Apple LaserWriter
* `ptx` - Cria uma indexa&ccedil;&atilde;o permutada mas n&atilde;o em CCWF
* `refer` - &Iacute;nsere refer&ecirc;ncias de bases de dados bibliogr&aacute;ficas
* `roffbib` - Faz o run off de uma base de dados bibliogr&aacute;fica
* `sortbib` - Ordena uma base de dados bibliogr&aacute;fica
* `spell` - Encontra erros de ortografia
* `style` - Analisa as caracter&iacute;sticas superficiais de um documento
* `tbl` - Formata tabelas para nroff/troff
* `tex` - Formata texto
* `tpic` - Converte arquivos pic source em comandos TeX
* `wget` - Permite-nos fazer o download completo de p&aacute;ginas web, com todos os arquivos, de forma f&aacute;cil e n&atilde;o interactiva, sem exigir por isso presen&ccedil;a do utilizador, respeitando tamb&eacute;m o arquivorobots.txt

13 Comandos Web
--------------------------------------------

* `html2ps` - Conversor de html para ps
* `latex2html` - Conversor de LaTeX para html
* `lynx` - Navegador web baseado em modo de texto, ou seja, &eacute; um web browser que nos permite abrir todo o tipo de p&aacute;ginas visualizando apenas os textos elinks, n&atilde;o vendo assim as imagens, e sendo por isso bastante r&aacute;pido, mas requere pr&aacute;tica para ser manuseado
* `netscape` - Navegador web da Netscape
* `sitecopy` - Aplica&ccedil;&atilde;o que nos permite manter f&aacute;cil e remotamente web sites
* `weblint` - Verificador de sintaxes e de estilos html

14 Comandos para manipular pacotes ".deb"
--------------------------------------------

* `dpkg -i nomedoarquivo.deb` - Instalar pacotes ".deb"
* `dpkg-reconfigure nomedoarquivo.deb` - Reconfigurar pacotes ".deb" instalados.
* `dpkg -l search_pattern` - Listar pacotes instalados.
