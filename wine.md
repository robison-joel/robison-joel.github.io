Wine
=====================

[Clique aqui](https://github.com/robison-joel/Codagem/tree/main/Shell/scripts/Wine) para o download do script de instalação do Wine.

Aqui temos as instruções para a instalação do wine no Ubuntu 22.04

1 Instalação
----------------------------------------------------------------------

1.1 Adicionando arquitetura i386 ( 32 bit ), de o comando abaixo no terminal.

`sudo dpkg --add-architecture i386`

1.2 Atualize o apt com o comando abaixo.

`sudo apt update`

1.3 Instale o wine com o comando abaixo.

`sudo apt install wine wine32 winetricks`

1.4 Abra as configurações do Wine para gerar os arquivos iniciais, só altere algo se souber o que está fazendo.

`winecfg`

1.5 Instale o Directx.

`winetricks d3dx9 ; wine ~/.cache/winetricks/directx9/directx_Jun2010_redist.exe`

1.6 Instale os complementos directmusic e directplay.

`winetricks directmusic directplay`

1.7 Para instalar as fonts Microsoft de os comandos abaixo.

`winetricks corefonts`

1.8 O compactador e descompactador 7zip é usado por vários instaladores de programas, instale ele para evitar problemas com programas que necessitem dele.

`winetricks 7zip`

1.9 Para instalar uma ótima coleção de codecs e outros componentes Windows de o comando abaixo no terminal.

`winetricks allcodecs`

1.10 Crie o arquivo para que os APP .exe sejam executados pelo Wine.

`sudo vim ~/.local/share/applications/wine.desktop`

1.11 Insira essas informações ao arquivo:

~~~
[Desktop Entry]
Name=Wine
Exec=wine
Type=Application
StartupNotify=true
Icon=winetricks
~~~

1.12 Crie a entrada para reconhecer os .exe.

`echo "application/x-ms-dos-executable=wine.desktop;" >> ~/.config/mimeapps.list`

1.13 Criar atalho para um programa especifico.

Local dos arquivos

/home/usuário/.wine/driver_c/Program\ Files/Nome\ do\ Programa/Programa.exe

~~~
[Desktop Entry]

Version=1.0

Encoding=UTF-8

Name=FiveRow

Type=Application

Exec=wine /home/$USER/.wine/drive_c/windows/fiverow.exe

Terminal=false

Icon=/home/$USER/.icons/fiverow.svg

Comment=Jogo da velha.

Categories=Game;

StartupNotify=true
~~~

FONTES
---------------------------------------------------------

* <https://linuxdicasesuporte.blogspot.com/2022/06/instalar-wine-no-ubuntu-2204.html>

* <https://www.vivaolinux.com.br/topico/Wine-Wine-X-Cedega/Problema-em-achar-programa-instalado-pelo-Wine>

* <https://www.vivaolinux.com.br/topico/Linux-E-Games/Atalho-de-executavel-do-wine>
