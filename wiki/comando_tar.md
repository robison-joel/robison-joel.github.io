Comando Tar
================================================================

O Tar é um dos comandos Linux mais utilizados para compactação de arquivos. Tar significa *tape archive*. Na maioria dos casos em que o processo é realizado com o comando Tar, é gerado um arquivo com extensão `.tar`. Para maior compactação é utilizado o `gzip`, gerando um arquivo `.tar.gz`.

Criar um Arquivo .tar no Linux
-----------------------------------------------------------------

Você pode criar compressões .tar para arquivos e diretórios. Um exemplo de um arquivo deste tipo é:

`tar -cvf` *sampleArchive.tar /home/sampleArchive*

O comando usa as opções `–cvf`, que significam:

* `c` – cria um novo arquivo .tar.
* `v` – mostra uma descrição do progresso de compactação.
* `f` – nome do arquivo.

Criar um Arquivo .tar.gz no Linux
-----------------------------------------------------------------

Uma forma de melhorar a compactação, podemos usar .tar.gz.

Exemplo:

`tar -cvzf sampleArchive.tar.gz /home/sampleArchive`

A opção adicional `z` representa a compressão gzip. Você também pode criar um arquivo .tgz similar ao tar.gz:

`tar -cvzf sampleArchive.tgz /home/sampleArchive`

Criar um Arquivo .tar.bz2 no Linux
-----------------------------------------------------------------

`tar -cvjf sampleArchive.tar.bz2 /home/sampleArchive`

O processo é similar com o .tar.tbz ou .tar.tb2:

`tar -cvjf sampleArchive.tar.tbz /home/sampleArchive`

`tar -cvjf sampleArchive.tar.tb2 /home/sampleArchive`

Como Descompactar Arquivos .tar no Linux
-----------------------------------------------------------------

O comando Tar também pode ser utilizado na descompactação de arquivos. O comando abaixo é um exemplo de como extrair arquivos no diretório atual:

`tar -xvf sampleArchive.tar`

Se você deseja realizar a extração para um diretório diferente, pode usar a opção -C:

`tar -xvf sampleArchive.tar -C /home/ExtractedFiles/`

Um comando similar pode ser usado na descompactação de arquivos .tar.gz:

`tar -xvf sampleArchive.tar.gz`

`tar -xvf sampleArchive.tar.gz -C /home/ExtractedFiles/`

.tar.bz2,.tar.tbz ou .tar.tb2 são descompactados de maneira semelhantes. Basta utilizar o comando:

`tar -xvf sampleArchive.tar.bz2`

Como Listar os Conteúdos de um Arquivo no Linux
-----------------------------------------------------------------

Depois que o arquivo tiver sido construído, você pode listar seus conteúdos com o comando:

`tar -tvf sampleArchive.tar`

Isso irá mostrar a lista completa, juntamente com suas permissões e datas. Da mesma maneira, para arquivos .tar.gz é usado o comando:

`tar -tvf sampleArchive.tar.gz`

Este mesmo método também funciona para a extensão.tar.bz2:

`tar -tvf sampleArchive.tar.bz2`

Como Descompactar um Único Arquivo .tar
-----------------------------------------------------------------

Com o arquivo compactado criado, é possível extrair um único item dele, como mostra o exemplo abaixo:

`tar -xvf sampleArchive.tar example.sh`

O example.sh é um único item que será extraído do arquivo sampleArchive.tar. Outra alternativa é usar o comando:

`tar --extract --file= sampleArchive.tar example.sh`

Para extrair um único item de um arquivo .tar.gz, você pode usar um comando semelhante:

`tar -zxvf sampleArchive.tar.gz example.sh`

Ou então:

`tar --extract --file= sampleArchive.tar.gz example.sh`

Para arquivos .tar.bz2:

`tar -jxvf sampleArchive.tar.bz2 example.sh`

Outra opção é:

`tar --extract --file= sampleArchive.tar.bz2 example.sh`

Como você pode ver, o comando Tar é bastante versátil em sua sintaxe.

Como Extrair Múltiplos Itens de Arquivos .tar
-----------------------------------------------------------------

Caso você queira extrair diversos itens de um arquivo compactado, utilize o formato de comando abaixo:

`tar -xvf sampleArchive.tar "file1" "file2"`

Para .tar.gz:

`tar -zxvf sampleArchive.tar.gz "file1" "file2"`

Arquivos com extensão .tar.bz2:

`tar -jxvf sampleArchive.tar.bz2 "file1" "file2"`

Extrair Diversos Arquivos de um Mesmo Padrão
-----------------------------------------------------------------

Para extrair itens que sigam um mesmo padrão, por exemplo, extrair apenas itens .jpg, utilize wildcards. Veja o exemplo abaixo:

`tar -xvf sampleArchive.tar --wildcards '*.jpg'`

Para .tar.gz você pode usar:

`tar -zxvf sampleArchive.tar.gz --wildcards '*.jpg'`

Comando para .tar.bz2:

`tar -jxvf sampleArchive.tar.bz2 --wildcards '*.jpg'`

Como Adicionar Arquivos em um .tar
-----------------------------------------------------------------

Além de poder extrair itens de um arquivo .tar, você também pode adicionar novos. Para isso, utilize a opção -r. O Tar Linux permite adicionar arquivos e diretórios.

Abaixo temos um exemplo de como adicionar o arquivo example.jpg ao arquivo compactado sampleArchive.tar.

`tar -rvf sampleArchive.tar example.jpg`

Também é possível adicionar um diretório. No exemplo abaixo iremos inserir o diretório image_dir dentro de sampleArchive.tar

`tar -rvf sampleArchive.tar image_dir`

Não é possível adicionar arquivos ou diretórios em arquivos .tar.gz ou .tar.bz2.

Como Verificar um Arquivo .tar
-----------------------------------------------------------------

Com o tar você pode verificar um arquivo. Esta é uma das maneiras em que isto é possível:

`tar -tvf sampleArchive.tar`

Esta função não é permitida em arquivos .tar.gz ou .tar.bz2.

Como Verificar o Tamanho de Arquivos no Linux
-----------------------------------------------------------------

Depois de criar um arquivo é possível verificar seu tamanho, que será mostrado em KB (Kilobytes).

Abaixo temos exemplos deste comando em diferentes tipos de arquivos:

`tar -czf - sampleArchive.tar | wc -c`

`tar -czf - sampleArchive.tar.gz | wc -c`

`tar -czf - sampleArchive.tar.bz2 | wc -c`

Fontes
-----------------------------------------------------------------------------

* <https://www.hostinger.com.br/tutoriais/comando-tar-linux>
