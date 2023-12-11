Backups
=========================

1 Comando rsync
-------------------------

Para fazer backup's com o comando rsync

Instalar o rsync em ambos os host's:

`sudo apt install rsync -y`

Para realizar a sincronização utilize:

`rsync -ahvz --progress --delete arquivo/pasta_local arquivo/pasta_remoto`

Onde:

* `-a`: Modo archive (arquivamento). Copia os arquivos e diretórios recursivamente (como -r) e preserva links simbólicos, permissões de arquivos, propriedades de usuário e grupo (ownership) e timestamps.

* `-h`: Números são representados em formato legível por humanos

* `-v`: Modo verboso, que mostra detalhes sobre a transferência de arquivos.

* `-z`: Comprimir os dados dos arquivos antes de enviá-los

* `–progress`: Mostrar o progresso da cópia de arquivos ao transferir os dados

* `–delete`: Exclui um arquivo ou diretório no destino caso ele não exista na origem

Também contamos com essas opções:

* `-e`: Especificar o shell remoto a ser usado (rsh, ssh)

* `-c`, `–checksum`: Calcula os *checksums* dos arquivos para verificar se eles são iguais ao transferi-los. Utilizada para verificar a integridade dos dados copiados.

* `–exclude`: Permite especificar arquivos ou diretórios que não devem ser copiados para o destino

* `–include`: Permite especificar arquivos ou diretórios que devem ser copiados para o destino

* `-r`: Copia dados recursivamente, sem preservar timestamps e permissões ao transferir os dados

* `-b`, `–backup`: Não sobrescreve arquivos que já existam no destino da transferência, mas os renomeia adicionando um sufixo ~ aos seus nomes, antes de executar a transferência de novos arquivos.

* `-u`, `–update`: Não sobrescreve nenhum arquivo no destino da transferência que possua uma data posterior (mais recente) à data do arquivo correspondente, na origem.

* `–remove-source-files`: Exclui (apaga) os arquivos no diretório de origem após o término da transferência de dados.

* `-n`: Modo *dry run* – executa uma tentativa de copiar dados sem realmente copiar qualquer arquivo.
