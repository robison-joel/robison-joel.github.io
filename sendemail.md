sendEmail
===============

1 O que é?
--------------------------

Script que envia email pelo terminal

2 Créditos
--------------------------

sendEmail-1.56 by Brandon Zehm <caspian@dotconf.net>

3 Instalação
--------------------------

`sudo apt-get install sendemail`

3 Sintaxe
--------------------------

`sendEmail -f ADDRESS [options]`

4 Instruções (ManPage)
--------------------------

Aqui há uma reproduçao do comando sendemail --help.

Required:

* -f ADDRESS - from (sender) email address

* At least one recipient required via -t, -cc, or -bcc

* Message body required via -m, STDIN, or -o message-file=FILE

Common:

* -t ADDRESS [ADDR ...]     to email address(es)

* -u SUBJECT                message subject

* -m MESSAGE                message body

* -s SERVER[:PORT]          smtp mail relay, default is localhost:25

* -S [SENDMAIL_PATH]        use local sendmail utility (default: /usr/bin/sendmail) instead of network MTA

Optional:

* -a   FILE [FILE ...]      file attachment(s)

* -cc  ADDRESS [ADDR ...]   cc  email address(es)

* -bcc ADDRESS [ADDR ...]   bcc email address(es)

* -xu  USERNAME             username for SMTP authentication

* -xp  PASSWORD             password for SMTP authentication

Paranormal:

* -b BINDADDR[:PORT]        local host bind address

* -l LOGFILE                log to the specified file

* -v                        verbosity, use multiple times for greater effect

* -q                        be quiet (i.e. no STDOUT output)

* -o NAME=VALUE             advanced options, for details try: --help misc

  * -o message-content-type=<auto|text|html>

  * -o message-file=FILE         -o message-format=raw

  * -o message-header=HEADER     -o message-charset=CHARSET

  * -o reply-to=ADDRESS          -o timeout=SECONDS

  * -o username=USERNAME         -o password=PASSWORD

  * -o tls=<auto|yes|no>         -o fqdn=FQDN

Help:

* --help                    the helpful overview you're reading now

* --help addressing         explain addressing and related options

* --help message            explain message body input and related options

* --help networking         explain -s, -b, etc

* --help output             explain logging and other output options

* --help misc               explain -o options, TLS, SMTP auth, and more

Fontes
------------------------------

* <https://www.vivaolinux.com.br/artigo/Enviando-emails-pelo-terminal>
