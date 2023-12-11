Debug Linux
==========================================================

Erro de Chave Pública GPG
-----------------------------------------------------------

Ao rodar um `sudo apt update` no terminal apresenta-se um erro "As assinaturas a seguir não puderam ser verificadas devido à chave pública não estar disponível: NO_PUBKEY XXXXXXXXXXXXXXXX".

No exemplo abaixo, estou postando o erro que aconteceu na desinstalação do navegador Brave.

```
user@suporte:~$ sudo apt update
Atingido:1 https://linux.teamviewer.com/deb stable InRelease
Obter:2 https://brave-browser-apt-release.s3.brave.com stable InRelease [7.546B]                                                                                                                                 
Obter:3 https://download.docker.com/linux/ubuntu bionic InRelease [64,4 kB]                                                                                                                                       
Err:2 https://brave-browser-apt-release.s3.brave.com stable InRelease                                                                                                                                             
  As assinaturas a seguir não puderam ser verificadas devido à chave pública não estar disponível: NO_PUBKEY XXXXXXXXXXXXXXXX
Atingido:4 http://archive.ubuntu.com/ubuntu jammy InRelease                                                                                                                                               
Obter:5 https://packages.microsoft.com/repos/ms-teams stable InRelease [5.931 B]                                                                                              
Atingido:6 http://archive.ubuntu.com/ubuntu jammy-updates InRelease                                                                                 
Atingido:7 https://esm.ubuntu.com/apps/ubuntu jammy-apps-security InRelease                                      
Atingido:8 https://esm.ubuntu.com/apps/ubuntu jammy-apps-updates InRelease               
Obter:9 http://archive.ubuntu.com/ubuntu jammy-backports InRelease [109 kB]              
Atingido:10 https://ppa.launchpadcontent.net/audio-recorder/ppa/ubuntu jammy InRelease       
Atingido:11 https://esm.ubuntu.com/infra/ubuntu jammy-infra-security InRelease                                            
Atingido:12 https://esm.ubuntu.com/infra/ubuntu jammy-infra-updates InRelease                                             
Atingido:13 http://archive.ubuntu.com/ubuntu jammy-security InRelease                                                     
Atingido:14 https://ppa.launchpadcontent.net/danielrichter2007/grub-customizer/ubuntu jammy InRelease
Atingido:15 https://ppa.launchpadcontent.net/elboulangero/goodvibes/ubuntu jammy InRelease
Baixados 187 kB em 3s (62,2 kB/s)
Lendo listas de pacotes... Pronto
Construindo árvore de dependências... Pronto
Lendo informação de estado... Pronto        
4 pacotes podem ser atualizados. Corra 'apt list --upgradable' para vê-los.
W: An error occurred during the signature verification. The repository is not updated and the previous index files will be used. GPG error: https://brave-browser-apt-release.s3.brave.com stable InRelease: As assinaturas a seguir não puderam ser verificadas devido à chave pública não estar disponível: NO_PUBKEY XXXXXXXXXXXXXXXX
W: Falhou ao buscar https://brave-browser-apt-release.s3.brave.com/dists/stable/InRelease  As assinaturas a seguir não puderam ser verificadas devido à chave pública não estar disponível: NO_PUBKEY XXXXXXXXXXXXXXXX
W: Falhou o download de alguns ficheiros de índice. Foram ignorados ou os antigos foram usados em seu lugar.

```

### Solução 1

Em primeira instância, você pode tentar simplesmente reinstalar a chave com o comando abaixo, substituindo o "XXXXXXXXXXXXXXXX" pela chave que está no erro acima (sem aspas).

`sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys XXXXXXXXXXXXXXXX`

### Solução 2

Rode o apt purge para o programa

`sudo apt purge brave`

Remova o repositório

`sudo rm -r /etc/apt/sources.list.d/brave-browser-release.list`

limpe o cache do apt

`sudo apt clean`

Para validar a solução, rode o update e repare se o erro persiste.

`sudo apt update`

NTFS no Linux
-----------------------------------

Para abrir, montar e visualizar partições NTFS no linux devemos instalar o Driver **ntfs-3g**.

### 1 Instalação

`sudo apt install ntfs-3g -y`

Drivers Nvidia no Ubuntu
--------------------------------

### 1 Atualize os programas e o sistema

`sudo apt update && sudo apt upgrade`

### 2 Identifique qual é a sua placa vídeo e qual o driver recomendado

`ubuntu-drivers devices | grep "recommended" | awk '{print $3}'`

o comando acima vai retornar qual a versão do driver recomendado para o seu componente.

### 3 Instale o driver recomendado

`sudo apt install nvidia-driver-'driverrecomendado'`

Manutenção Linux
-----------------------

### 1 Verificação de temperatura

#### 1.1 Temperatura do CPU

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

#### 1.2 Temperatura do HD


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

Falha na Interface Gráfica
-----------------------------------------

### 1 Problema

Iniciar, reiniciar e desligar o modo gráfico através do terminal (Gnome)

> Dica para ambientes Gnome.

Existe momentos que a interface gráfica do Linux, por algum motivo "estranho", pode travar ou então você deseja que a mesma seja reiniciada. Uma maneira de fazer isso é:

1.1 Abra o terminal e vá até o diretório "/etc/init.d":

`cd /etc/init.d`

Neste diretório tem um arquivo que se chama "gdm", é com esse arquivo que vamos manipular a interface gráfica.

1.2 No nosso caso vamos reiniciar a interface. Para isso é basta usar o seguinte comando:

`sudo service gdm restart`

Com isso a interface gráfica será reiniciada.

2 Conteúdo adicional

Parar a interface gráfica:

`sudo service gdm stop`

Iniciar:

`sudo service gdm start`

Reiniciar:

`sudo service gdm restart`

Iniciar em modo terminal
----------------------------------------

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

FONTE
----------------------------------

* <https://br.ccm.net/faq/15768-linux-ver-a-temperatura-do-cpu>

* <https://www.youtube.com/watch?v=ygwbi7gJCh0>

* <https://dicasrapidas.com.br/dicas-linux/como-saber-a-temperatura-do-hd-no-linux.html>

* <https://community.brave.com/t/how-to-remove-brave-from-apt-get/143302>

* <https://elias.praciano.com/2015/01/como-montar-particao-ntfs-ou-vfat-no-linux/>

* <http://maguscode.blogspot.com>