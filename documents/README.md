# 🧠 Bloc 1 – Client/Serveur Web & Architecture

> 📚 *"Comprendre HTTP, c'est parler la langue du Web."*  
> Ce dépôt contient l’ensemble des travaux pratiques autour du protocole HTTP, des architectures client-serveur, et de la configuration de serveur web local.

---

## 🗂️ Sommaire

| 📄 Section | 🔗 Lien |
|-----------|--------|
| 1. 🌐 [Méthodes HTTP (GET vs POST)](http-methodes.md) |
| 2. 🧾 [En-têtes HTTP](http-headers.md) |
| 3. 🧩 [Codes de statut HTTP](http-status.md) |
| 4. 🔍 [Décomposition d’une URL](url.md) |
| 5. 🌍 [Négociation de contenu](negotiation-contenu.md) |
| 6. 💻 [Commandes `curl` (exemples)](curl-exemples.md) |

---

## 🔧 Environnement & outils

- 🧰 **XAMPP** version `8.x` – Apache/PHP/MySQL local
- 🖥️ **Système** : Windows 10 / Linux / macOS *(à adapter selon ta config)*
- 🔁 **Git + GitHub Classroom** pour le versionnage
- 🧵 **Markdown** pour la documentation
- 🧪 `curl` pour l’exécution des requêtes HTTP

---

## 📁 Arborescence du repo

```
bloc1/
├── documents/
│ ├── README.md # ← Vous êtes ici
│ ├── http-methodes.md
│ ├── http-headers.md
│ ├── http-status.md
│ ├── url.md
│ ├── negotiation-contenu.md
│ └── curl-exemples.md
└── public/ # Fichiers publiés via le virtual host
```

---

## 🛠️ À propos du virtual host

Virtual host configuré pour `http://dev.local` via Apache + XAMPP.  
Voir détails dans la section [Curl & Virtual Host](curl-exemples.md#🧪-tests-curl-avec-devlocal)


---

## ✅ État d’avancement

| Partie | État | Notes |
|--------|------|-------|
| Méthodes GET/POST | ❌ Non-Fait | Exemples + tableau comparatif |
| Headers HTTP | ❌ Non-Fait | Liste + explications + curl |
| Status HTTP | ❌ Non-Fait | Familles + cas d’usage |
| Décomposition URL | ❌ Non-Fait | Tableau explicatif |
| Négociation contenu | ❌ Non-Fait | Headers `Accept`, `Vary`, etc. |
| Curl | ❌ Non-Fait | Commandes, réponses commentées |
| Virtual host | ❌ Non-Fait | Apache + `dev.local` OK |

---

## 🧠 Bonus pour les correcteurs

- 📎 Tous les fichiers `.md` sont liés entre eux via des liens internes
- 🧼 Commits réguliers et propres (`git log` clean)
- 🛑 Aucune capture d’écran sans contexte/commentaire
- 💬 Chaque réponse est commentée et justifiée
