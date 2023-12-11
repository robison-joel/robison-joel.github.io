OpenFire
====================================

Java
-----------------------------------------------------

1 Instalar

1 No **Ubuntu 18.04** ou superior.

`sudo apt install openjdk-8-jdk`

`sudo apt install openjdk-8-jre`

2 No **Debian 10** ou superior.

`wget -qO - https://adoptopenjdk.jfrog.io/adoptopenjdk/api/gpg/key/public | sudo apt-key add -`

`echo "deb $([ \"$(uname -m)\" = \"x86_64\" ] && echo -n '[arch=amd64]') https://adoptopenjdk.jfrog.io/adoptopenjdk/deb/ buster main" | sudo tee /etc/apt/sources.list.d/adoptopenjdk.list`

`sudo apt update`

`sudo apt install adoptopenjdk-8-hotspot`

3 Para verificar a versão do Java.

`java -version`

4 Habilite o serviço no sistema

`sudo systemctl enable --now openfire`

5 Verifique o status do serviço.

`systemctl status openfire`

MariaDB
-----------------------------------------------------

1 Instalação

`apt install mariadb-server`

2 Verifique o status do serviço

`systemctl status mariadb`

3 Para a operação do daemon

`systemctl start mariadb`

`systemctl restart mariadb`

`systemctl stop mariadb`

`systemctl reload mariadb`

4 Execute o script de segurança.

`mysql_secure_installation`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Abaixo uma imagem que ilustra as respostas das perguntas feitas a partir de agora.

![mysql_secure_installation](pics/mariadb_security.png)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Na sequencia acima você pode escolher uma senha especifica para o MariaDB. Não perca essa chance e deixe seu MariaDB seguro.

`CREATE DATABASE openfire;`

`GRANT ALL PRIVILEGES ON openfire.* TO openfire@localhost -> IDENTIFIED BY ‘StrongP@assword123!’;`

`FLUSH PRIVILEGES;`

`QUIT`

Fonte
-----------------------------------------------------

* <https://www.vivaolinux.com.br/dica/Instalando-o-Java-8-no-Debian-10>

* <https://itslinuxfoss-com.translate.goog/how-to-install-openfire-on-ubuntu-20-04/?_x_tr_sl=auto&_x_tr_tl=pt&_x_tr_hl=pt-BR>

* <https://pt.linux-console.net/?p=251#gsc.tab=0>

* <https://tidahora.com.br/instalando-servidor-de-chat-interno-para-empresas-com-openfire-no-ubuntu/>
