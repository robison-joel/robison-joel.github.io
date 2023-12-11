Manutenção Linux
===================================

1 Verificação de temperatura
-----------------------------------

### 1.1 Temperatura do CPU

Para a verificação da temperatura da CPU e seus núcleos utilizamos a ferramenta "lm-sensors".

1.1.1 Instalação

`sudo apt install lm-sensors`

1.1.2 Utilização

O comando abaixo faz uma varredura de todos os sensores que o seu computador ou servidor possuem.

`sudo sensors-detect`

Após a varredura, exibimos os valores na tela do terminal

`sensors`

O comando abaixo mostra os índices em tempo real.

`watch sensors`

### 1.2 Temperatura do HD


Para a verificação da temperatura do HD, devemos utilizar o recurso hddtemp.

1.2.1 Instalação.

`apt install hddtemp`

1.2.2 Uso

Para usá-lo é preciso saber o nome do disco que você vai monitorar, usando o comando abaixo:

`lsblk`

A saída do comando será similar a essa:

```
NAME                     MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
sda                        8:0    0 21,9T  0 disk 
├─sda1                     8:1    0  512M  0 part /boot/efi
├─sda2                     8:2    0  732M  0 part /boot
└─sda3                     8:3    0 21,8T  0 part 
  ├─srvmaster--vg-root   252:0    0 21,8T  0 lvm  /
  └─srvmaster--vg-swap_1 252:1    0  976M  0 lvm  [SWAP]
sr0                       11:0    1 1024M  0 rom  
```

Agora que você já sabe qual disco, execute o comando com o caminho do mesmo.

`hddtemp /dev/xxx`

Fonte
--------------------------------------------------------------

* <https://br.ccm.net/faq/15768-linux-ver-a-temperatura-do-cpu>

* <https://www.youtube.com/watch?v=ygwbi7gJCh0>

* <https://dicasrapidas.com.br/dicas-linux/como-saber-a-temperatura-do-hd-no-linux.html>

