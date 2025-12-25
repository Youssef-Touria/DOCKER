# Super Mario – Docker (pengbai/supermario)

## 1) Recherche de l'image sur Docker Hub
Objectif : vérifier que l’image existe sur Docker Hub avant de la récupérer.
![alt-text](image/recherche_image_v2.jpg)

## 2) Récupération (pull) de l'image
Commande utilisée : `docker pull pengbai/supermario`
Résultat : téléchargement de l’image en local.
![alt-text](image/recuperation_image.jpg)

## 3) Image disponible dans la liste des images locales
Commande utilisée : `docker images`
Résultat : l’image `pengbai/supermario` apparaît dans la liste.
![alt-text](image/image_locale.jpg)

## 4) Run de l'image (lancer un container sur le port 8600)
Objectif : exposer le container (8080) sur le port 8600 de la machine.
Commande (terminal) : `docker run -d --name supermario-8600 -p 8600:8080 pengbai/supermario`
![alt-text](image/commande_run.jpg)

### Résultat dans Docker Desktop (container créé et démarré)
![alt-text](image/container_run.jpg)

### Deuxième container lancé sur un autre port
Exemple : `docker run -d --name supermario-8601 -p 8601:8080 pengbai/supermario`
![alt-text](image/container_run_2.jpg)

## 5) Usage avec 1 et 2 conteneurs démarrés
Vérification : accès via navigateur.
- 1 container : `http://localhost:8600`
- 2 containers : `http://localhost:8600` et `http://localhost:8601`
![alt-text](image/usage_1_containeur.jpg)
![alt-text](image/usage_2_containeur.jpg)

## 6) Gameplay (au moins 3 captures)
![alt-text](image/gameplay_1.jpg)
![alt-text](image/gameplay_2.jpg)
![alt-text](image/gameplay_3.jpg)

## 7) Trouver l'ID du container (2 façons)
Méthode 1 : `docker ps`
![alt-text](image/trouver_id_1.jpg)

Méthode 2 : Docker Desktop > Containers (ID/Name visible)
![alt-text](image/trouver_id_2.jpg)

## 8) Arrêt des conteneurs
Commande (terminal) : `docker stop <CONTAINER_ID>` (ou `docker stop supermario-8600`)
![alt-text](image/arret_supermario-8600.jpg)

Arrêt via Docker Desktop (bouton Stop)
![alt-text](image/arret_supermario-8061.jpg)

## 9) Vérification après arrêt
Résultat attendu : le jeu n’est plus accessible (container stoppé).
![alt-text](image/utilisation_apres_arret.jpg)
![alt-text](image/container-stoppé.jpg)

## 10) Suppression des conteneurs (2 façons)
Terminal : `docker rm <CONTAINER_ID>` / `docker rm supermario-8600`
![alt-text](image/suppr_conteneur_1.jpg)

Docker Desktop : Containers > Delete/Remove
![alt-text](image/suppr_conteneur_2.jpg)

## 11) Suppression de l'image (2 façons)
Terminal : `docker rmi pengbai/supermario`
![alt-text](image/suppr_image_1.jpg)

Docker Desktop : Images > Remove
![alt-text](image/suppr_image_2.jpg)
