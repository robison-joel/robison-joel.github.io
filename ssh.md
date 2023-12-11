SSH
=============================================================

[Clique aqui](https://github.com/robison-joel/Codagem/tree/main/Shell/scripts/ssh) para o download do script de instalação do ssh.

1 O que é?
----------------------------------------------

Acrônimo de *Secure Socket Shell* É um protocolo de rede que permite acesso a um determinado sistema (Server ou PC), via shell.

2 Qual?
----------------------------------------------

O mais difundido e utilizado, no mundo linux, é o [OpenSSH](https://www.openssh.com/). E é sobre ele que vamos direcionar esse howto.

![Logo do OpenSSH](https://www.openssh.com/images/openssh.gif)

-------------------

3 Instalação
----------------------------------------------

**Antes de instalar, pense nisso:**

> Qual a minha finalidade para o uso do ssh?
O SSH permite conexões ssh entre um "client" e um "server". Se você queira **acessar o seu computador á partir de outro**, deve instalar ambos os pacotes. Caso queira **apenas acessar outro computador**, por motivos de segurança o mais recomendado é instalar somente o pacote "client".

### 3.1 Terminal

Abra uma sessão no terminal e digite:

#### No Ubuntu e derivados

`sudo apt-get install openssh-client openssh-server`

#### No ArchLinux e derivados

`pacman -S openssh`

Aperte ENTER e insira a sua senha de sudo. Espere a instalação acabar.

### 3.2. Pós-intalação

Para se certificar que foi instalado e que está rodando corretamente no seu sistema, use um esses dois comandos:

Para verificar o status do serviço SSH:

`service ssh status`  ou `service ssh status | grep Active`

Para iniciar o o servico SSH:

`service ssh start`

Para reiniciar o o servico SSH:

`service ssh restart`

Para parar o o servico SSH:

`service ssh stop`

4 Instruções para conexão
----------------------------------------------

### 4.1 Sintaxe:

Basicamente, a conexão ssh é feita, por escrito no shell, respeitando essa sintaxe:

`ssh user@servidor`

Onde:

* user = usuário real e habilitado á fazer login no sistema que está sendo acessado.

* servidor = IP ou dominio do computador que será acessado.

Após o request lhe será solicitado inserir a senha do usuário e...BINGO!

5Customização
----------------------------------------------

Para customizar o acesso ssh do seu servidor vocẽ deve editar dois arquivos distintos:

### 5.1  Edite o arquivo /etc/issue.net

O arquivo ***issue.net*** contém a mensagem que vai aprecer antes do usuário.

`sudo vim /etc/issue.net`

### 5.2 Edite o arquivo /etc/motd

O arquivo ***/etc/motd***, por sua vez, contém a mensagem que será exibida logo após a autenticação.

`sudo vim /etc/motd`

### 5.3 Habilítar os banners

Para habilitar os banners criados nos arquivos acima, vocẽ deve habilitá-los no arquivo ***/etc/ssh/sshd_conf***.

No arquivo , procure por uma linha que diz:

>__#Banner__

descomente e insira o nome do arquivo issue ao lado

>__Banner /etc/issue.net__

### 5.4 Reinicie o serviços

Reinicie o serviço ssh para que as aterações entrem em vigor.

`sudo service ssh restart`

Fntes
----------------------------------------------

* <https://pt.linkedin.com/pulse/mensagem-de-banner-em-servidores-linux-atrav%C3%A9s-do-ssh-marculino>

* <https://www.guiafoca.org/guiaonline/intermediario/ch27s29.html>

* <https://ivanix.wordpress.com/2008/12/04/arquivos-de-inicializacao-do-linux/>

* <https://gnulinuxbr.wordpress.com/2009/07/21/arquivos-etcissue-e-etcmotd/>

* <http://www.linhadecodigo.com.br/artigo/2974/dicas-avancadas-de-seguranca-para-ssh.aspx#ixzz7QaODMw7p>
