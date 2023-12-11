Falha na Interface Gráfica
============================================================================

1 Problema
------------------------------------------------------------

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

Fonte
----------------------------------------------------------------

* <http://maguscode.blogspot.com>
