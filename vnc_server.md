VNC
========================

X11VNC
------------------------

### Ubuntu

#### Instalação

Para instalar use o comando:

`sudo apt-get install x11vnc`

Para criar a senha:

`sudo x11vnc -storepasswd SEU_PASSWORD /etc/x11vnc.pass`

Para dar permissão ao arquivo de senha:

`sudo chmod 744 /etc/x11vnc.pass`

O comando a seguir vai rodar o X11vnc

`sudo x11vnc -auth /var/run/lightdm/root/:0 -noxrecord -noxfixes -noxdamage -rfbauth /etc/x11vnc.pass -forever -bg -rfbport 5900 -o /tmp/x11vnc.log`

Bom, até aí o aplicativo vai funcionar direitinho. Contudo, após reiniciar a máquina ele não mais estará rodando. Para fazer com que o programa inicie com o Sistema Operacional, será necessário criar um script dentro de /etc/init.d/, dar permissão de execução e executar o comando "update-rc.d" para fazer com que isso aconteça.

Criar o arquivo **/etc/init.d/vnc-server**

`vim /etc/init.d/vnc-server`

adicionar as linhas de comando dentro do arquivo:

```
#!/bin/bash
 
start() {
    echo "Iniciando VNC-Server..."
    x11vnc -env FD_XDM=1 -display :0 -forever -rfbauth /root/.vncpasswd &>> /var/log/vnc-server.log &
    echo "[OK]"
}
 
stop() {
    echo "Desligando VNC-Server..."
    killall x11vnc &>> /var/log/vnc-server.log
    echo "[OK"]
}
    case "$1" in
    start) start
    ;;
    stop) stop
    ;;
    restart) stop; start
    ;;
    *) echo "Uso correto: (start|stop|restart)"
    ;;
esac
```

Para dar permissão de execução para ao script:

`chmod +x /etc/init.d/vnc-server`

Agora, vamos temos que colocar o script para iniciar com o sistema:

`cd /etc/init.d/`

`update-rc.d vnc-server defaults`

O x11vnc já está configurado para iniciar com o sistema e você pode fazer o STOP e START com os comandos abaixo:

##### Operação do Daemon

`/etc/init.d/vnc-server start`

`/etc/init.d/vnc-server stop`

`/etc/init.d/vnc-server restart`

Caso você não precise mais que ele suba junto com o sistema operacional, faça o comando abaixo:

`cd /etc/init.d/`

`update-rc.d -f vnc-server remove`

A porta padrão de execução do VNC é a 5900

Para iniciar

`/etc/init.d/vnc-server`

crie um script com o comando acima

```
#!/bin/bash
#
/etc/init.d/vnc-server
```

Fontes
---------------------

* <http://almirjr-narede.blogspot.com/2015/07/instalar-e-configurar-o-x11vnc-para.html>
