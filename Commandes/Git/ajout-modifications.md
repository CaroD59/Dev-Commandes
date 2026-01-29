# 🛠️ Git : Suivi & Enregistrement (Add, Status, Commit)

Ce guide se concentre sur le flux de travail quotidien : vérifier ce qu'on a fait et l'enregistrer proprement.

---

## 🔍 1. Observer les changements (Status & Diff)

Avant de sauvegarder, il faut toujours savoir où on en est.

| Commande            | Utilité                                                                    |
| :------------------ | :------------------------------------------------------------------------- |
| `git status`        | **La base.** Affiche les fichiers modifiés, supprimés ou non suivis.       |
| `git diff`          | Affiche **ligne par ligne** ce que tu as changé (avant de faire le `add`). |
| `git diff --staged` | Affiche les changements qui ont déjà été ajoutés avec `git add`.           |

---

## 📥 2. Préparer les modifications (Add)

L'étape de "staging" (la salle d'attente avant l'enregistrement).

| Commande            | Utilité                                                                      |
| :------------------ | :--------------------------------------------------------------------------- |
| `git add .`         | Ajoute **toutes** les modifications de ton projet d'un coup.                 |
| `git add <fichier>` | Ajoute seulement un fichier spécifique (plus précis).                        |
| `git add -p`        | Permet de choisir **morceau par morceau** ce que tu veux ajouter (très pro). |

---

## 💾 3. Enregistrer définitivement (Commit)

C'est ici que tu crées un point de sauvegarde dans l'histoire de ton code.

| Commande                   | Utilité                                                                                                |
| :------------------------- | :----------------------------------------------------------------------------------------------------- |
| `git commit -m "Message"`  | Enregistre ton travail avec un message court et clair.                                                 |
| `git commit -am "Message"` | **Raccourci :** Fait le `add` et le `commit` en même temps (uniquement pour les fichiers déjà connus). |
| `git commit --amend`       | "Oups, j'ai oublié un truc" : fusionne tes modifs avec le tout dernier commit.                         |

---

## 🚀 4. Envoyer sur le serveur (Push)

C'est l'étape finale pour mettre ton code en ligne (GitHub, GitLab, etc.).

| Commande                      | Utilité                                                                   |
| :---------------------------- | :------------------------------------------------------------------------ |
| **`git push`**                | Envoie tes commits locaux vers le dépôt distant.                          |
| **`git push -u origin main`** | Utilisé lors du **premier envoi** pour lier ta branche locale au serveur. |
| **`git push --force`**        | Force l'envoi (Attention : à utiliser avec prudence, écrase le distant).  |

---

## 📜 5. Consulter l'historique (Log)

Pour voir tes anciens enregistrements et les commentaires associés.

| Commande            | Utilité                                                                 |
| :------------------ | :---------------------------------------------------------------------- |
| `git log`           | Affiche la liste complète des commits (auteur, date, message).          |
| `git log --oneline` | Version compacte : une ligne par commit (idéal pour la lisibilité).     |
| `git log -p`        | Affiche l'historique avec le détail des lignes modifiées à chaque fois. |

---

## 💡 Le Workflow quotidien complet

Voici l'ordre logique à suivre pour ne jamais rien perdre :

1. Je code ma fonctionnalité.
2. `git status` -> "Qu'est-ce que j'ai changé ?"
3. `git diff` (Je relis mon code pour être sûr qu'il n'y a pas de bêtises).
4. `git add .` ou **`git add index.html index.js index.css`** -> "Je prépare tout (ou juste mes fichiers ciblés) pour la sauvegarde."
5. `git commit -m "Mon message"` -> "J'enregistre mon travail sur mon PC."
6. **`git push`** -> "J'envoie tout sur GitHub pour que ce soit en sécurité."
