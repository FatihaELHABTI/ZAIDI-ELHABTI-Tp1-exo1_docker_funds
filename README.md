# Exercice 1 — Découverte de Docker

## 📌 Objectif
Prise en main des commandes Docker de base : téléchargement d'images, exécution de conteneurs, consultation des logs, nettoyage, etc.

---

## 🧪 Étapes réalisées

1. **Vérifier l'installation Docker**
   ```bash
docker --version
docker info
   ```

2. **Exécuter le conteneur `hello-world`**
   ```bash
docker run --rm hello-world
   ```

3. **Télécharger l'image `nginx:alpine` sans la lancer**
   ```bash
docker pull nginx:alpine
   ```

4. **Lister les images présentes**
   ```bash
docker images
   ```

5. **Lancer nginx en arrière-plan sur port 8080**
   ```bash
docker run -d --name mon-nginx -p 8080:80 nginx:alpine
   ```

6. **Accéder au serveur nginx dans le navigateur**
   ```text
http://localhost:8080
   ```

7. **Afficher les logs du conteneur nginx**
   ```bash
docker logs mon-nginx
# ou en temps réel
docker logs -f mon-nginx
   ```

8. **Lister tous les conteneurs (actifs et stoppés)**
   ```bash
docker ps -a
   ```

9. **Arrêter puis supprimer le conteneur nginx**
   ```bash
docker stop mon-nginx
docker rm mon-nginx
   ```

10. **Nettoyer les images inutilisées**
   ```bash
# Supprimer uniquement les images non référencées
docker image prune
# Supprimer toutes les images inutilisées (risqué)
docker image prune -a
   ```

---

## 💭 Questions de réflexion

### 1) Différence entre image et conteneur
Une **image** est un modèle immuable contenant le système de fichiers et les instructions de lancement.  
Un **conteneur** est une *instance en exécution* dérivée d'une image.

### 2) Rôle de l'option `-d`
`-d` (detach) exécute le conteneur en arrière-plan, laissant le terminal libre et permettant aux services comme nginx de tourner de façon persistante sans bloquer l'écran.

---

## 📂 Structure du dépôt
```
docker-exo1/
├── README.md
├── captures_realisation_tp/

```

---

