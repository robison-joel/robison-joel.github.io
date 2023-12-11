Samba share
=========================================================================================

## 1 Instalação

[Clique aqui](https://github.com/robison-joel/Codagem/tree/main/Shell/scripts/samba) para o download do script de instalação do samba.

Para instalar o Samba basta rodar um *sudo apt install*. Abaixo, o comando que instala o samba juntamente com alguns adicionais.

`sudo apt install samba -y`

`sudo apt install samba-common -y`

`sudo apt install samba-testsuite -y`

`sudo apt install samba-vfs-modules -y`

`sudo apt install fuse -y`

`sudo apt install fuse-emulator-gtk -y`

`sudo apt install fuse-emulator-utils -y`

`sudo apt install fusefat -y`

`sudo apt install fuse-zip -y`

`sudo apt install fuseiso -y`

`sudo apt install fusesmb -y`

`sudo apt install gvfs -y`

`sudo apt install gvfs-common -y`

`sudo apt install gvfs-fuse -y`

## 2 Usuário do samba

Para utilização do samba é necessário cadastrar seu usuário nele.

`sudo smbpasswd -a $USER`

Será solicitado incluir uma senha. Pode-se atribuir a mesma senha de login no sistema do usuário, embora não seja aconselhável.

## 3 Configuração

### 3.1 Configuração de compartilhamentos

Exemplo de arquivo smb.conf:

```
    workgroup = WORKGROUP
    server string = %h server (Samba, Ubuntu)
 wins support = yes
 dns proxy = yes
 log file = /var/log/samba/log.%m
 max log size = 1000
 syslog = 0
 panic action = /usr/share/samba/panic-action %d
 server role = standalone server
 passdb backend = tdbsam
 obey pam restrictions = yes
 unix password sync = yes
 passwd program = /usr/bin/passwd %u
 pam password change = yes
 map to guest = bad user
#    
[printers]
 comment = All Printers
 browseable = no
 path = /var/spool/samba
 printable = yes
 guest ok = no
 read only = yes
 create mask = 0700
#
#    
[print$]
 comment = Printer Drivers
 path = /var/lib/samba/printers
 browseable = yes
 read only = yes
 guest ok = no
#
#    
##### PASTAS COMPARTILHADAS
#    
[usuario2$Servidor]
 comment = Pasta home de Usuario em Servidor.
 path = /home/usuario2/
 browseable = yes
 read only = no
 guest ok = no
 valid users = usuario2
#    
[usuario1$Servidor]
 comment = Pasta home de Bruna usuario1 em Servidor.
 path = /home/usuario1/
 browseable = yes
 read only = no
 guest ok = no
 valid users = usuario1, usuario2
#
[play$Servidor]
 comment = HD de Multimidia em Servidor.
 path = /mnt/A829-4889/
 browseable = yes
 read only = no
    guest ok = yes
#
[HD$Servidor]
 comment = HD em Servidor.
 path = /mnt/3D5F3E455DFDCFF4/
 browseable = yes
 read only = no
 guest ok = no
 valid users = usuario2
#
[host$Servidor]
 comment = Host do Apache em Servidor.
 path = /var/www/html/
 browseable = yes
 read only = no
 guest ok = yes
#
[nuvem$Servidor]

 comment = Pasta do Dropbox em Servidor.
 path = /home/usuario2/Dropbox/
 browseable = yes
 read only = no
 guest ok = no
 valid users = usuario2
```

### 3.2 Smb.conf (completo)

3.2.1 Parametros iniciais


Parâmetros possíveis e aceitos no arquivo `/etc/samba/smb.conf`.

**Variaveis de ambiente que podem ser usadas**
`%a` - sistema operacional do cliente
`%I` - endereco ip do cliente
`%m` - nome NetBios do cliente
`%M` - Nome DNS do cliente
`%u` - Nome do usuario efetivo
`%U` - Nome do usuario NetBios primario Linux correpondente ao %u
`%g` - Grupo*  Diretorio home de %u %G` -  -Grupo primario de %U

**Nome do servico corrente**
`%d` - Numero do processo (PID) do servidor corrente
`%h` - Nome DNS da maquina em que o samba esta rodando
`%L` - Nome NetBios do servidor samba
`%N` - Diretorio home do servidor, do mapeamento automount
`%v` - Versao do samba
`%R` - O nivel do protocolo SMB que foi negociado
`%T` - Data e horario correntes

Configuração Global
--------------------------

[global]
**Determina o nome NetBios do servidor samba**
 netbios name = SAMBA

**Determina o dominio ou grupo de trabalho no qual o samba vai se anunciar**
 workgroup = DOMINIO

**Define a pontuacao do servidor samba para ser eleito como PDC, minimo de 33**
 os level = 254

**Define se o servidor tentará se tornar o navegador principal do dominio.**
 main aster = `yes` Define se o servidor tentará ou não participar das eleições para navegador local do grupo de trabalho e se o servidor samba na eleição de masterbrowser terá vantagens.

**Define se o servidor samba é um dominio para que clientes façam logons**
 domain logons = yes

**Define se o servidor Ã© o masterbrowser**
 master browse = yes

**Determina um comentatio que ira aparecer junto ao ambiente de rede**
 server string = Samba %v on (%h)

**Determina o caminho dos perfis das contas**
*no exemplo abaixo, ficara em \\nomedoservidor\[Profiles]\nome_da_conta*
 logon path = \\%L\Profiles\%U

**Determina o drive de logon**
 logon drive = J:

**Determina o logon home ou seja pasta do usuário principal manualmente**
 logon home = \\%L\homes\%U

**Determina um script de logon padrão caso deseje**
 logon script = nomedoscript.bat ou nomedoscript.cmd

**Define o nivel de seguranca do servidor**
*sao eles [user], [server], e [domain]*
 security = user

**Define o tamanho maximo do log do samba.**
*Padrão de 5mb ou 5000kb.*
 max log size = 5000

**Define a ordem de pesquisa da resolução de nomes do samba**
 name resolve order = lmhosts host wins bcast

**Define o nivel de depuração do samba nos daemons.**
*valores de 0 a 9.*
 debug level = 1

**Define como o servidor samba vai se anunciar**
 announce as = [NT Server] [NT Workstation] [Windows 9x]

**Define o programa de senhas utilizado pelo samba**
 passwd program = /usr/bin/passwd %u

**Define o script de logon da conta**
*no caso abaixo ele ira procurar algum scipts que bate com o mesmo numero da conta criada, portanto Netbios name.*
 logon script = %U.bat

**Define o arquivo onde estao instaladas e configuradas as impressoras no servidor**
*muito importante caso deseje compartilhar impressoras no samba*
 printcap name = /etc/printcap
 load printers = yes

**Define se tem suporte wins ou nao.**
 wins support = yes
 wins proxy = yes
 dns proxy = yes
 max wins ttl = 518400
 wins server = 192.168.xxx.xxx

**Define o numero de caracteres das senhas e do login**
 password level = 10
 username level = 10

**Define se as restrições do usuário nos módulos PAM terão efeito também no samba.**
 obey pam restrictions = yes

**Define as condições das senhas.**
 min password length = 5
 password history = 2
 user must logon to change password = yes
 maximum password age = 10
 minimum password age = 5
 lockout duration = 3
 reset count minutes = 2
 bad lockout attempt = 2

**Define se o servidor vai mostrar horas**
 time server = yes
 lpq command = lpq -P'%p'
 socket options = TCP_NODELAY SO_RCVBUF=8192 SO_SNDBUF=8192
 lprm command = lprm -P'%p' %j
 lpresume command = lpc release '%p' %j
 print command = lpr -r -P'%p' %s
 printing = lprng
 queuepause command = lpc stop '%p'
 unix password sync = Yes
 queueresume command = lpc start '%p'
 lppause command = lpc hold '%p' %j
 log level = 1

**Define se usa caracteres em formato windows**
 unix charset = iso8859-1
 display charset = cp850

**Define se as palavras vão ser em minusculas**
 preserve case = no
 short preserve case = no
 default case = lower

Funções:

* comment = `comentário` define um comentario.
* read only = `yes`  `no` define se o compartilhamento é ou não somente leitura
* writable = `yes`  `no` define se o compartilhamento é ou não modo escrita
* public = `yes`  `no` define se o compartilhamento é publico
* valid users = [user1] [@grupo1] define os usuarios validos a acessar o compartilhamento
* create mask = [0600] define a mascara em formato de octetos
* create mode = [0640] define as permissões padrões da criação de arquivos
* force create mode = [0640]
* directory mask = [0700]
* force directory mode = [0640]
* browsable = `yes`  `no`
* locking = `yes`  `no`
* write cache size = [500000]
* follow symlink = `yes`  `no`
* wide links = `yes`  `no`
* guest ok = `yes`  `no`
* path = `/arquivos/scripts`
* preserve case = `yes`  `no`
* short preseve case = `yes`  `no`
* default case = [lower] [upper]
* character set = [iso8859-1]  seleciona a lingua padrão do samba
* client code page = [850] Seleciona a página de códigos do samba para tratar os caracteres
* preserve case = `yes`  `no`
* valid chars = [á:Á é:É ó:Ó ú:Ú â:Â ê:Ê ô:Ô ã:Ã õ:Ô à:À ò:Ò]
* guest acount = [nobody] [@grupo1] Define a conta local que será mapeada quando um usuario se conectar sem senha
* invalid users = [user1] [@grupo1] Define uma lista de usuário que estão proibidos a acessar o compartilhamento
* valid users = [user1] [@grupo1] Semelhante a "invalid users" porém é ao contrário
* obey pam restrictions = `yes`  `no` Indica se as restrições do usuário nos módulos PAM terão efeito
* hide dot files = `yes`  `no` Define se oculta ou nao as extençoes dos arquivos
* hide files = /*.mp3/*.wav/*.tif/*.pif/*.mpg/*.mpeg/*.jpg/*.bmp Define quais extencao vao ser ocultadas
* veto files = /*.mp3/*.wav/*.tif/*.pif/*.mpg/*.mpeg/*.jpg/*.bmp Define quais extençoes vao ser vetadas, ou seja nao poderao ser gravadas.
* delete veto files = `yes` Define se o usuario pode ou nao apagar os arquivos vetados.
* vfs objects = recycle - Define uma lixeira
* recycle:repository = .recycle
* recycle:keeptree = True
* recycle:maxsize = 1024000
* recycle:versions = True
* recycle:noversions = .doc|.xls|.ppt|.pdf
* recycle:touch = False
* recycle:exclude = *.tmp*.temp *.obj*.~??

**Seção especial do samba, nao pode ser esquecida, é a pasta pessoal do login**

<pre>
[homes]
   comment = Pastas dos usuarios
   read only = no
   writable = yes
   public = no
   writeable = Yes
   valid users = %S
   create mask = 0664
   create mode = 0640
   force create mode = 0640
   directory mask = 0775
   force directory mode = 0777
   browsable = yes
   locking = no
   write cache size = 500000
</pre>

**Define parametros para os perfis do windows**

<pre>
[Profiles]
   path = /arquivos/profiles
   read only = No
   guest ok = Yes
   writeable = Yes
   browseable = No
</pre>

**Define parametros para os scripts de logon da microsoft**

<pre>
[netlogon]
   browseable = no
   comment = Compartilhamento de Scripts
   path = /arquivos/scripts
</pre>

**Secao especial do samba, nao pode ser esquecida**

<pre>
[printers]
   comment = Impressoras ( Todas )
   path = /var/spool/samba
</pre>

**Define parametros para uma possivel atualizacao de anti virus**

<pre>
[base]
   guest ok = No
   writable = yes
   comment = Impressora Laser Postscript
   path = /var/spool/samba
   printer name = HP
   browseable = yes
   printable = yes
   printer = lp
   printing = lprng
   read only = yes
   guest ok = yes
   valid users = usuario1, usuario2, @grupo1, @grupo2
   create mode = 0700
</pre>

**Define parametros para o diretoio principal**
[samba]
    comment = Diretorio Principal
    path = /arquivos
    read only = No
    force create mode = 0775
    force directory mode = 0775
    guest ok = yes
    writeable = Yes

**Define um exemplo de compartilhamento**
[teste]
    comment = Pasta de teste
    path = /arquivos/teste
    write list = @suporte
    read only = No
    force create mode = 0775
    force directory mode = 0775
    valid users = usuario1, usuario2, @grupo1, @grupo2
    guest ok = Yes
    browseable = Yes

**Define se oculta ou nao as extençoes dos arquivos**
 hide dot files = Yes

**Define quais extencao vao ser ocultadas**
 hide files = /*.mp3/*.wav/*.tif/*.pif/*.mpg/*.mpeg/*.jpg/*.bmp

**Define quais extençoes vao ser vetadas, ou seja nao poderao ser visualizadas**
 veto files = /*.mp3/*.wav/*.tif/*.pif/*.mpg/*.mpeg/*.jpg/*.bmp

**Define se o usuario tem permissão ou nao apagar os arquivos vetados**
 veto fi = yes

**Um Exemplo Completo**

<pre>
[exemplo]
   comment = Comentario
   path = /arquivos/teste
   valid users = @grupo1, @grupo2
   read only = No
   create mask = 0777
   force create mode = 0775
   force security mode = 0775
   guest ok = No
   browseable = No
   locking = no
   write cache size = 500000
   share modes = no
   veto files = /*.mp3/*.wav/*.tif/*.pif/*.jpg/*.bmp
   hide files = /*.mp3/*.wav/*.tif/*.pif/*.jpg/*.bmp
   vfs objects = recycle
   recycle:repository = .recycle
   recycle:keeptree = True
   recycle:maxsize = 1024000
   recycle:versions = True
   recycle:noversions = .doc|.xls|.ppt|.pdf
   recycle:touch = False
   recycle:exclude = *.tmp*.temp *.obj*.~??

<pre>
Smb.conf
SAMBA PDC
Criado por : Paulo Junior - www.blog.paulojr.info - www.paulojr.info
Data : 08/02/2008
</pre>
