Bind 9
=============================================================

[Clique aqui](https://github.com/robison-joel/Codagem/tree/main/Shell/scripts/Bind%209) para o download do script de instalação do Bind%209.

1 Instalação
-------------------------------------------------------------

1.1 Verifique o status do firewall do sistema.

`sudo ufw status`

1.2 Caso ele esteja ativo, permita o serviço.

`sudo ufw allow Bind9`

1.3 Atualize

`sudo apt update`

`apt list --upgradable`

`sudo apt upgrade`

1.4 Instale os pacotes á seguir

`apt install bind9 -y`

`apt install bind9utils -y`

`apt install bind9-doc -y`

`apt install dnsutils -y`

2 Configuração
-------------------------------------------------------------

2.1 Arquivos de configuração

/etc/bind

2.1.1 named.conf.options

`/etc/bind/named.conf.options`

Edição

`sudo vim /etc/bind/named.conf.options`

2.2.1 A diretiva "listen-on" permite especificar as redes que o DNS servidor servirá. Não escreva isso ou escreva "Any"; funcionar para todos os endereços.

```
listen-on {

10.10.10.0/24;

10.1.0.0/16;

...

};
```

2.2.2 Os encaminhadores contêm os endereços IP de DNS servidores para os quais a solicitação é redirecionada se nosso servidor não contiver os dados necessários.

```

forwarders {

8.8.8.8;

8.8.4.4;

};
```

2.2.2 named.conf

`sudo vim /etc/bind/named.conf`

2.2.3 named.conf.local

`sudo vim /etc/bind/named.conf.local`

```

zone "grayguide.local" IN { // Domain name
type master; // Primary DNS
file "/etc/bind/forward.grayguide.local.db"; // Forward lookup file
allow-update { none; }; // Since this is the primary DNS, it should be none.
}

zone "grayguide.local" IN { // Domain name
type master; // Primary DNS
file "/etc/bind/forward.grayguide.local.db"; // Forward lookup file
allow-update { none; }; // Since this is the primary DNS, it should be none.
}
```

2.3 Verifique a configuração:

`sudo named-checkconf`

> Se nenhum erro aparecer, então tudo está em ordem. Reinicie o serviço para que as alterações tenham efeito.

`sudo systemctl restart bind9`

2.4 Operação do daemon

2.4.1

`sudo systemctl start bind9`

2.4.2

`sudo systemctl status bind9`

2.4.3

`sudo systemctl stop bind9`

Fonte
---------------------------------------------------------------------

* <https://www.digitalocean.com/community/tutorials/how-to-configure-bind-as-a-private-network-dns-server-on-ubuntu-18-04-pt>

* <https://serverspace.io/pt/support/help/configure-bind9-dns-server-on-ubuntu/>
