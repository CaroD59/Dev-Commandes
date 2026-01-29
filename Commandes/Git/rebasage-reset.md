# ⏪ Git : Reset & Rebase (Annuler et Réorganiser)

Ce guide est dédié aux corrections d'erreurs et à la réorganisation de l'historique de tes commits.

---

## 🔙 1. Git Reset (Revenir en arrière)

Le Reset sert à "défaire" des commits ou des ajouts.

| Commande                       | Effet                                                                                                              |
| :----------------------------- | :----------------------------------------------------------------------------------------------------------------- |
| `git reset HEAD <fichier>`     | **Désélectionner** un fichier après un `git add` (il redeviendra rouge).                                           |
| `git reset --soft HEAD~1`      | **Annule le dernier commit** mais **garde ton code** intact dans l'éditeur.                                        |
| `git reset --mixed HEAD~1`     | Annule le commit et le `git add`. Ton code est préservé mais non préparé.                                          |
| `git reset --hard HEAD~1`      | **⚠️ Annule tout.** Supprime le dernier commit ET tout le code associé. Retour à l'état exact du commit précédent. |
| `git reset --hard <ID-COMMIT>` | Téléporte ton projet à l'état exact d'un commit spécifique (via son ID).                                           |

---

## 🏗️ 2. Git Rebase (Réécrire l'histoire)

Le rebase sert à garder un historique propre et linéaire, ou à fusionner des commits.

### A. Mettre à jour sa branche

Au lieu de faire un `merge` (qui crée un commit de fusion), le rebase déplace tes commits au-dessus des derniers commits du `main`.

1. `git checkout feature-branche`
2. `git rebase main` -> "Reprends mes modifs et pose-les par-dessus le main actuel."

### B. Rebase Interactif (Nettoyer ses commits)

Pour fusionner plusieurs petits commits en un seul propre avant de push :
`git rebase -i HEAD~3` (pour les 3 derniers commits)

- Une liste s'ouvre : change `pick` par `squash` pour fusionner un commit avec le précédent.

---

## 🛠️ 3. Corriger le dernier commit (Amend)

Si tu as juste oublié d'ajouter un fichier ou fait une faute dans le message :

1. `git add fichier-oublie.js`
2. `git commit --amend -m "Nouveau message correct"`

---

## 🆘 4. Le mode "Au secours"

| Situation                                          | Commande                                                                                                       |
| :------------------------------------------------- | :------------------------------------------------------------------------------------------------------------- |
| "Mon rebase se passe mal !"                        | `git rebase --abort` (Annule tout et revient au début).                                                        |
| "J'ai fait un reset --hard par erreur !"           | `git reflog` (Affiche l'historique de TOUTES tes actions pour retrouver l'ID du commit perdu).                 |
| "Je veux annuler un commit déjà envoyé sur GitHub" | `git revert <ID-COMMIT>` (Crée un nouveau commit qui fait l'inverse du précédent, c'est plus sûr qu'un reset). |

---

## 💡 Résumé du Workflow de correction

1. **Erreur de message ?** -> `git commit --amend`.
2. **Erreur de fichier ajouté ?** -> `git reset HEAD <fichier>`.
3. **Dernier commit raté (mais code bon) ?** -> `git reset --soft HEAD~1`.
4. **Branche pas à jour avec le main ?** -> `git rebase main`.
