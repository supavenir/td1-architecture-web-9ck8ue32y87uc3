[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/m50_KXCC)
[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=20729899)
# Bloc 1 — Client/server web - Architecture
Durée indicative: 3 h  
Thème: Client–Serveur Web / Architecture

---

## 🎯 Objectifs
- Utiliser un repository GitHub Classroom pour versionner et publier vos travaux.
- Rédiger une documentation technique en Markdown.
- Manipuler HTTP (méthodes, en-têtes, statuts, négociation de contenu).
- Installer et configurer un serveur web local (XAMPP + virtual host).
- Pratiquer les requêtes HTTP en ligne de commande avec curl.

---

### ✅ Pré-requis
- Compte GitHub actif.
- Connexion internet.
- Droits administrateur sur votre poste.

---

### 📦 Repository et rendu
- Utilisez le repository associé à votre assignment Classroom.
- Commitez régulièrement (au minimum à la fin de chaque partie).
- Rédigez vos réponses en Markdown dans un sous-dossier documents/ de votre repo bloc1.
- Vous pouvez créer plusieurs fichiers .md et les relier entre eux.

Arborescence suggérée:
```
bloc1/
├─ documents/
│  ├─ README.md  (sommaire de vos travaux)
│  ├─ http-methodes.md
│  ├─ http-headers.md
│  ├─ http-status.md
│  ├─ url.md
│  ├─ negotiation-contenu.md
│  └─ curl-exemples.md
└─ public/ (fichiers publiés si nécessaire)
```

---

### 📝 Markdown (rappels/ressources)
- Markdown est un langage de balisage léger utilisé par GitHub.
- À lire/visionner (faites aussi vos propres recherches):
  - Apprendre le Markdown en 60 s
  - Tutoriel en 10 minutes
  - Référence Markdown

Astuce: utilisez des titres hiérarchisés, des listes, des tableaux, des blocs de code et des liens internes entre vos fichiers.

---

### 📚 Lectures HTTP (indispensables)
Ne limitez pas vos lectures aux titres ci-dessous; complétez par vos propres recherches.
- [Vue d’ensemble de HTTP (MSDN)](https://developer.mozilla.org/fr/docs/Web/HTTP/Overview)
- [Historique et évolution de HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Evolution_of_HTTP)
- [En-têtes (Headers) HTTP](https://www.ionos.fr/digitalguide/hebergement/aspects-techniques/http-header/)
- [Méthodes HTTP](https://developer.mozilla.org/fr/docs/Web/HTTP/Methods)
- [Codes de statut HTTP (response status)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
- [Types MIME](https://developer.mozilla.org/fr/docs/Web/HTTP/Basics_of_HTTP/MIME_Types)
- [Négociation de contenu](https://developer.mozilla.org/fr/docs/Web/HTTP/Content_negotiation)
- [Pour aller plus loin: cours complet HTTP](https://www.pierre-giraud.com/http-reseau-securite-cours/)

Consignez dans vos fichiers les éléments clés et exemples que vous retenez.

---

## 🧪 Travaux à réaliser

### 1) Méthodes GET et POST
- Illustrez, avec un ou plusieurs exemples concrets, les différences entre GET et POST.
- Mentionnez:
  - URLs utilisées
  - Données envoyées (corps, paramètres de requête)
  - En-têtes pertinents
  - Réponses obtenues

Exemple de structure attendue:
```
Contexte
URL
Requête (méthode, headers, corps)
Réponse (status, headers, extrait du corps)
Commentaire (sécurité, cache, idempotence, etc.)
```

---

### 2) Comparaison GET vs POST (tableau)
Remplissez un tableau comparatif basé sur vos exemples:

| Critère                   | GET                               | POST                              |
|--------------------------|------------------------------------|-----------------------------------|
| Visibilité des données   |                                    |                                   |
| Idempotence              |                                    |                                   |
| Mise en cache            |                                    |                                   |
| Longueur utile           |                                    |                                   |
| Cas d’usage typiques     |                                    |                                   |
| Sécurité (surface)       |                                    |                                   |

---

### 3) Extensibilité de HTTP
- Expliquez en quoi HTTP est extensible (méthodes, en-têtes, codes, versions, négociation).
- Donnez des exemples concrets (nouveaux headers, méthodes WebDAV, extensions, etc.).

---

### 4) HTTP « sans état »
- Définissez « protocole sans état ».
- Conséquences pour la navigation web.
- Mécanismes compensatoires (cookies, sessions, tokens) et impacts.

---

### 5) Décomposer une URL
- Décomposez une URL type et expliquez chaque partie.

Modèle à compléter:
```
schéma://identifiants@hôte:port/chemin?requête#fragment
```

| Partie        | Exemple             | Rôle                                             |
|---------------|---------------------|--------------------------------------------------|
| Schéma        | https               |                                                  |
| Identifiants  | user:pass           |                                                  |
| Hôte          | dev.local           |                                                  |
| Port          | 443                 |                                                  |
| Chemin        | /api/v1/resources   |                                                  |
| Requête       | q=abc&page=2        |                                                  |
| Fragment      | section-3           |                                                  |

---

### 6) Familles de codes de statut
Listez les familles et donnez un exemple pour chacune:

| Famille | Signification               | Exemple | Cas d’usage typique                      |
|---------|-----------------------------|---------|------------------------------------------|
| 1xx     | Information                 | 100     |                                         |
| 2xx     | Succès                      | 200     |                                         |
| 3xx     | Redirection                 | 302     |                                         |
| 4xx     | Erreur côté client          | 404     |                                         |
| 5xx     | Erreur côté serveur         | 500     |                                         |

---

### 7) Négociation de contenu
- Expliquez le principe (headers Accept, Accept-Language, Accept-Encoding, Content-Type, Vary…).
- Illustrez avec un exemple requête/réponse montrant une variante servie selon les préférences client.

---

### 8) Installation Apache & virtual host (XAMPP)
- Installez XAMPP et configurez un virtual host local pour dev.local.
- Guide: https://slamwiki2.kobject.net/web/server#xampp
- Fournissez:
  - Version de XAMPP/Apache
  - Extrait de configuration du virtual host
  - Emplacement du DocumentRoot
  - Capture(s) d’écran ou sortie de vérification (curl, navigateur)

Exemple de bloc de config (à adapter):
```apache
<VirtualHost *:80>
    ServerName dev.local
    DocumentRoot "C:/xampp/htdocs/dev"
    <Directory "C:/xampp/htdocs/dev">
        AllowOverride All
        Require all granted
    </Directory>
    ErrorLog "logs/dev-error.log"
    CustomLog "logs/dev-access.log" combined
</VirtualHost>
```

---

### 9) curl — requêtes à effectuer
Pour chaque requête: affichez la commande, le résultat (entête + extrait du corps si pertinent) et vos commentaires.

a) GET vers http://dev.local  
```bash
curl -i http://dev.local/
```

b) Afficher uniquement l’entête de la réponse pour cette URL  
```bash
curl -I http://dev.local/
```

c) GET vers une ressource inexistante http://dev.local/notExisting  
```bash
curl -i http://dev.local/notExisting
```

d) Afficher l’entête pour cette ressource inexistante  
```bash
curl -I http://dev.local/notExisting
```

e) Déposer un fichier localement dans le dossier download depuis la racine de votre virtual host dev.local, puis le télécharger avec curl  
- Dépôt (au choix: copie locale ou upload si vous avez prévu un endpoint)  
- Téléchargement:
```bash
curl -O http://dev.local/download/monfichier.zip
# ou
curl -o ./monfichier.zip http://dev.local/download/monfichier.zip
```

Astuce: utilisez -v pour le mode verbeux et -H pour ajouter des en-têtes personnalisés.

---

### 10) Principaux en-têtes de requête HTTP
- Listez et expliquez les en-têtes clés; illustrez leur rôle par un exemple curl.

Tableau à compléter:

| En-tête            | Rôle                                    | Exemple de valeur                 | Illustration (commande/réponse) |
|--------------------|------------------------------------------|-----------------------------------|----------------------------------|
| Host               |                                          | dev.local                         |                                  |
| User-Agent         |                                          | curl/8.7.1                        |                                  |
| Accept             |                                          | text/html,application/json;q=0.9  |                                  |
| Accept-Language    |                                          | fr-FR,fr;q=0.9                    |                                  |
| Accept-Encoding    |                                          | gzip, br                          |                                  |
| Content-Type       |                                          | application/json                  |                                  |
| Content-Length     |                                          | 123                               |                                  |
| Authorization      |                                          | Bearer …                          |                                  |
| Cookie             |                                          | session=...                       |                                  |
| Referer            |                                          | http://dev.local/page             |                                  |
| If-None-Match      |                                          | "etag123"                         |                                  |
| If-Modified-Since  |                                          | Tue, 15 Nov 1994 12:45:26 GMT     |                                  |

Exemples:
```bash
# Négociation de contenu
curl -i http://dev.local/ -H "Accept: application/json"

# Langue préférée
curl -i http://dev.local/ -H "Accept-Language: fr-FR,fr;q=0.9"
```

---

## ✅ Conseils d’évaluation et de bonnes pratiques
- Commits atomiques et messages clairs.
- Reproduisibilité: indiquez versions/outils/OS.
- Clarté de la doc: sommaire, liens internes, captures légendées.
- Justifiez vos choix et commentez vos résultats (pas seulement des captures).

---

## 📤 À livrer
- Le repository GitHub avec:
  - documents/ contenant tous les fichiers .md remplis
  - configuration du virtual host (extrait) et preuves de fonctionnement
  - scripts/commandes curl utilisés ( éventuellement scripts .sh/.bat)
- Un README.md dans documents/ qui fait office de sommaire et pointe vers chaque section.
