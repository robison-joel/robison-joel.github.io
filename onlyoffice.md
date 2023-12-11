Only Office
================================================================

Suite de Ferramentas de escritório Multiplataforma.

1 Instalação
----------------------------------------------------------------

1.1 Crie a pasta que vai receber o arquivo de Instalação.

`sudo mkdir .onlyoffice`

1.2 Entra na pasta

`cd .onlyoffice/`

1.3 Faz o download do arquivo deinstalação.

`sudo wget https://download.onlyoffice.com/install/desktop/editors/linux/onlyoffice-desktopeditors_amd64.deb`

> Caso o link acima esteja desatualizado procure o mais recente em: <https://www.onlyoffice.com/pt/download-desktop.aspx#desktop>

1.4 Concede permissão de execução ao arquivo.

`sudo chmod +x onlyoffice-desktopeditors_amd64.deb`

1.5 Executa

`sudo dpkg -i onlyoffice-desktopeditors_amd64.deb`

1.6 Instala dependêcias, caso hajam.

`sudo apt install -f -y`

1.7 Atualiza.

`sudo apt update ; apt list --upgradable ; sudo apt upgrade -y`

1.8 Caso queira, após a instalação você pode deletar os arquivos de instalação.

`cd ..`

`sudo rm -rf .onlyoffice`

Fonte
----------------------------------------------------------------

* <https://www.onlyoffice.com/pt/download-desktop.aspx#desktop>
