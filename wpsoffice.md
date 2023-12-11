WPS Office
================================================================

Programa para acesso remoto.

1 Instalação
----------------------------------------------------------------

1.1 Crie a pasta que vai receber o arquivo de Instalação.

`sudo mkdir .wpsoffice`

1.2 Entra na pasta

`cd .wpsoffice/`

1.3 Faz o download do arquivo deinstalação.

`sudo wget https://wdl1.pcfg.cache.wpscdn.com/wpsdl/wpsoffice/download/linux/10976/wps-office_11.1.0.10976.XA_amd64.deb`

> Caso o link acima esteja desatualizado procure o mais recente em:

1.4 Concede permissão de execução ao arquivo.

`sudo chmod +x wps-office_11.1.0.10976.XA_amd64.deb`

1.5 Executa

`sudo dpkg -i wps-office_11.1.0.10976.XA_amd64.deb`

1.6 Instala dependêcias, caso hajam.

`sudo apt install -f -y`

1.7 Atualiza.

`sudo apt update ; apt list --upgradable ; sudo apt upgrade -y`

1.8 Caso queira, após a instalação você pode deletar os arquivos de instalação.

`cd ..`

`sudo rm -rf .wpsoffice`
