# No-IP

No Ubuntu
------------------------------------------

No Debian
------------------------------------------

#### Instalação

Atualiza os repositórios.

`apt update`

Instala dependências

`apt install make`

`apt install gcc`

Entra na pasta onde vai ser instalado

`cd /usr/local/src`

Baixa o NOIP_DUC

`wget http://www.no-ip.com/client/linux/noip-duc-linux.tar.gz`

Descompacta

`tar xzf noip-duc-linux.tar.gz`

Entra na pasta descompactada

`cd noip-2.1.9-1`

Instala

`make`

`make install`

Ao fim da instalação, será necessário se conectar no no-ip, colocando o e-mail e a senha utilizadas para fazer login no site do No-ip.

A saída será semelhante a essa:

```

if [ ! -d /usr/local/bin ]; then mkdir -p /usr/local/bin;fi
if [ ! -d /usr/local/etc ]; then mkdir -p /usr/local/etc;fi
cp noip2 /usr/local/bin/noip2
/usr/local/bin/noip2 -C -c /tmp/no-ip2.conf

Auto configuration for Linux client of no-ip.com.
```

Nesse momento, insira suas credenciais do no-ip.

> Please enter the login/email string for no-ip.com  `email@dominio.com` (e-mail usado no cadastro do no-ip)
> Please enter the password for user '<rjgsinfo@gmail.com>'  `***********` (senha criada no cadastro do no-ip)

E a configuração será finalizada assim:

```
Only one host [rjgs.ddns.net] is registered to this account.
It will be used.
Please enter an update interval:[30]  15
Do you wish to run something at successful update?[N] (y/N)  y
Please enter the script/program name  

New configuration file '/tmp/no-ip2.conf' created.

mv /tmp/no-ip2.conf /usr/local/etc/no-ip2.conf
```
