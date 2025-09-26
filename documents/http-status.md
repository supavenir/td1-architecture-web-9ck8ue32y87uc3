# 📊 Codes de statut HTTP

> Les **codes de statut HTTP** permettent au serveur d'indiquer au client le **résultat d'une requête** : succès, erreur, redirection, etc.

---

## 🧱 Structure d’un code HTTP

- Les codes sont composés de **3 chiffres**.
- Le **1er chiffre** indique la **famille** du statut.
- Les **2 autres** précisent le **détail** du cas.

---

## 🗂️ Familles de codes de statut

Voici un tableau récapitulatif avec exemples :

| Famille | Signification            | Exemple | Description courte                     | Cas d’usage typique                     |
|---------|--------------------------|---------|----------------------------------------|-----------------------------------------|
| `1xx`   | Information               | `100` Continue     | Le serveur a bien reçu la requête initiale | Communication continue, upgrade         |
| `2xx`   | Succès                   | `200` OK           | Requête réussie                        | Récupération de ressource, formulaire OK |
| `3xx`   | Redirection              | `302` Found        | Le client doit faire une autre requête | Redirection temporaire, login            |
| `4xx`   | Erreur côté client       | `404` Not Found    | La ressource n’existe pas              | Mauvaise URL, fichier manquant           |
| `5xx`   | Erreur côté serveur      | `500` Internal Server Error | Erreur serveur                       | Problème interne, crash, exception       |

---

## 🧨 Principales erreurs HTTP

| Code | Famille | Nom                     | Description                                                    | Cas d’usage courant                                       |
|------|---------|--------------------------|----------------------------------------------------------------|------------------------------------------------------------|
| 400  | 4xx     | Bad Request              | La requête est mal formée ou invalide                          | Syntaxe JSON invalide, paramètre manquant                 |
| 401  | 4xx     | Unauthorized             | Authentification requise (token ou login)                      | API sécurisée sans token / session                        |
| 403  | 4xx     | Forbidden                | Accès interdit, même si authentifié                            | Droits insuffisants (ex: admin-only)                     |
| 404  | 4xx     | Not Found                | Ressource inexistante                                          | Mauvaise URL, fichier ou page supprimé                   |
| 405  | 4xx     | Method Not Allowed       | Méthode HTTP non autorisée pour cette ressource                | Utilisation de PUT sur un endpoint qui accepte seulement GET |
| 409  | 4xx     | Conflict                 | Conflit avec l’état actuel de la ressource                     | Tentative de création d’un utilisateur déjà existant      |
| 410  | 4xx     | Gone                     | La ressource n’est plus disponible (et ne reviendra pas)       | Page définitivement supprimée                             |
| 415  | 4xx     | Unsupported Media Type   | Type de contenu non supporté par le serveur                    | Envoi de XML sur un endpoint JSON                         |
| 429  | 4xx     | Too Many Requests        | Trop de requêtes (rate limiting)                               | Protection contre DDoS ou abus d’API                      |
| 500  | 5xx     | Internal Server Error    | Erreur interne générique du serveur                            | Bug, exception non gérée                                  |
| 501  | 5xx     | Not Implemented          | Fonctionnalité non implémentée sur le serveur                  | Méthode HTTP inconnue ou non gérée                        |
| 502  | 5xx     | Bad Gateway              | Mauvaise réponse du serveur en amont (reverse proxy)           | Proxy reçoit une erreur d’un autre serveur                |
| 503  | 5xx     | Service Unavailable      | Serveur indisponible ou en maintenance                         | Maintenance planifiée ou surcharge                        |
| 504  | 5xx     | Gateway Timeout          | Timeout d’un serveur intermédiaire (proxy ou gateway)          | Backend lent ou injoignable                               |


