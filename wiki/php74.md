PHP 7.4
==========================

1 Instalação
-------------------------------

> Para a

`sudo apt update`

1.1 Instalar php7.4 e bibliotecas necessárias

`sudo apt-get install software-properties-common`

`sudo add-apt-repository ppa:ondrej/php`

`sudo apt-get update`

`sudo apt list --upgradable`

`sudo apt-get upgrade`

`sudo apt install php7.4 -y`

`sudo apt install libapache2-mod-php7.4 -y`

`sudo apt install php7.4-curl -y`

`sudo apt install php7.4-intl -y`

`sudo apt install php7.4-zip -y`

`sudo apt install php7.4-soap -y`

`sudo apt install php7.4-xml -y`

`sudo apt install php7.4-gd -y`

`sudo apt install php7.4-mbstring -y`

`sudo apt install php7.4-bcmath -y`

`sudo apt install php7.4-common -y`

`sudo apt install php7.4-xml -y`

`sudo apt install php7.4-mysqli -y`

1.2 Habilitando mods do apache2 para trabalhar com o PHP7.4

`a2enmod php7.4`

1.3 Reescreve os mods

`a2enmod rewrite`

1.4 Restart do apache2

`sudo service apache2 restart`

ou

`systemctl restart apache2`

FONTES
-------------------------------

* <https://tecadmin.net/how-to-install-php-on-ubuntu-22-04/>

* <https://dev.to/alexandrefreire/como-instalar-o-php-7-4-no-ubuntu-463f>

* <https://www.linuxcapable.com/how-to-install-php-7-4-on-ubuntu-20-04-lts/>
