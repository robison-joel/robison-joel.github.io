CentOS 7
==========

## 1 Configurar a rede

1.1 Rodar o __nmtui__ para a configuração de rede.

`nmtui`

1.2 Restart no serviço de rede para que as mudanças sejam efetivas.

`service network status`

1.3 Comandos para administrar o serviço de rede:

1.3.1 Para testar a configuração.

`service network try-restart`

1.3.2 Para reiniciar.

`service network restart`

1.3.3 Para iniciar.

`service network start`

1.3.4 Para parar.

`service network stop`

1.3.5 Para forçar o reinicio.

`service network force-reload`

2 Atualizar
-------------------------------------------

2.1 Atualizar os repositórios

`yum check-update`

2.2 Atualizar o sistema.

`yum upgrade`
