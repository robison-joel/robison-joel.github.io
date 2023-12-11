OpenVPN
==============================

Procediemto que instala um Servidor OpenVPN no Ubuntu Server 20.04.

Instalação
------------------------------

Atualizar os repositórios, programas e sistema.

`sudo apt update ; apt list --upgradable ; sudo apt upgrade -y`

Baixe os pacotes para instalação

`wget https://git.io/vpn -O openvpn-ubuntu-install.sh`

Concede permissão de execução para o arquivo.

`chmod -v +x openvpn-ubuntu-install.sh`

Execute o script de instalação.

`bash openvpn-ubuntu-install.sh`

A instalação será guiada á partir de alguns questionamentos. Responda-os conforme as instruções abaixo.

* Desative o suporte para IPV6;
* Defina a porta da VPN;
* Escolha UDP;
* Escolha um servidor DNS para a sua conexão VPN;
* Desabilite A compressão;
* Não customize as configurações de criptografia;

Em seguida
