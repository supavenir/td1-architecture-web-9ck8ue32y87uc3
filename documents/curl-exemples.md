# 🐚 Exemples de requêtes curl

---

## a) GET vers http://dev.local

```bash
curl -i http://dev.local/
```

### Résultat attendu

- Statut `200 OK` si le serveur est actif
- En-têtes complets (Content-Type, Date, Server, etc.)
- Corps HTML ou autre contenu par défaut

### Commentaire

Requête simple pour récupérer la page d’accueil.
Le `-i` affiche les en-têtes + corps.

---

## b) Afficher uniquement l’entête de la réponse

```bash
curl -I http://dev.local/
```

### Résultat attendu

- En-têtes HTTP uniquement
- Pas de corps renvoyé

### Commentaire

Le `-I` (majuscule i) interroge uniquement les en-têtes (HEAD HTTP).
Utile pour vérifier le type de contenu, statuts, cache, etc.

---

## c) GET vers une ressource inexistante

```bash
curl -i http://dev.local/notExisting
```

### Résultat attendu

- Statut `404` Not Found
- En-têtes HTTP
- Corps pouvant contenir une page d’erreur personnalisée ou message d’erreur

### Commentaire

Permet de tester la gestion des erreurs 404 par le serveur.

---

## d) Afficher l’entête pour cette ressource inexistante

```
curl -I http://dev.local/notExisting
```

### Résultat attendu

- Statut `404` Not Found
- En-têtes HTTP uniquement

### Commentaire

Même que c), mais on ne récupère que les en-têtes.

---

## e) Télécharger un fichier depuis le dossier download

### Dépôt

Selon ta configuration, copie locale dans `public/download/monfichier.zip` (exemple).

### Téléchargement avec curl

```
curl -O http://dev.local/download/monfichier.zip

```
ou
```
curl -o ./monfichier.zip http://dev.local/download/monfichier.zip
```

## Résultat attendu

- Fichier `monfichier.zip` téléchargé dans le dossier courant
- En-têtes HTTP confirmant la réussite (`200 OK`)

Commentaire

- `-O` conserve le nom du fichier d’origine.
- `-o` permet de choisir un nom/localisation différente.
