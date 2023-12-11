Drivers Nvidia no Ubuntu
===============================

## 1. Atualize os programas e o sistema.
 
`sudo apt update && sudo apt upgrade`

## 2. Identifique qual é a sua placa vídeo e qual o driver recomendado:

`ubuntu-drivers devices | grep "recommended" | awk '{print $3}'`

o comando acima vai retornar qual a versão do driver recomendado para o seu componente.

## 3. Instale o driver recomendado:

`sudo apt install nvidia-driver-'driverrecomendado'`
