Usuarios Linux
========================================

1 Senhas
--------------------------------------

1.1 Atribuir ou trocar a senha de um usuario.

`sudo passwd nomedousuario senha`

2 Recuperação de senha
--------------------------------------

Caso você esqueça a senha do seu linux, você pode resetar a senha do seu usuario.

2.1 Ligue o computador e aguarde aparecer o menu do gerenciador de boot GRUB;

> Se o menu do GRUB não aparecer, experimente pressionar e segurar a tecla `Shift` depois que apertar o botão “Power” para ligar o computador. Teclas como F8, F3 e F10 também podem te ajudar;

2.3 No menu do GRUB, use as teclas de direção e vá até a opção “Advanced Options for Ubuntu” ou “Opções avançadas para Ubuntu” e então tecle **enter**;

2.4 Na tela que será exibida, selecione uma das opções de boot que possui **“recovery mode”** no final do nome e tecle **enter**;

2.5 Quando aparecer a tela do **"Menu de recuperação"**, use as teclas de direção e vá até a opção `root- Drop to root shell prompt` ou `root- Desistir e ir para terminal em modo root` e pressione **enter**. Com isso, você verá o prompt de comando no final da tela.

2.6 Aperte Ctrl + l para limpar a tela.

2.7 Digite o comando a seguir e tecle **enter**, para montar o sistema de arquivos com permissão de leitura e escrita;

`mount -o rw,remount/`

2.8 Para alterar a senha do usuário, use o comando `passwd NOME_USUARIO` (substituindo NOME_USUARIO pelo seu nome de usuário). Será solicitado inserir a nova senha, digite-a e tecle **enter**.

> Caso você não se lembre do nome de usuário, para descobrir, digite o comando `ls /home` e tecle **enter**:

2.9 Depois confirme essa senha, digitando-a novamente e teclando **enter**. No final, será exibida a mensagem `passwd: password updated successfully` ou `passwd: senha atualizada com sucesso`, confirmando que a senha de usuário foi redefinida com êxito;

2.10 Por fim, execute o comando exit para voltar ao “Menu de recuperação” e nele, selecione e tecle **enter** na opção “resume Resume normal boot” ou “resume Continuar inicialização normal”, para sair do modo de recuperação.
