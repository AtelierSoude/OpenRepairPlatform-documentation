# Installation

!!! warning "Ce guide est réservé aux développeurs-euses"
    Même si l'installation est simple, il est recommandé d'avoir quelques notions de programmation.


Cette application est encore en cours de développement. Toutes les contributions sont les bienvenues. Veuillez nous contacter si vous souhaitez contribuer et nous vous indiquerons comment procéder.

OpenRepairPlatform est une application basée sur Django conçue pour organiser des structures de réparation collaborative. Elle offre des fonctionnalités de gestion organisationnelle, de publication d'événements, de gestion des membres de la communauté, de suivi des réparations et de partage.

La plateforme a été créée par l'Atelier Soudé, une organisation qui répare les appareils électriques et électroniques des particuliers à Lyon, en France.


**Installation locale** : 
Pour une installation locale, installer l'application via docker compose

**Installation sur un serveur distant** :
En production, installez l'application uniquement en mode production.
Vous devez louer ou créer votre serveur Linux. Pour plus de simplicité, nous recommandons d'utiliser 
une instance Cloud. Par exemple chez [Scaleway](https://www.scaleway.com/fr/elements/). 
Accédez ensuite à votre serveur via [SSH](https://www.scaleway.com/en/docs/configure-new-ssh-key/). 

## Prérequis :
- [docker](https://docs.docker.com/engine/install/)
- git (`apt install git`)

## Lancer l'application en mode production

1 - Mettre en place l'environnement 

```bash
git clone https://github.com/AtelierSoude/OpenRepairPlatform.git
cd OpenRepairPlatform
touch .env
```

2 - Modifier le fichier .env 

```bash
#Contenu par défaut du fichier .env
# Activer la recherche de localisation sur la page d'accueil
LOCATION=1

# Paramètres DJANGO pour la configuration dev ou production 
DJANGO_SETTINGS_MODULE=openrepairplatform.settings.dev
SECRET_KEY=CHANGE_ME

# Pour activer le mode debug, mettre la variable d'environement à True
DEBUG=true
PREPROD=True # !!! Pour empêcher les robots d'indexer. Changer à false en production

#Paramètres de mail, uniquement en prod
EMAIL_PASSWORD=CHANGE_ME
EMAIL_HOST_USER=CHANGE_ME
EMAIL_HOST=CHANGE_ME
DEFAULT_FROM_EMAIL=no-reply@reparons.org

# Paramètre let's encrypt et nginx
#Le domaine principale que django va utiliser
DOMAINDNS=dev.reparons.org
# Hôtes autorisés et variables pour docker
# Some autorised hosts and vars are added for docker implementation
DOMAINS=localhost 127.0.0.1 [::1]
EMAIL=contact@atelier-soude.fr
SERVER_CONTAINER=openrepairplatform_nginx

# Paramètre postgres
POSTGRES_USER=openrepairplatform
POSTGRES_DBNAME=openrepairplatform
POSTGRES_PASSWORD=mangerdespommes
```

3.Ajouter la valeur de `DOMAINDNS` a votre fichier de configuration host (optionnel)

4.Lancer les commandes suivantes :

```bash
cd [git checkout directory]/
docker compose up
```

Le site web est désormais déployé et accessible à l'adresse 127.0.0.1:8005 (ou http://[DOMAINDNS]).

Par défaut, l'application de développement démarrera avec un serveur livereload, la surveillance automatique des fichiers django et la compilation automatique des fichiers vue.js.

5.Créez une organisation dans le chemin « http://localhost:8005/admin » et vous pourrez démarrer tout le reste (une documentation plus complète sera fournie ultérieurement).


## Lancer l'application en mode production


1 - Mettre en place l'environnement 

```bash
git clone https://github.com/AtelierSoude/OpenRepairPlatform.git
cd OpenRepairPlatform
touch .env
```

2 - Modifier le fichier .env 

```bash
#Contenu par défaut du fichier .env
# Activé la recherche de localisation sur la page d'accueil
LOCATION=1

# Paramètres DJANGO pour la configuration dev ou production 
DJANGO_SETTINGS_MODULE=openrepairplatform.settings.dev
SECRET_KEY=CHANGE_ME

# Pour activer le mode debug, mettre la variable d'environement à True
DEBUG=true
PREPROD=True # !!! Pour empêcher les robots d'indexer. Changer à false en production

#Paramètres de mail, uniquement en prod
EMAIL_PASSWORD=CHANGE_ME
EMAIL_HOST_USER=CHANGE_ME
EMAIL_HOST=CHANGE_ME
DEFAULT_FROM_EMAIL=no-reply@reparons.org

# Paramètre let's encrypt et nginx
#Le domaine principale que django va utiliser
DOMAINDNS=dev.reparons.org
# Hôtes autorisés et variables pour docker
# Some autorised hosts and vars are added for docker implementation
DOMAINS=localhost 127.0.0.1 [::1]
EMAIL=contact@atelier-soude.fr
SERVER_CONTAINER=openrepairplatform_nginx

# Paramètre postgres
POSTGRES_USER=openrepairplatform
POSTGRES_DBNAME=openrepairplatform
POSTGRES_PASSWORD=mangerdespommes
```

3 - Lancer l'application en mode production

Ce script va arrêter les services openrepairplatform et lancer l'application :
1. obtenir le certificat pour le domaine en utilisant certbot/nginx
2. build l'application
3. lancer l'application
4. exécuter les migrations
5. lancer l'application

```bash
sh ./install.prod.sh
```
