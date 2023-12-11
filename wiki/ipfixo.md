IP Fixo - Ubuntu
==========================================================

> Este procedimeto será efetivo na versão **Ubuntu 18.04** ou superior.

1 Como configurar
----------------------------------------------------------

Para a configuração de IP fixo no Ubuntu devemos editar o arquivo de extensão __.yaml__ contido na pasta _/etc/netplan/_.

> Para este procedimento, devemos ter instalado algum editor de texto que possibilite efetuar mudanças como root.

2 Edição
----------------------------------------------------------

Certifique-se do nome do arquivo .yaml na pasta /etc/netplan.

`ls /etc/netplan`

Abra o documento para a edição.

`sudo vim /etc/netplan/*.yaml`

3 Exemplo comentado
----------------------------------------------------------

```
# This is the network config written by 'subiquity'
network:
  version: 2
  renderer: networkd
  ethernets:
    enp2s0: #----------------------------> Nome da sua interface de rede.
      addresses: [x.x.x.x/xx] #----------> IP que o computador terá.
      dhcp4: false #---------------------> Desabilita o DHCP por IPV4
      dhcp6: false #---------------------> Desabilita o DHCP por IPV6
      routes:
        - to: default
        via: x.x.x.x #----------------> IP do Gateway (IP do seu modem).
      nameservers:
        addresses: [x.x.x.x, x.x.x.x] #--> IP dos servisores de DNS - 8.8.8.8, 8.8.4.4
```

> O arquivo é sensível á erros na tabulação do arquivo. Não descuide disso.

4 Finalizando a configuração
----------------------------------------------------------

4.1 Testando a configuração

Esta opção "testa" a configuração que você fez no arquivo __.yaml__. Caso haja algo de errado, na sintaxe ou na tabulação, ele mostrará o log de erro. Se tudo estiver certo, ele vai pedir para confirmar a configuração e aplicá-la.

`sudo netplan try`

4.2 Testando a configuração, com a opção de debug (mostra os erros de forma mais completa).

`sudo netplan try --debug`

4.3 Aplica a configuração definitivamente.

`sudo netplan apply`


Fonte
----------------------------------------------------------

* <https://netplan.io/examples>
