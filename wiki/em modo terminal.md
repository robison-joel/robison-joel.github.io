Iniciar em modo terminal
================================================================

1 Como configurar o linux para iniciar diretamente em modo texto, diminuindo a energia, maximizando o desempenho da máquina.

1.1 Abra um terminal (Usando o Dash ou pressionando as teclas CTRL+ALT+T);

1.2 Copie e cole o comando abaixo no terminal e aperte enter:

`sudo gedit /etc/default/grub`

1.3 Edite o arquivo de configuração, fazendo as seguintes mudanças:

1.3.1 Comente a linha GRUB_CMDLINE_LINUX_DEFAULT=”quiet splash”, adicionando # no início. Isso irá desativar a tela colorida do Ubuntu;

1.3.2 Mude GRUB_CMDLINE_LINUX=”” para GRUB_CMDLINE_LINUX=”text”. Isso fará com que o Ubuntu inicialize diretamente em modo de texto;

1.3.3 Descomente essa linha #GRUB_TERMINAL=console, removendo o # no início. Isso faz com que o menu do GRUB fique em modo de texto (tela preto e branco, sem imagem de fundo)

1.4 Salve e feche o arquivo;

1.5 Atualize o Grub com o comando abaixo:

`sudo update-grub`

1.6 Para ver o resultado, reinicie o computador.

Fonte
----------------------------------------------------------------

* <http://maguscode.blogspot.com>
