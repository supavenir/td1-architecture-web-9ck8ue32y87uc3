# 🔄 Négociation de contenu HTTP

> La **négociation de contenu** permet au serveur de fournir la meilleure version possible d’une ressource en fonction des préférences exprimées par le client dans les en-têtes HTTP.

---

## ⚙️ Principe général

- Le client indique ses préférences (formats, langues, encodages) via les **en-têtes de requête**.
- Le serveur choisit la variante la plus adaptée et répond avec un **en-tête `Content-Type`** approprié.
- Le serveur peut aussi indiquer les variantes possibles via l’en-tête `Vary`.

---

## 🛠️ En-têtes clés utilisés

| En-tête             | Rôle                                                   | Exemple                                   |
|---------------------|--------------------------------------------------------|-------------------------------------------|
| `Accept`            | Types MIME acceptés par le client                      | `text/html, application/json;q=0.9`      |
| `Accept-Language`   | Langues préférées par le client                         | `fr-FR, fr;q=0.9, en-US;q=0.8`            |
| `Accept-Encoding`   | Encodages (compression) supportés                      | `gzip, deflate, br`                        |
| `Content-Type`      | Type MIME du contenu renvoyé par le serveur             | `application/json; charset=utf-8`         |
| `Vary`              | Indique les en-têtes sur lesquels la réponse varie     | `Accept, Accept-Language`                  |

---

## 🔍 Exemple de négociation avec `Accept`

### Requête client

```http
GET /resource HTTP/1.1
Host: dev.local
Accept: application/json, text/html;q=0.8
```

### Réponse serveur (format JSON choisi)

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Vary: Accept

{
  "id": 123,
  "name": "Produit A"
}
```

> Le serveur choisit le format JSON, car application/json a une priorité plus haute que text/html (q=0.8).

---

### 🔍 Exemple de négociation avec Accept-Language

### Requête client

```http
GET /page HTTP/1.1
Host: dev.local
Accept-Language: fr-FR,fr;q=0.9,en-US;q=0.8,en;q=0.7
```

### Réponse serveur (version française servie)

```
HTTP/1.1 200 OK
Content-Type: text/html; charset=utf-8
Content-Language: fr-FR
Vary: Accept-Language

<html>
  <body>
    <h1>Bienvenue</h1>
    ...
  </body>
</html>
```

---

### 🧠 Résumé

- La négociation de contenu améliore l’expérience utilisateur en adaptant la réponse.
- Elle repose sur des en-têtes standards très utilisés.
- Elle nécessite une bonne gestion côté serveur pour gérer les variantes.

