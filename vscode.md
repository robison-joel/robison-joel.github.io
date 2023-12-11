Visual Studio Code
======================================================

1 Instalação
----------------------------------------------------------------

1.1 Crie a pasta que vai receber o arquivo de Instalação.

`sudo mkdir .vscode`

1.2 Entra na pasta

`cd .vscode/`

1.3 Faz o download do arquivo deinstalação.

`sudo wget https://az764295.vo.msecnd.net/stable/c3511e6c69bb39013c4a4b7b9566ec1ca73fc4d5/code_1.67.2-1652812855_amd64.deb`

> Caso o link acima esteja desatualizado procure o mais recente em: 

1.4 Concede permissão de execução ao arquivo.

`sudo chmod +x code_1.67.2-1652812855_amd64.deb`

1.5 Executa

`sudo dpkg -i code_1.67.2-1652812855_amd64.deb`

1.6 Instala dependêcias, caso hajam.

`sudo apt install -f -y`

1.7 Atualiza.

`sudo apt update ; apt list --upgradable ; sudo apt upgrade -y`

1.8 Caso queira, após a instalação você pode deletar os arquivos de instalação.

`cd ..`

`sudo rm -rf .vscode`

2 Atalhos do VSCode
------------------------------------------------------

2.1 Geral

* Ctrl + Shift + P, = paleta de comando F1 Show.

* Ctrl + P Quick Open, = vá para o arquivo ...

* Ctrl + Shift + N = Nova janela / instância.

* Ctrl + Shift + W = Fechar janela / instância.

* Ctrl +, = configurações do usuário.

* Ctrl + K Ctrl + S = Atalhos de teclado.

2.2 Edição básica

* Ctrl + X = Linha de corte (seleção vazia) 

* Ctrl + C = Copiar linha (seleção vazia) 

* Alt + ↑ / ↓ = Mover linha para cima / baixo 

* Shift + Alt + ↓ / ↑ = Copiar linha para cima / baixo 

* Ctrl + Shift + K = Excluir linha 

* Ctrl + Enter = Inserir linha abaixo 

* Ctrl + Shift + Enter = Inserir linha acima 

* Ctrl + Shift + \ = Ir para o suporte correspondente 

* Ctrl +] / [linha Indent / outdent 

* Home / End = Ir para o começo / fim da linha 

* Ctrl + Home = Ir para o início do arquivo 

* Ctrl + End = Ir para o final do arquivo 

* Ctrl + ↑ / ↓ = Linha de rolagem para cima / baixo

* Alt + PgUp / PgDn Rola a página para cima / baixo

* Ctrl + Shift + [Dobre (colapse) a região

* Ctrl + Shift +] Desdobrar (uncollapse) região

* Ctrl + K Ctrl + [Dobre (reduza) todas as sub-regiões

* Ctrl + K Ctrl +] Desdobra (uncollapse) todas as sub-regiões

* Ctrl + K Ctrl + 0 Dobre (reduza) todas as regiões

* Ctrl + K Ctrl + J Desdobra (uncollapse) todas as regiões

* Ctrl + K Ctrl + C Adicionar comentário de linha

* Ctrl + K Ctrl + U Remover comentário de linha 

* Ctrl + / Alternar comentário de linha 

* Shift + Alt + A Alternar comentário do bloco 

* Alt + Z Toggle quebra automática de palavras 

2.3 Navegação

* Ctrl + T = Mostrar todos os símbolos 

* Ctrl + G = Ir para linha ... 

* Ctrl + P = Ir para arquivo ... 

* Ctrl + Shift + O = Ir para o símbolo ... 

* Ctrl + Shift + M cMostrar painel de problemas 

* F8 = Ir para o próximo erro ou aviso 

* Shift + F8 = Ir para erro ou aviso anterior 

* Ctrl + Shift + Tab = Navegar pelo histórico do grupo de editor 

* Alt + ← / → = Retroceder / avançar 

* Ctrl + M = Toggle Tab move o foco 

2.4 Pesquise e substitua

* Ctrl + F = Encontrar 

* Ctrl + H = Substituir 

* F3 / Shift + F3 = Encontrar próximo / anterior 

* Alt + Enter = Seleciona todas as ocorrências de Encontrar correspondência

* Ctrl + D = Adicionar seleção ao próximo Encontrar jogo

* Ctrl + K Ctrl + D = Move a última seleção para a próxima Find match 

* Alt + C / R / W = Alternar maiúsculas / minúsculas / regex / palavra inteira

2.5 Multi-cursor e seleção

* Alt + Clique no cursor Inserir 

* Ctrl + Alt + ↑ / ↓ Inserir cursor acima / abaixo 

* Ctrl + U Desfazer a última operação do cursor 

* Shift + Alt + I Insere o cursor no final de cada linha selecionada 

* Ctrl + I Seleciona a linha atual 

* Ctrl + Shift + L Seleciona todas as ocorrências da seleção atual 

* Ctrl + F2 Seleciona todas as ocorrências da palavra atual 

* Shift + Alt + → Expandir seleção 

* Shift + Alt + ← Seleção de encolhimento 

* Shift + Alt + (arraste o mouse) = Seleção de coluna (caixa) 

* Ctrl + Shift + Alt + (tecla de seta) = Seleção de coluna (caixa) 

* Ctrl + Shift + Espaço = Dicas do parâmetro do acionador 

* Shift + Alt + F = Formatar documento.

* Ctrl + K Ctrl + F = Seleção de formato.

* F12 = Ir para definição.

* Alt + F12 = Peek Definition.

* Ctrl + K F12 = Abrir Definição para o lado.

* Shift + F12 = Mostrar referências.

* F2 = Renomear Símbolo.

* Ctrl + K Ctrl + X = Cortar espaços em branco à direita.

* Ctrl + K + M = Alterar idioma do arquivo.

2.6 Gerenciamento de editor

* Ctrl + F4, Ctrl + W Fechar editor.

* Ctrl + K F Fechar pasta.

* Ctrl + \ Split editor.

* Ctrl + K Ctrl + ← / → = Concentra-se no grupo de editores anterior / seguinte.

* Ctrl + Shift + PgUp / PgDn = Mover editor para a esquerda / direita.

* Ctrl + K ← / → = Mover o grupo do editor ativo 

2.7 Gerenciamento de arquivos

* Ctrl + N = Novo Arquivo 

* Ctrl + O = Abrir arquivo ... 

* Ctrl + S = Salvar 

* Ctrl + Shift + S = Salvar como ... 

* Ctrl + K + S = Salvar tudo 

* Ctrl + F4 = Close 

* Ctrl + K Ctrl + W = Fechar tudo 

* Ctrl + Shift + T = Reabrir editor fechado 

* Ctrl + K + Enter = Manter o editor do modo de visualização aberto 

* Ctrl + Tab = Aberto ao lado 

* Ctrl + Shift + Tab = Abrir anterior 

* Ctrl + K + P = Caminho de cópia do arquivo ativo 

* Ctrl + K + R = Revela o arquivo ativo no Explorer 

* Ctrl + K + O = Mostra o arquivo ativo em uma nova janela / instância 


2.8 Exibição

* F11 = Alternar tela cheia.

* Shift + Alt + 0 = Alternar o layout do editor (horizontal / vertical).

* Ctrl + "+" ou "-" = Zoom in / out.

* Ctrl + B = Alterna a visibilidade da barra lateral.

* Ctrl + Shift + E = Mostrar o Explorer / Alternar o foco.

* Ctrl + Shift + F = Mostrar pesquisa.

* Ctrl + Shift + G = Mostrar controle de código-fonte.

* Ctrl + Shift + D = Mostrar depuração.

* Ctrl + Shift + X = Mostrar extensões.

* Ctrl + Shift + H = Substituir nos arquivos.

* Ctrl + Shift + J = Toggle Detalhes da pesquisa.

* Ctrl + Shift + U = Mostrar painel de saída.

* Ctrl + Shift + V = Abra a pré-visualização do Markdown.

* Ctrl + K + V = Abre a pré-visualização do Markdown para o lado.

* Ctrl + K + Z = Modo Zen (Esc Esc para sair).


2.9 Depurar

* F9 = Alternar ponto de interrupção.

* F5 = Iniciar / Continuar.

* Shift + F5 = Stop.

* F11 / Shift + F11 = Passo para dentro / fora.

* F10 = Passar por cima.

* Ctrl + K Ctrl + I = Mostrar o cursor.

2.10 Terminal integrado

* Ctrl + ` = Mostrar terminal integrado 

* Ctrl + Shift + ` = Criar novo terminal 

* Ctrl + C = Copiar seleção 

* Ctrl + V = Cole no terminal ativo 

* Ctrl + ↑ / ↓ = Rola para cima / baixo 

* Shift + PgUp / PgDn = Rola a página para cima / baixo 

* Ctrl + Home / End = Rola para cima / baixo

Fonte
----------------------------------------------------------------

