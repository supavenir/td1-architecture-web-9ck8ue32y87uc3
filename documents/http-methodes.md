# 🌐 Méthodes HTTP : GET vs POST

> Les méthodes `GET` et `POST` sont les plus couramment utilisées en HTTP. Elles permettent de récupérer ou d'envoyer des données entre un client (navigateur ou outil comme `curl`) et un serveur web.

---

## 📌 Contexte

Nous allons comparer les deux méthodes à l'aide d'exemples concrets et illustrés avec `curl`.  
Objectifs :

- Comprendre leur fonctionnement
- Identifier leurs différences fondamentales
- Savoir quand utiliser l'une ou l'autre

---

## 🔎 Exemple 1 – Requête `GET`

### 📍 URL

```text
http://dev.local/
```

### 📨 Requête

```bash
curl -i "http://dev.local/search?q=chatgpt"
```

### 🔁 Détails

- Méthode : `GET`
- Données envoyées : dans l’URL (paramètres de requête ?q=chatgpt)
- Headers :

```
GET /search?q=chatgpt HTTP/1.1
Host: dev.local
User-Agent: curl/8.7.1
Accept: */*
```

### 📬 Réponse (extrait)

```
HTTP/1.1 200 OK
Content-Type: text/html; charset=UTF-8

Résultats de recherche pour "chatgpt"
```

---

## 🧾 Exemple 2 – Requête POST

### 📍 URL

```text
http://dev.local/login
```

### 📨 Requête

```
curl -i -X POST http://dev.local/login \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "username=admin&password=1234"
```

### 🔁 Détails

- Méthode : `POST`
- Données envoyées : dans le corps de la requête
- Headers :

```
POST /login HTTP/1.1
Host: dev.local
Content-Type: application/x-www-form-urlencoded
Content-Length: 29
```

## 📬 Réponse (extrait)

```
HTTP/1.1 302 Found
Location: /dashboard
Set-Cookie: sessionId=xyz123
```