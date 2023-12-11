MiniDLNA
=================================

1 Instalação
-----------------------------

`sudo apt-get install minidlna -y`

2 Configuração
-----------------------------

2.1 Edite o arquivo **/etc/minidlna.conf**

`sudo vim /etc/minidlna.conf`

Descomentar e editar o parametro

```

Como é          | Como deve ficar
----------------|-------------------
#user=minidlna  | user=root
#db_dir=...     | db_dir=...
#log_dir=...    | log_dir=...
#friendly_name= | friendly_name=NOME_DO_SERVIDOR
media_dir=...   | media_dir=/CAMINHO/DOS/ARQUIVOS

```

2.2 Edite o arquivo /etc/default/minidlna

`sudo nano /etc/default/minidlna`

```

Como é                           | Como deve ficar
---------------------------------|-------------------
#USER="minidlna"                 | USER="root"
START_DAEMON="yes"               | START_DAEMON="yes"
#CONFIGFILE="/etc/minidlna.conf" | CONFIGFILE="/etc/minidlna.conf" 
#LOGFILE="/var/log/minidlna.log" | LOGFILE="/var/log/minidlna.log"
#DAEMON_OPTS="-r"                | DAEMON_OPTS="-r"

```

2.3 Restart o servico

`sudo service minidlna restart`

2.4 Programe para iniciar o servico junto com o sistema

`sudo service minidlna force-reload`

3 Exemplo
-----------------------------

```

# This is the configuration file for the MiniDLNA daemon, a DLNA/UPnP-AV media
# server.
#
# Unless otherwise noted, the commented out options show their default value.
#
# On Debian, you can also refer to the minidlna.conf(5) man page for
# documentation about this file.

# Specify the user name or uid to run as.
user=root

# Path to the directory you want scanned for media files.
#
# This option can be specified more than once if you want multiple directories
# scanned.
#
# If you want to restrict a media_dir to a specific content type, you can
# prepend the directory name with a letter representing the type (A, P or V),
# followed by a comma, as so:
#   * "A" for audio    (eg. media_dir=A,/var/lib/minidlna/music)
#   * "P" for pictures (eg. media_dir=P,/var/lib/minidlna/pictures)
#   * "V" for video    (eg. media_dir=V,/var/lib/minidlna/videos)
media_dir=/media/luizotavio/FILMES_EXTERNO

# Path to the directory that should hold the database and album art cache.
db_dir=/var/cache/minidlna

# Path to the directory that should hold the log file.
log_dir=/var/log

# Type and minimum level of importance of messages to be logged.
#
# The types are "artwork", "database", "general", "http", "inotify",
# "metadata", "scanner", "ssdp" and "tivo".
#
# The levels are "off", "fatal", "error", "warn", "info" or "debug".
# "off" turns of logging entirely, "fatal" is the highest level of importance
# and "debug" the lowest.
#
# The types are comma-separated, followed by an equal sign ("="), followed by a
# level that applies to the preceding types. This can be repeated, separating
# each of these constructs with a comma.
#
# The default is to log all types of messages at the "warn" level.
#log_level=general,artwork,database,inotify,scanner,metadata,http,ssdp,tivo=warn

# Use a different container as the root of the directory tree presented to
# clients. The possible values are:
#   * "." - standard container
#   * "B" - "Browse Directory"
#   * "M" - "Music"
#   * "P" - "Pictures"
#   * "V" - "Video"
# If you specify "B" and the client device is audio-only then "Music/Folders"
# will be used as root.
#root_container=.

# Network interface(s) to bind to (e.g. eth0), comma delimited.
# This option can be specified more than once.
#network_interface=

# IPv4 address to listen on (e.g. 192.0.2.1/24).
# If omitted, the mask defaults to 24. The IPs are added to those determined
# from the network_interface option above.
# This option can be specified more than once.
#listening_ip=

# Port number for HTTP traffic (descriptions, SOAP, media transfer).
# This option is mandatory (or it must be specified on the command-line using
# "-p").
port=8200

# URL presented to clients (e.g. http://example.com:80).
#presentation_url=/

# Name that the DLNA server presents to clients.
# Defaults to "hostname: username".
friendly_name=MeuServidorDLNA

# Serial number the server reports to clients.
# Defaults to 00000000.
serial=681019810597110

# Model name the server reports to clients.
#model_name=Windows Media Connect compatible (MiniDLNA)

# Model number the server reports to clients.
# Defaults to the version number of minidlna.
#model_number=

# Automatic discovery of new files in the media_dir directory.
#inotify=yes

# List of file names to look for when searching for album art.
# Names should be delimited with a forward slash ("/").
# This option can be specified more than once.
album_art_names=Cover.jpg/cover.jpg/AlbumArtSmall.jpg/albumartsmall.jpg
album_art_names=AlbumArt.jpg/albumart.jpg/Album.jpg/album.jpg
album_art_names=Folder.jpg/folder.jpg/Thumb.jpg/thumb.jpg

# Strictly adhere to DLNA standards.
# This allows server-side downscaling of very large JPEG images, which may
# decrease JPEG serving performance on (at least) Sony DLNA products.
#strict_dlna=no

# Support for streaming .jpg and .mp3 files to a TiVo supporting HMO.
#enable_tivo=no

# Notify interval, in seconds.
#notify_interval=895

# Path to the MiniSSDPd socket, for MiniSSDPd support.
#minissdpdsocket=/run/minissdpd.sock

```

Fontes
-----------------------------

* <https://www.todoespacoonline.com/w/2015/05/servidor-dlna-no-ubuntu-minidlna/>

* <https://www.youtube.com/watch?v=vnREG-YWiKE>
