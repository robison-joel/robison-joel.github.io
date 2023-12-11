TFTP Server
==============================

Instalação
------------------------------

Instalando deploy do servidor

`sudo apt install tftpd-hpa -y`

Operação do Daemon
-----------------------------

`systemctl status tftpd-hpa`

`systemctl enable tftpd-hpa`

`systemctl start tftpd-hpa`

`systemctl stop tftpd-hpa`

`systemctl restart tftpd-hpa`

Configuração
------------------------------

Faça uma cópia se segurança do arquivo de configuração.

`cp -rv /etc/default/tftpd-hpa /etc/default/tftpd-hpa.bckp`

Edite o arquivo **/etc/default/tftpd-hpa**.

`vim /etc/default/tftpd-hpa`

defina os parâmetros conforme abaixo.

```
RUM_DAEMON="sim"
TFTP_USERNAME="tftp"
TFTP_DIRECTORY="/srv/tftp"
TFTP_ADDRESS=":69"
TFTP_OPTIONS="--secure"
```

Client
------------------------------

Para instalar o client.

`apt install tftp-hpa`

Fonte
-------------------------

* <https://www.youtube.com/watch?v=5AEGcE1HbrQ>
