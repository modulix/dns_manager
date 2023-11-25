# dns_manager
Interface FastAPI de gestion dynamique du DNS
## IHM & API
Cette application Python offre une interface d'administration d'un service DNS
L'API vous permet d'intégrer la création/modification/suppression de vos noms de domaine
dans vos pipelines CI/CD ou tout autre forme d'automatisation.
## Architecture
Ce système vous permet de contrôler vos noms de domaine sur votre infrastructure :
dns_manager -> ns1.domaine.tld
            -> ns2.domaine.tld
            -> ns3.domaine.tld
            -> nsX.domaine.tld
            -> ns1.autredomaine.tld
dns_manager -> ns2.autredomaine.tld
            -> ...
Le dns_manager administre les serveurs du domaine de façon sécurisée par SSH.
L'application peut-être "multi-instanciée" (par ex. présente sur plusieurs serveurs DNS).
## Installation
### Image Docker
(en cours)
Une image Docker avec tinydns et dns_manager
### Pre-requis
Ce logiciel écrit en Python est prévu pour fonctionner sur un serveur GNU-Linux,
il nécessite l'installation préalable du logiciel *tinydns*.
### Téléchargement
Copier le sources depuis : https://github.com/modulix/dns_manager
...
### Configuration
Copier le fichier dns_manager.service fourni (l'adapter au besoin) dans /etc/systemd/system/dns_manager.conf
## Lancement/Arrêt
L'application est prévue pour fonctionner en tant que service système :
systemctl enable dns_manager
systemct start dns_manager
systemctl status dns_manager
systemctl stop dns_manager
