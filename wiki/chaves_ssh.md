Chaves SSH
=================================

1 Criando a chave
---------------------------------

Para a conexão com chave, primeiro gere a chave em seu computador.

`ssh-keygen`

Você pode criar a sua chave com a criptografia RSA:

`ssh-keygen -t rsa`

Caso queira identificar o arquivo podes indicar o caminho absoluto para o aqruivo. Por exemplo:

`ssh-keygen /home/usuario/.ssh/arquivo`

Durante a criação da chave será necessário determinar uma frase de acesso. trata-se de uma "frase" de segurança: escolha com sabedoria.

2 Obtendo a chave
---------------------------------

Copie o conteúdo da sua chave pública, em um notepad ou editor de texto qualquer. Para abtê-lo, utilize o seguinte comando:

`cat /home/usuario/.ssh/arquivo.pub`

3 Enviando a chave
---------------------------------

Para enviar a chave para o host que deverá ser acessado, pode-se utilizar dois métodos:

### 3.1 Metodo direto

`ssh-copy-id usuario@ip_do_servidor`

`ssh-copy-id -i /home/usuario/.ssh/arquivo.pub usuario@ip_do_servidor`

### 3.2 Metodo tradicional

Incluir a sua chave publica no arquivo `/home/usuario/.ssh/authorized_keys`.

Para isso, siga esses passos:

Acesse o servidor em questão via ssh (inicialmnte com a senha), e adicione a sua chave ao arquivo `/home/usuario/.ssh/authorized_keys`:

`sudo echo "*conteúdo do arquivo .pub copiado" >> /home/usuario/.ssh/authorized_keys`
