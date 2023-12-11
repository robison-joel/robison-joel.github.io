Proxmox
====================================

Instalação
------------------------------------

Troubleshooting
------------------------------------

A resposta está de fato na página [Package_Repositories](https://pve.proxmox.com/wiki/Package_Repositories)

<https://pve.proxmox.com/wiki/Package_Repositories>

Editar minha lista de repositórios em /etc/apt/sources.list conforme:

`vim /etc/apt/sources.list`

```
deb http://ftp.br.debian.org/debian bullseye main contrib

deb http://ftp.br.debian.org/debian bullseye-updates main contrib

# Repositório PVE pve-no-subscription fornecido por proxmox.com,
# Nao recomendado para uso em produção
deb http://download.proxmox.com/debian/pve bullseye pve-no-subscription

# security updates
deb http://security.debian.org bullseye-security main contrib
```

E também deve comentar a linha listada em `/etc/apt/sources.list.d/pve-enterprise.list`.

`vim /etc/apt/sources.list`

Ficando dessa forma:

```
#deb https://enterprise.proxmox.com/debian/pve bullseye pve-enterprise
```

Fonte
---------------------------------------

* <https://forum.proxmox.com/threads/update-unauthorized-after-latest-update.61584/>
