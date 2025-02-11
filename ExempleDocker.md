# Déploiement avec Docker Compose

Ce document explique comment utiliser Docker Compose pour déployer l'application **Calculateur-carbo**.

## Prérequis

- Docker installé sur votre machine
- Docker Compose installé

## Installation et Démarrage

1. Clonez le dépôt :
   ```sh
   git clone https://github.com/Nem0oo/Calculateur-carbo.git
   cd Calculateur-carbo
   ```
2. Contenu du Docker-compose.yml à placer dans le repertoire parent
    ```yaml
    services:
	  Calculateur-carbo:
	    image: httpd:alpine3.21
	    restart: unless-stopped
	    container_name: Calculateur-carbo
	    volumes:
	      - ./Calculateur-carbo:/usr/local/apache2/htdocs
	    ports:
	      - "80:80"
    ```

2. Démarrez le conteneur avec Docker Compose :
   ```sh
   docker-compose up -d
   ```
3. L'application sera accessible via `http://localhost`.

---

**Auteur :** Nem0oo