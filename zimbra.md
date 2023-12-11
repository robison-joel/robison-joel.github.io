Zimbra
======================================

Instalação
----------------------------------

1.1 Ascende a root

`sudo su`

1.2 Cria a pasta

`mkdir zimbra_app`

1.3 Entra na pasta

`cd zimbra_app/`

1.4 Download do pacote

`wget https://files.zimbra.com/downloads/8.8.15_GA/zcs-8.8.15_GA_4179.UBUNTU20_64.20211118033954.tgz`

1.5 Descompacta

`tar -vzxf zcs-8.8.15_GA_4179.UBUNTU20_64.20211118033954.tgz`

1.6 Apaga o arquivo compactado

`cd zcs-8.8.15_GA_4179.UBUNTU20_64.20211118033954.tgz`

1.7 Entra na pasta Descompactada

`cd zcs-8.8.15_GA_4179.UBUNTU20_64.20211118033954/`

1.8 Confere permissões no arquivo de Instalação

`chmod +x install.sh`

1.9 Roda o script de Instalação

`./install.sh`

Principais comandos
------------------------------------------

Comandos úteis na administração do Zimbra.

Descobrir qual é a versão e arquitetura do seu Zimbra:

`zmcontrol -v`

Comando para Iniciar o server:

`/etc/init.d/zimbra start` ou `zmcontrol start`

Parar o servidor

`/etc/init.d/zimbra stop` ou `zmcontrol stop`

Reiniciar o servidor:

`/etc/init.d/zimbra restart` ou `zmcontrol restart`

Checar o status do servidor:

`/etc/init.d/zimbra status` ou `zmcontrol status`

Obter ajuda do comando zmprov

`zmprov help commands`

Obter opções de uso do e a sintaxe de comandos do zmprov:

`zmprov -h`

Trocar o nome da máquina do Zimbra:

`/etc/init.d/zimbra stop ; /opt/zimbra/libexec/zmsetservername -o antigo.dominio.com -n novo.dominio.com`

Obter nome da máquina do Zimbra:

`zmhostname`

Listar todos os domínios no Zimbra:

`zmprov gad`

Criar outro domínio:

`zmprov cd dominio.org.br`

Renomear um domínio:

`zmprov -l rd dominio.org.br dominio.net.br`

Criar alias para domínio:

`zmprov cad alias_dominio.com.br dominio.com.br`

Verificar qual o domínio padrão do Zimbra:

`zmprov gacf zimbraDefaultDomainName`

Para remover um domínio ou um alias de domínio:

`zmprov dd alias_dominio.com.br`

Criar usuario:

`zmprov ca usuario@dominio.com.br 'senhaaqui'`

Alterar a senha de um usuário:

`zmprov sp usuario@dominio.com.br 'dominio.usuario'`

Listar todos usuarios:

`zmprov -l gaa`

Listar todos os usuários de um domínio:

`zmprov -l gaa dominio.com.br`

Listar usuários que são administradores:

`zmprov -l gaaa`

Transformar um usuario em administrador:

`zmprov -l gaaa dominio.com.br`

Criar um usuario com o atributo de administrador

`zmprov ma usuario@dominio.com.br zimbraIsAdminAccount TRUE`

Renomear conta:

`zmprov ca usuario@dominio.com.br 'senhaaqui' zimbraIsAdminAccount TRUE`

Renomer conta mudando de domínio:

`zmprov ra usuario@dominio.com.br usuario1@dominio.com.br`

Deletar Conta:

zmpra da <usuario@dominio.com.br>

Visualizar atributos de uma conta:

`zmprov ga usuario@dominio.com.br`

Adicionar alias a uma conta:

`zmprov aaa usuario@dominio.com.br alias_usuario@dominio.com.br`

Listar os alias:

`for i in $(zmprov -l gaa); do echo -e "\n$i:"; zmprov ga $i | grep MailAlias; done`

Listar os alias de um determinado domínio:

`for i in $(zmprov -l gaa dominio.com); do echo -e "\n$i:"; zmprov ga $i | grep MailAlias; done`

Remover alias

`zmprov raa usuario@dominio.com.br alias_usuario@dominio.com.br`

Para criar uma lista:

`zmprov cdl lista@dominio.com.br`

Visualizar listas de distribuição:

`zmprov gadl`

Adicionar membros à lista de distribuição:

`zmprov adlm lista@dominio.com.br usuario@dominio.com.br`

Adicionar um usuario a todas as listas de distribuição:

`for listas in $(zmprov gadl); do zmprov adlm $listas usuario@dominio.com.br; done`

Ver todas as informações de uma lista:

`zmprov gdlm lista@dominio.com.br`

Ver todas as informações de uma lista:

`zmprov gdl lista@dominio.com.br`

Remover membro de uma lista:

`zmprov rdlm lista@dominio.com.br lista@dominio.com.br`

Renomear uma lista de distribuição:

`zmprov rdl lista@dominio.com.br novalista@dominio.com.br`

Ocultar uma lista de distribuição da GAL:

`zmprov mdl lista@dominio.com.br  zimbraHideInGal TRUE`

Exibir uma lista de distribuição da GAL:

`zmprov mdl lista@dominio.com.br  zimbraHideInGal FALSE`

Remover uma lista:

`zmprov ddl lista@dominio.com.br`

Listar Classes:

`zmprov gac`

Criar uma nova COS:

`zmprov cc nome_da_classe`

Ver todos os atributos de uma classe:

`zmprov gc nome_da_classe`

Alterar a COS de um usuário:

`zmprov sac usuario@dominio.com.br nova_classe`

Para ver quantos usuários de um dominio estão em classes:

`zmprov cta dominio.com.br`

Obter o atributo da quota da COS:

`zmprov gc nome_classe zimbraMailQuota`

Obter cuota utilizada por cada usuário de um domínio (Formato Conta Quota Quota Utilizada):

`zmprov gqu localhost`

Alterar attribute de quota para o valor de 80M, este número deve ser em
bytes

`zmprov mc nome_da_classe zimbraMailQuota 83886080`

Checar se a quota foi alterada

`zmprov gc nome_da_classe zimbraMailQuota`

Para ver a cuota de cada usuario, vocee pode usar o comando:

`for i in $(zmprov -l gaa); do zmprov ga $i zimbraMailQuota; done`

Trocar a senha de administrador:

`zmprov sp admin@dominio.com.br 'senhaaqui'`

Logs de entrega de email na caixa (LMTP) Login e Logout Imap/Pop/Mapi, Erros
na aplicação java, operações de indexação, lentidão no banco de dados (slow
queries) e outros

`tail -f /opt/zimbra/log/mailbox.log`

Logs de atividade do postfix, status dos serviços, atividades do antivirus e antispam e outros:

`tail -f /opt/zimbra/log/zimbra.log`

Logs de autenticação:

`tail -f /opt/zimbra/log/audit.log`

Logs do antivirus db:

`tail -f /opt/zimbra/log/clamd.log`

Logs de atualizaçao do Antivirus Clamav

`tail -f /opt/zimbra/log/freshclam.log`

Logs ao DB do store que estão demorando

`tail -f /opt/zimbra/log/myslow.log`

Logs de treinamento do Antispam

`tail -f /opt/zimbra/log/spamtrain.log`

Ativar somente o acesso http:

`zmtlsctl http ; zmcontrol restart`

Ativar somente o acesso https:

`zmtlsctl https ; zmcontrol restart`

Ativa o acesso http e https:

`zmtlsctl mixed ; zmcontrol restart`

Logs
----------------------

Pastas de logs do zimbra

`/var/zimbra/log/audit.log`

`/var/zimbra/log/zimbra.log`

`/opt/zimbra/log/mailbox.log`

### Ubuntu e Debian

`/var/zimbra/log/mail.log`

### CentOS

`/var/zimbra/log/maillog`

FONTE:
--------------------------

* <https://linuxrede.wordpress.com/2014/02/22/lista-de-comandos-zimbra/https://linuxrede.wordpress.com/2014/02/22/lista-de-comandos-zimbra/>

* <https://www.youtube.com/watch?v=ozR7cDYFJsU>
