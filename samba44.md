SAMBA 4
==========

1 Instalação
-------------

### 1.1 Pre-instalação

Preparação do ambiente para a instalação. Aconselhamos a executar os comandos no modo sudo, individualmente.

```apt-get install build-essential```

```apt-get install libacl1-dev```

```apt-get install libattr1-dev```

```apt-get install libblkid-dev```

```apt-get search libgnutls-dev```

```apt-get install libreadline-dev```

```apt-get install python-dev```

```apt-get install python-dnspython```

```apt-get install gdb```

```apt-get install pkg-config```

```apt-get install libpopt-dev```

```apt-get install libldap2-dev```

```apt-get install libgnutls28-dev```

```apt-get install libpam-cracklib```

```apt-get install libpam-doc```

```apt-get install libpam-modules```

```apt-get install libpam-modules-bin```

```apt-get install libpam-runtime```

```apt-get install libpam0g```

```apt-get install libpam0g-dev```

---------

### 1.2 Executa a instalação

1.2.1 Cria o diretório para baixar o SAMBA4

```mkdir .samba4```

1.2.2 Entra na pasta

```cd .samba4```

1.2.3 Baixar o SAMBA4

```wget https://download.samba.org/pub/samba/samba-latest.tar.gz```

1.2.4 Descompactar

```tar xvfz samba-latest.tar.gz```

1.2.5 Entra da pasta extraída

```cd samba(tab)```

1.2.6 Compile com os seguintes comandos

```./configure --enable-debug```

```make ; make install```

Fonte
----------

* <https://google.com.br/>
