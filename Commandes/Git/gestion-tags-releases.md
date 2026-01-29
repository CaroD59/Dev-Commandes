# 🏷️ Git : Gestion des Tags & Releases

Les tags permettent de marquer des points précis dans l'historique de ton projet comme étant importants (généralement des versions publiées).

---

## 📌 1. Créer des Tags

Il existe deux types de tags, mais on utilise presque toujours les **annotés** car ils contiennent plus d'infos (auteur, date, message).

| Commande                                  | Action                                                |
| :---------------------------------------- | :---------------------------------------------------- |
| `git tag v1.0`                            | Créer un tag léger (simple étiquette).                |
| `git tag -a v1.0 -m "Version stable 1.0"` | Créer un **tag annoté** avec un message (Recommandé). |
| `git tag -a v1.1 <ID-COMMIT>`             | Créer un tag pour un commit passé spécifique.         |

---

## 🔍 2. Lister et Voir les Tags

| Commande            | Action                                      |
| :------------------ | :------------------------------------------ |
| `git tag`           | Lister tous les tags du projet.             |
| `git tag -l "v1.*"` | Lister les tags qui commencent par "v1.".   |
| `git show v1.0`     | Voir les détails du tag et le code associé. |

---

## 🚀 3. Envoyer les Tags sur GitHub

Par défaut, `git push` n'envoie **pas** les tags. Il faut le préciser.

| Commande                 | Action                                           |
| :----------------------- | :----------------------------------------------- |
| `git push origin v1.0`   | Envoyer un tag spécifique sur le serveur.        |
| `git push origin --tags` | Envoyer **tous** tes tags locaux d'un seul coup. |

---

## 🗑️ 4. Supprimer un Tag

| Commande                        | Action                                  |
| :------------------------------ | :-------------------------------------- |
| `git tag -d v1.0`               | Supprimer le tag sur ton PC (local).    |
| `git push origin --delete v1.0` | Supprimer le tag sur le serveur GitHub. |

---

## 📦 5. Les "Releases" (Sur GitHub/GitLab)

Les **Releases** sont basées sur les Tags. Elles permettent de :

1. Transformer un Tag en une page de téléchargement propre.
2. Joindre des fichiers compilés (ex: un `.exe`, un `.zip` ou un `.apk`).
3. Rédiger un "Changelog" (la liste des nouveautés).

**Comment faire :**

1. Crée et push ton tag (`v1.0`).
2. Va sur GitHub dans la section **"Releases"**.
3. Clique sur **"Draft a new release"**.
4. Choisis ton tag `v1.0` et rédige ton titre et ta description.

---

## 💡 Astuce : Le Semantic Versioning (SemVer)

Pour nommer tes tags, on utilise souvent le format `MAJOR.MINOR.PATCH` (ex: `1.4.2`) :

- **MAJOR** : Gros changements (incompatible avec avant).
- **MINOR** : Nouvelles fonctionnalités (compatible).
- **PATCH** : Corrections de bugs.
