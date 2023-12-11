Debian
============================================

1 Comandos
-------------------------------------------------------------

1.1 Desligar

`systemctl poweroff`

1.2 Reiniciar

`systemctl reboot`

2 Habilitar o "sudo"
----------------------------

Por questão de segurança o usuario do debian somente o root tem direitos de *superusuario*.
Para que outros usuarios tenham a capacidade de executar comandos como superusuario, utilizando o prefixo `sudo` devemos habilitar essa funcionalidade, como descrito abaixo.

### 2.1 Instalação

ascenda a root

`su`

Após colocar a senha, aperte enter.

Instale o pacote sudo:

`apt install sudo -y`

### 2.2 Configuração

Durante a insatalação do pacote, será criado o arquivo /etc/sudoers. Vamos editá-lo:

`vim /etc/sudoers`

Nele, procure a expressão

> root    ALL=(ALL:ALL) ALL".

Abaixo dela acrescente o seu registro, conforme o seu usuario (não root), respeitando a sintaxe do registro de root.

```
root    ALL=(ALL:ALL) ALL
usuario ALL=(ALL:ALL) ALL
```

Salve e feche o arquivo.

Á partir de agora, o "usuario" terá a possibilidade de usar o "sudo" para executar tarefas administrativas.

Fonte

* <https://www.edivaldobrito.com.br/como-ativar-o-sudo-no-debian/>


SE O a2enmod não funcionar:
http://pkgs.loginroot.com/errors/notFound/a2enmod
