Zabbix
=====================================================

Pré-requesitos mínimos
-----------------------------

➔ Sistema Linux Ubuntu Server 22.04 LTS
➔ Zabbix 6.0 LTS
➔ 2 CPU
➔ 2 GB RAM

Pré-instalação
-----------------------------

Vamos instalar o Apache e o MariaDB.

`sudo apt update`

`apt install vim -y`

`àpt install locales -y`

### Instalação do Apache

`apt install apache2 -y`

`apt install apache2-doc -y`

`apt install apache2-utils -y`

### Instalação do MariaDB

`sudo apt install mariadb-server -y`

Procedimento de segurança para o Banco de Dados.

`sudo mysql_secure_installation`

> Sua senha de acesso ao BD será de seu usuário root, pois nessa versão eles usam o MariaDB no lugar do MySQL.
>
> Recomendamos colocar uma senha para o root do DB, não desabilitar o acesso externo, desabilitar o usuario anônimo e apagar o banco de teste.

Crie o conteúdo do banco de dados.

`mysql -uroot -p`

mysql> `create database zabbix character set utf8mb4 collate utf8mb4_bin;`

mysql> `create user zabbix@localhost identified by 'zabbix';`

mysql> `grant all privileges on zabbix.* to zabbix@localhost;`

mysql> `set global log_bin_trust_function_creators = 1`

mysql> `quit;`

Instalação do zabbix
-----------------------------

Agora, vamos instalar o Zabbix

`mkdir zabbix`

`cd zabbix/`

Download do zabbix.

`wget https://repo.zabbix.com/zabbix/6.4/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.4-1+ubuntu22.04_all.deb`

`chmod +x zabbix-release_6.4-1+ubuntu22.04_all.deb`

`dpkg -i zabbix-release_6.4-1+ubuntu22.04_all.deb`

`apt install -f`

`apt update`

Pacotes adicionais

`apt install zabbix-server-mysql -y`

`apt install zabbix-frontend-php -y`

`apt install zabbix-apache-conf -y`

`apt install zabbix-sql-scripts -y`

`apt install zabbix-agent -y`

Agora, vamos carregar as informações para dentro do nosso Banco de Dados!

Caso precise, localize o arquivo com esses comandos:

`apt install locate -y`

`locate server.sql.gz`

O comando acima vai mostrar os caminhos que contem esse arquivo "server.sql.gz". Utilize o que se refere ao mysql no comando abaixo.

Ao encontrar, vamos continuar importando as informações para o banco de dados.

`zcat /usr/share/zabbix-sql-scripts/mysql/server.sql.gz | mysql --default-character-set=utf8mb4 -u zabbix -p zabbix`

A senha é:

`zabbix`

Aguarde (pacientemente) até acabar o aporte das informações.

Desabilite a opção **log_bin_trust_function_creators** depois de importar as informações.

`mysql -uroot -p`

mysql> `set global log_bin_trust_function_creators = 0;`

mysql> `quit;`

Configuração
-----------------------------------------

Edite o arquivo **/etc/zabbix/zabbix_server.conf**:

`vim /etc/zabbix/zabbix_server.conf`

Localize os parâmetros abaixo, descomente se necessário e faça as alterações conforme disposto abaixo:

~~~
DBHost=localhost
DBName=zabbix
DBUser=zabbix
DBPassword=zabbix
~~~

Agora, edite o arquivo **/etc/apache2/conf-available/zabbix.conf**.

`vim /etc/apache2/conf-available/zabbix.conf`

Descomentar a seguinte linha:

`php_value date.timezone Europe/Riga`

Alterar para:

`php_value date.timezone America/Sao_Paulo`

E vamos instalar o PT-BR:

`locale -a`

`locale-gen pt_BR.UTF-8`

Agora, vamos dar um restart em todos os serviços:

`systemctl restart zabbix-server zabbix-agent apache2`

Configura para que os serviços iniciem com o sistema.

`systemctl enable zabbix-server zabbix-agent apache2`

Exibe o status de cada um dos serviços.

`systemctl status zabbix-server zabbix-agent apache2`

Acesso WebGUI
------------------------

Ache o seu IP:

`hostname -I`

Acessar interface Web:

`http://<IP_do_host>/zabbix`

Login:

`Admin` (com A maiúsculo)

Senha:

`zabbix`

Fonte
----------------------------------------

* <https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/>
