# Définition der termes

## Surveillance (Monitoring)
La surveillance des systèmes informatiques est une pratique aussi ancienne que l’exploitation des systèmes informatiques eux-mêmes. Le processus de surveillance collecte des données sur un système afin de vérifier si celui-ci fonctionne comme prévu. Il inclut des rapports et des alertes sur les erreurs, les défauts ou les valeurs de données anormales. 
[[source: the-difference-between-monitoring-and-observabilit]](https://aws.amazon.com/fr/compare/the-difference-between-monitoring-and-observability)

## Observabilité (Observability)
L’observabilité élargit la portée et la visibilité des outils de surveillance traditionnels, en incorporant des données situationnelles et historiques supplémentaires et des interactions entre les systèmes. Elle permet de rechercher la cause racine des alertes de surveillance et d’étudier les problèmes liés aux interactions entre plusieurs composants.
[[source: the-difference-between-monitoring-and-observabilit]](https://aws.amazon.com/fr/compare/the-difference-between-monitoring-and-observability)

# Fonctionalités de Grafana

# Installer Grafana sur Windows OS

~~~ps1
winget search grafana

# Name              Id                             Version  Match        Source
# -----------------------------------------------------------------------------
# GrafanaEnterprise GrafanaLabs.Grafana.Enterprise 10.3.3.0 Tag: grafana winget
# GrafanaOSS        GrafanaLabs.Grafana.OSS        10.3.4.0 Tag: grafana winget

winget install --id GrafanaLabs.Grafana.Enterprise --exact --source winget --silent

# RootDir: C:\Program Files\GrafanaLabs\grafana
# ConfDir: ..\conf
# BinDir: ..\bin # grafana.exe, grafana-cli.exe, grafana-server.exe
# DataDir: ..\data
~~~

Ajouter les chemins vers le BinDir et ConfDir dans l'environnement des variables Windows pour pouvoir acceder à l'inface grafana (grafana-cli) et le server grafana (grafana-server) sans devoir donner le cheming absolu.

Afficher les information sur la l'instance de grafana installée sur votre machine.
~~~ps1
# ouvrir PowerShell et taper
grafana

NOM:
   grafana -Le serveur grafana et l'interface de commande

USAGE:
   grafana [global options] command [command options] [arguments...]

VERSION:
   10.3.3

AUTEUR:
   Grafana Project <hello@grafana.com>

COMMANDES:
   cli        exécuter l'interface de commande grafana
   server     exécuter le serveur grafana
   apiserver  exécuter un service api autonome (experimental)
   help, h    afficher la liste des commandes

OPTIONS GLOBALES:
   --help, -h     affiche l'aide
   --version, -v  affiche la version
~~~

## Configurer

~~~ps1
# RootDir: C:\Program Files\GrafanaLabs\grafana
# ConfDir: ..\conf

# Edit defaults.ini
# The ip address to bind to, empty will bind to all interfaces
http_addr = localhost

# The http port to use
http_port = 3000
~~~

## Se Connecter

~~~ps1
http://localhost:3000/login
username: admin
password: admin (default to reset after the first login)
~~~

~~~ps1
./grafana-server.exe --config "C:\Program Files\GrafanaLabs\grafana\bin\defaults.ini" --homepath "C:\Program Files\GrafanaLabs\grafana"
~~~

# Administrer grafana




