Discord
================================================================

Mensageiro que possibilita criação de grupos, reuniões e Videoconferências.

1 Instalação
----------------------------------------------------------------

1.1 Crie a pasta que vai receber o arquivo de Instalação.

`sudo mkdir .discord`

1.2 Entra na pasta

`cd .discord/`

1.3 Faz o download do arquivo deinstalação.

`sudo wget https://dl.discordapp.net/apps/linux/0.0.17/discord-0.0.17.deb`

> Caso o link acima esteja desatualizado procure o mais recente em: 

1.4 Concede permissão de execução ao arquivo.

`sudo chmod +x discord-0.0.17.deb`

1.5 Executa

`sudo dpkg -i discord-0.0.17.deb`

1.6 Instala dependêcias, caso hajam.

`sudo apt install -f -y`

1.7 Atualiza.

`sudo apt update ; apt list --upgradable ; sudo apt upgrade -y`

1.8 Caso queira, após a instalação você pode deletar os arquivos de instalação.

`cd ..`

`sudo rm -rf .discord`