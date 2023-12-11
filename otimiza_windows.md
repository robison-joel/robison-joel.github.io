Otimizando o Windows.
===========================

Este procedimento é de complexidade média e servirá para otimizar o funcionamento e a interação do seu Windows 10. 

## 1 NO CMD

1.2 Reparando arquivos diretamente da base atualizada da Microsoft

Para fazer esse reparo, utilize o comando abaixo pressionando Enter:

`DISM /Online /Cleanup-image /Restorehealth`

1.3 Verificando arquivos corrompidos

`sfc /scannow`

1.4 Verificação de disco:

`chkdsk c:/f`

## 2 EXECUTAR

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



