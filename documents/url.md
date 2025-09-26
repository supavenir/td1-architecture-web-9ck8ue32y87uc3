# 🌐 Décomposer une URL

> Une **URL (Uniform Resource Locator)** est une adresse qui permet d'accéder à une ressource sur un réseau, généralement le Web.

---

## 📌 Structure d’une URL complète

```bash
schéma://identifiants@hôte:port/chemin?requête#fragment
```

## 🔍 Tableau de décomposition

| Partie         | Exemple                           | Rôle / Description                                            |
|----------------|-----------------------------------|---------------------------------------------------------------|
| **Schéma**     | `https`                           | Le protocole utilisé : `http`, `https`, `ftp`, etc.          |
| **Identifiants**| `user:pass`                      | (Optionnel) Utilisateur + mot de passe pour l’accès          |
| **Hôte**       | `dev.local` ou `example.com`      | Le nom de domaine ou l'adresse IP du serveur                 |
| **Port**       | `443`                             | (Optionnel) Port du service (`443` pour HTTPS, `80` pour HTTP) |
| **Chemin**     | `/api/v1/resources`               | Le chemin vers la ressource sur le serveur                   |
| **Requête**    | `?q=abc&page=2`                   | (Optionnel) Paramètres de requête (query string)             |
| **Fragment**   | `#section-3`                      | (Optionnel) Ancre dans le document (non transmise au serveur)|

## 🧪 Exemple concret

```
https://john:doe@api.example.com:8443/data/files?q=test&type=json#download
```

| Partie        | Exemple                | Rôle / Description                                              |
|---------------|------------------------|-----------------------------------------------------------------|
| **Schéma**    | `https`                | Protocole utilisé (HTTP, HTTPS, FTP, etc.)                      |
| **Identifiants** | `user:pass`          | Optionnel, nom d’utilisateur et mot de passe pour authentification |
| **Hôte**      | `dev.local`            | Nom de domaine ou adresse IP du serveur                         |
| **Port**      | `443`                  | Optionnel, numéro de port du service (80 HTTP, 443 HTTPS par défaut) |
| **Chemin**    | `/api/v1/resources`    | Chemin vers la ressource sur le serveur                         |
| **Requête**   | `q=abc&page=2`         | Optionnel, paramètres de la requête (query string)              |
| **Fragment**  | `section-3`            | Optionnel, ancre dans la page (non envoyée au serveur)          |

