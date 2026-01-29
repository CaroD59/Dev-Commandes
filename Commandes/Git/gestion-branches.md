# 🌿 Git : La Gestion des Branches (Branching)

Les branches permettent de créer des univers parallèles pour coder une fonctionnalité sans risquer de casser la version stable (`main`) de ton projet.

---

## 📍 1. Les commandes de base

| Commande                | Action                                                                   |
| :---------------------- | :----------------------------------------------------------------------- |
| `git branch`            | Liste les branches locales (**l'astérisque `*`** indique où tu es).      |
| `git branch -a`         | Liste **toutes** les branches (locales + sur le serveur GitHub).         |
| `git checkout -b <nom>` | **Créer** une branche et **basculer** dessus immédiatement.              |
| `git checkout <nom>`    | Changer de branche pour retourner sur une autre.                         |
| `git branch -d <nom>`   | Supprimer une branche (si elle a été fusionnée).                         |
| `git branch -D <nom>`   | **Forcer** la suppression d'une branche (attention, perte de données !). |

---

## 🔄 2. Renommer une branche

Si tu as fait une faute de frappe ou que tu veux changer le nom :

- **Renommer la branche actuelle :**
  `git branch -m <nouveau-nom>`

---

## 🌐 3. Branches et GitHub (Remote)

Parfois, tu crées une branche sur ton PC et tu veux que tes collègues la voient sur GitHub.

| Commande                         | Action                                                                                  |
| :------------------------------- | :-------------------------------------------------------------------------------------- |
| `git push -u origin <nom>`       | Envoie ta nouvelle branche locale sur GitHub pour la première fois.                     |
| `git push origin --delete <nom>` | Supprime la branche sur le serveur GitHub.                                              |
| `git fetch`                      | Met à jour ta liste de branches locales avec celles créées par d'autres sur le serveur. |

---

## 🚀 4. Le Workflow "Pro" (Feature Branch)

C'est la méthode utilisée en entreprise :

1.  **S'assurer d'être à jour :**
    `git checkout main` -> `git pull`
2.  **Créer sa zone de travail :**
    `git checkout -b feature/bouton-contact`
3.  **Coder et Enregistrer :**
    `git add .` -> `git commit -m "Ajout du bouton"`
4.  **Envoyer pour relecture :**
    `git push -u origin feature/bouton-contact`
5.  **Fusionner :** (Une fois validé)
    `git checkout main` -> `git merge feature/bouton-contact`

---

## 📥 5. Mettre de côté sans commit (Git Stash)

Tu es sur une branche, tu n'as pas fini, mais tu dois changer de branche en urgence ? Git ne te laissera pas faire si tu as des modifs en cours.

- **Mettre au coffre-fort :**
  `git stash` (Tes modifs "disparaissent", ton dossier est propre).
- **Récupérer ses modifs plus tard :**
  `git stash pop` (Tes modifs reviennent là où tu en étais).
