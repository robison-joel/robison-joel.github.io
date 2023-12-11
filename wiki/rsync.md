# RSYNC

## 1 O que é?

Comando que copia, em forma de síncrona, arquivos entre pastas locais ou em computadores em rede.

## 2 Instalação

Abra seu terminal e digite o seguinte comando (inserindo a senha na sequência).

`sudo apt-get install rsync -y`

## 3 Exemplo de sintaxe

3.1 Quando a cópia pe no mesmo host, ou para um disco externo.

`rsync -vurh --progress [origem/] [destino]`

3.2 Quando a cópia será feita em um computador remoto

`rsync -avz [origem/] usuario@servidor:[destino]`

Obs.: Utilizar sempre os caminhos absolutos nas pastas e arquivos.

## 4 Opções para este comando

* `-v`

"Verbose mode".Exibe o que está sendo copiado

* `-u`

Update: Não sobreescreve os arquivos no destino caso eles sejam mais "recentes" do que os da na origem.

* `-r`

Recursivo: Copia todo o conteúdo da pasta de forma recursiva sem

* `-h`

Exibe valores de tamanhos de arquivos em formato inteligível aos humano.

* `-z`

Compacta os arquivos antes de enviá-los á origem.

* `--progress`

Mostra uma barra de progresso no ato da cópia dos arquivos.

* `--exclude`

Permite especificar arquivos ou diretórios que não devem ser copiados para o destino

Sintaxe: --exclude=file1,file2...

* `--include`

Permite especificar arquivos ou diretórios que deverão ser copiados para o destino

Sintaxe: --include=file1,file2...

* `--delete`

Exclui o arquivo ou diretório na origem, caso ele não exista na origem.

## FONTES

* <https://www.digitalocean.com/community/tutorials/how-to-use-rsync-to-sync-local-and-remote-directories-pt>

* <https://terminalroot.com.br/2021/05/10-exemplos-de-uso-do-comando-rsync.html>

* <https://www.hostinger.com.br/tutoriais/comando-rsync-linux>

* <http://www.bosontreinamentos.com.br/linux/10-exemplos-do-comando-rsync-para-backup-e-sincronismo-de-arquivos-no-linux/>
