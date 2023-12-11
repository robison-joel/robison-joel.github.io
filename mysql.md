MySQL
================================================================

1 Instalação
----------------------------------

Atualizar

`sudo apt update ; apt list --upgradable ; sudo apt upgrade`

Depois disso, instale o pacote mysql-server

`sudo apt install mysql-server`

Configurando o MySQL

`sudo mysql_secure_installation`

Assim que apertar enter, aparecerá um diálogo (em inglês) que é semelhante ao descrito abaixo:

> NOTA: EXECUTAR TODAS AS PARTES DESTE SCRIPT É RECOMENDADO PARA TODOS MariaDB SERVIDORES EM USO DE PRODUÇÃO! POR FAVOR, LEIA CADA PASSO COM ATENÇÃO!
> Para fazer login no MariaDB para protegê-lo, precisaremos do senha para o usuário root. Se você acabou de instalar o MariaDB e ainda não definiu a senha de root, você deve apenas pressionar enter aqui.
>
> Digite a senha atual para root (digite para nenhum):

digite a **senha de root** para seu mysql. Caso a senha seja aceita, aparecerá a confirmação:

> OK, senha usada com sucesso, seguindo em frente...
> Definir a senha de root ou usar o unix_socket garante que ninguém pode fazer login no usuário root do MariaDB sem a devida autorização.
>
> Você já tem sua conta root protegida, então você pode responder 'n' com segurança.
>
> Mudar para autenticação unix_socket [S/n]

Digite "s" ou "y" + `enter`

> Ativado com sucesso!
> Recarregando tabelas de privilégios...
> ...Sucesso!
> Você já tem sua conta root protegida, então você pode responder 'n' com segurança.
>
> Alterar a senha do root? [S/n]

Digite "n" + `enter`

> ... pulando.
> Por padrão, uma instalação do MariaDB tem um usuário anônimo, permitindo que qualquer  pessoa para entrar no MariaDB sem ter que ter uma conta de usuário criada para eles. Destina-se apenas para testes e para tornar a instalação ir um pouco mais suave. Você deve removê-los antes de se mudar para um ambiente de produção.

Remover usuários anônimos? [S/n] s
 ... Sucesso!

> Normalmente, o root só deve ter permissão para se conectar a partir de 'localhost'. este garante que alguém não consiga adivinhar a senha do root da rede.

Não permitir login root remotamente? [S/n] n
 ... pulando.

> Por padrão, o MariaDB vem com um banco de dados chamado 'test' que qualquer um pode Acesso. Isso também é destinado apenas para teste e deve ser removido antes de passar para um ambiente de produção.
> Remover banco de dados de teste e acesso a ele? [S/n] s
> Eliminando banco de dados de teste...
>
>... Sucesso!
>
> Removendo privilégios no banco de dados de teste...
>
> ... Sucesso!

Recarregar as tabelas de privilégios garantirá que todas as alterações feitas até agora entrará em vigor imediatamente.

> Recarregar tabelas de privilégios agora? [S/n] s
>
> ... Sucesso!
>
> Limpando...

Tudo feito! Se você concluiu todas as etapas acima, seu MariaDB a instalação agora deve ser segura.

Obrigado por usar o MariaDB!

nível de validação de senha.

> Selecione o nível ao digitar 2 (assim o mysql exigirá que sua senha tenha pelo menos **oito caracteres** de tamanho e inclua uma mistura de caracteres em **maiúsculo**, **minúsculo**, **numérico** e **especial**.

Escolha uma senha para o root.

```
Erro encontrado:
> Error: Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2)

```
