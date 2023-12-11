WINDOWS 10
===============================================

GPEDIT
--------------------------------------------------

Instalar e ativar o gpedit.msc no Windows 10 e Windows 11.

As versões posteriores ao Windows 8 não contam com o Editor de Política de Grupo Local (gpedit) ativado por padrão. Abaixo o procedimento para ativá-lo no Windows 10 e Windows 11.

Abra o CMD:

* Método 1: Clique no menu iniciar > pesquisar. Na caixa de pesquisa  escreva "cmd.exe" e aperte enter.

* Método 2: Aperte a `Tecla do Windows` + `r` para abrir o pop-up do Executar. Escreva cmd.exe e aperte o enter.

Vai abrir a janela do command.exe ou cmd. Nela escreva o comando abaixo.

> Sim. É possível copiar e colar. Mas não seria mais interessante escrevê-lo?

`FOR %F IN ("%SystemRoot%\servicing\Packages\Microsoft-Windows-GroupPolicy-ClientTools-Package~*.mum") DO (DISM /Online /NoRestart /Add-Package:"%F")`

Aguarde até aparecer a mensagem “A operação foi concluída com êxito.”

Agora digite o comando abaixo e aperte enter:

`FOR %F IN ("%SystemRoot%\servicing\Packages\Microsoft-Windows-GroupPolicy-ClientExtensions-Package~*.mum") DO (DISM /Online /NoRestart /Add-Package:"%F")`

Aguarde a confirmação de instalação com exito.

Para abrir o gpedit escreva `gpedit.msc` no cmd ou no pop-up do Executar.

Instalar o RDP no Windows 10
---------------------------------------------------------------

1 Crie a pasta **RDP Wrapper** onde serão descompactados os arquivos baixados. Posteriormente ela será movida para `C:\Arquivos de programas` (ou C:\\Program Files) pois o programa somente será executado da forma correta neste local.

> Será necessário efetuar ajustes nas excessões no Windows Defender para evitar que os arquivos sejam excluídos.

2 Baixe os arquivos [RDPWrap-v1.6.2.zip](https://github.com/stascorp/rdpwrap/releases/download/v1.6.2/RDPWrap-v1.6.2.zip) e  [autoupdate.zip](https://raw.githubusercontent.com/asmtron/rdpwrap/master/autoupdate.zip) extraindo-os na pasta **RDP Wrapper**.

3 Com os arquivos todos extraídos na pasta “**RDP Wrapper**” vamos copiá-la para `C:\Arquivos de programas`.

4 Dentro de "C:\\Arquivos de programas\\RDP Wrapper" clique com o botão direito no arquivo `autoupdate__enable_autorun_on_startup.bat` e selecione a opção Executar como administrador para ativar a opção de atualização automática do RDP Wrapper.

5 Em seguida clique com o botão direito no arquivo `autoupdate.bat` e selecione a opção “Executar como administrador” para instalar e atualizar a conexão remota do Windows 10 em seu computador.

6 Para testar se a conexão remota está funcionando, execute o arquivo RDPCHeck.exe e na janela aberta, clique em “Conectar”. Ao fazer isso, será exibida a tela de login do Windows.

Atalhos de teclado
-------------------------------------------------

***Seleção***

Tecla          | Ação
---------------|---------------------------------------
CTRL + A       | Seleciona tudo;
CTRL + C       | Copia o que está selecionado;
CTRL + Insert  | Copia o que está selecionado;
CTRL + X       | Corta o que está selecionado;
CTRL + V       | Cola o conteúdo da área de transferência. Normalemnte isso é o que foi copiado ou recortado;
SHIFT + Insert | Cola o conteúdo da área de transferência. Normalemnte isso é o que foi copiado ou recortado;

***Ações***

Tecla                           | Ação
--------------------------------|---------------------------------------
CTRL + Z                        | Ação de desfazer a última ação;
CTRL + Y                        | Refaz (repete) a última ação;
CTRL + SHIFT + N                | Cria uma nova pasta no diretório atual;
ALT + F4                        | Fecha a janela principal e também abre o popup de desligamento de sistema;
CTRL + D                        | Envia os arquivos selecionaos para a lixeira;
SHIFT + Delete                  | Apaga definitivamente o(s) ítem(ns) selecionado(s);
F2                              | Renomeia o ítem selecionado;
Esc                             | Cancela a tarefa atual. Também é usada para sair da tela cheia;
ALT + TAB                       | Alterna entre as janelas abertas;
PrScn (Print Screen)            | Faz uma captura de tela do seu computador;
Tecla Windows + I               | Abre as configurações do Windows;
Tecla Windows + E               | Abre o explorador de arquivos;
Tecla Windows + A               | Abre a Central de Ações;
Tecla Windows + D               | Mostra a Área de Trabalho (minimiza todas as janelas abertas);
Tecla Windows + L               | Bloqueia a sessão atual;
Tecla Windows + V               | Abre o histórico da área de transferência;
Tecla Windows + . ou ;          | Abre o painel de emojis;
Tecla Windows + PrtScn          | Tira um print da tela;
Tecla Windows + SHIFT + S       | Abre a ferramenta de captura de tela;
Tecla Windows + Seta á esquerda | Ajusta a janela atual na lateral esquerda da tela atual;
Tecla Windows + Seta á direita  | Ajusta a janela atual na lateral direita da tela atual;
Tecla Windows + 1 a 9           | Abre o aplicativo correspondente ao numeral na sequência disposta dos ícones da barra de ferramentas;
Tecla Windows + T               | Alterna seleção entre os aplicativos da barra de ferramentas;
Tecla Windows + ALT + 1 a 9     | Abre o menu de contexto de cada aplicativo correspondente ao numeral na sequência disposta dos ícones da barra de ferramentas;

Alterar a senha
-----------------------------

Alterar senha de usuário do Windows via linha de comando.

primeiro liste os usuários da maquina:

`net user`

depois use o comando para alterar a senha

`net user nome-do-usuario *`

e digite a senha duas vezes.

fonte da dica: <https://youtu.be/CVfJsXJvxlY>

Montando partição windows
-----------------------------

Montando partição windows e desativando hibernar

`sudo mkdir /media/win`

`blkid`

`sudo ntfsfix /dev/sda3`

`sudo ntfs-3g -o remove_hiberfile /dev/sda /media/win`

Renomeando o cmd
-----------------------------

`cd /Windows/System32/`

`mv Utilman.exe Utilman.exe.bkp`

`cp cmd.exe Etilman.exe`

Otimizando o Windows
---------------------------------------

Este procedimento é de complexidade média e servirá para otimizar o funcionamento e a interação do seu Windows 10.

### 1 NO CMD

1.2 Reparando arquivos diretamente da base atualizada da Microsoft

Para fazer esse reparo, utilize o comando abaixo pressionando Enter:

`DISM /Online /Cleanup-image /Restorehealth`

1.3 Verificando arquivos corrompidos

`sfc /scannow`

1.4 Verificação de disco:

`chkdsk c:/f`

### 2 EXECUTAR

Para abrir a janela do comando executar, pressione: Tecla do Windows + "R"

2.1 Prefetch

É um componente do gerenciador de memória que pode acelerar o processo de inicialização do Windows e de outros programas. Para otimizar escreva este comando no "executar" e ele vai abrir uma pasta na tela. Apague todos os arquivos dela.

`prefetch`

2.2 Arquivos recentes e temporários.

Os três comandos abaixo tratam dos arquivos temporários e recentes do windows. Podem ser todos deletados. Escreva o comando no "Executar" e ao apertar enter, abrirá uma janela com os arquivos a serem apagados.

`recent`

e

`%temp%`

e

`temp`

2.3 Limpa o disco de arquivos temporários. Ao executar o comando, selecione o disco C:\ e aperte Enter.

`cleanmgr`
