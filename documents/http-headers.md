# 🧾 En-têtes HTTP

> Les en-têtes HTTP permettent de transporter des **informations supplémentaires** dans les requêtes et réponses HTTP.  
> Ils sont essentiels pour la négociation de contenu, la gestion des sessions, la sécurité, etc.

---

## 📌 Qu'est-ce qu’un en-tête HTTP ?

- Ce sont des paires **clé: valeur** ajoutées à chaque requête ou réponse HTTP.
- Ils permettent de :
  - Informer sur le client ou le serveur
  - Transmettre des métadonnées
  - Gérer le contenu (type, langue, cache…)
  - Gérer l’authentification, les cookies, etc.

---

## 🧪 Exemple de requête avec `curl`

```bash
curl -i http://dev.local -H "Accept: application/json" -H "User-Agent: curl/8.7.1"
```

## 🗂️ 1. Tableau des principaux en-têtes de requête (client → serveur)

| En-tête             | Rôle                                   | Exemple de valeur                      | Illustration `curl`                         |
|---------------------|----------------------------------------|----------------------------------------|---------------------------------------------|
| `Host`              | Nom du serveur ciblé                   | `dev.local`                            | `curl -H "Host: dev.local"`                 |
| `User-Agent`        | Info sur le client (navigateur, bot…) | `curl/8.7.1`, `Mozilla/5.0`            | `curl -H "User-Agent: curl/8.7.1"`          |
| `Accept`            | Types MIME acceptés                    | `text/html`, `application/json`        | `curl -H "Accept: application/json"`        |
| `Accept-Language`   | Langues préférées                      | `fr-FR,fr;q=0.9`                        | `curl -H "Accept-Language: fr-FR,fr;q=0.9"` |
| `Accept-Encoding`   | Encodages supportés                    | `gzip, br`                             | `curl -H "Accept-Encoding: gzip"`           |
| `Content-Type`      | Type de données envoyées               | `application/json`, `text/plain`       | `curl -H "Content-Type: application/json"`  |
| `Content-Length`    | Longueur du corps envoyé               | `123`                                  | Automatique ou avec `--data-binary`         |
| `Authorization`     | Authentification                       | `Bearer TOKEN`, `Basic base64...`      | `curl -H "Authorization: Bearer token"`     |
| `Cookie`            | Envoie les cookies de session          | `sessionId=xyz123`                     | `curl -H "Cookie: sessionId=abc"`           |
| `Referer`           | Page d’origine                         | `http://dev.local/page`                | `curl -H "Referer: http://dev.local/page"`  |
| `If-None-Match`     | Cache avec ETag                        | `"etag123"`                            | `curl -H "If-None-Match: \"etag123\""`      |
| `If-Modified-Since` | Cache avec date                        | `Tue, 15 Nov 1994 12:45:26 GMT`        | `curl -H "If-Modified-Since: ..."`          |

## 📬 2. Tableau des en-têtes de réponse (serveur → client)

| En-tête              | Rôle                                  | Exemple de valeur                         |
|----------------------|---------------------------------------|-------------------------------------------|
| `Content-Type`       | Type du contenu retourné              | `text/html; charset=UTF-8`                |
| `Content-Length`     | Taille du corps de la réponse         | `4523`                                    |
| `Set-Cookie`         | Création d’un cookie                  | `sessionId=abc123; Path=/; HttpOnly`      |
| `Location`           | Redirection                          | `/login` ou URL complète                  |
| `Cache-Control`      | Gestion du cache                     | `no-cache`, `max-age=3600`                |
| `ETag`               | Identifiant unique du contenu         | `"abc123"`                                |
| `Last-Modified`      | Date de dernière modification         | `Tue, 15 Nov 1994 12:45:26 GMT`           |
| `Vary`               | Dépendance de la réponse à un header  | `Accept-Language`, `Accept-Encoding`      |
| `WWW-Authenticate`   | Demande d’authentification            | `Basic realm="Secure Zone"`               |
| `Server`             | Info sur le serveur (optionnel)       | `Apache/2.4.54 (Win64)`                   |
