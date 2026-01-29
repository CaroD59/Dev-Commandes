# 🛠️ Git : Fusion (Merge) & Résolution de Conflits

Ce guide t'explique comment combiner ton travail avec celui des autres et comment réagir quand Git ne sait pas quelle version choisir.

---

## 🌿 1. Travailler avec les Branches

Avant de fusionner, il faut naviguer entre tes versions.

| Commande                      | Action                                                           |
| :---------------------------- | :--------------------------------------------------------------- |
| `git branch`                  | Liste tes branches (celle avec une `*` est la branche actuelle). |
| `git checkout -b feature-nom` | Crée une nouvelle branche et bascule dessus.                     |
| `git checkout main`           | Retourne sur la branche principale.                              |

---

## 🤝 2. Fusionner (Merge)

Ramener les modifications d'une branche dans une autre.

1. **Va sur la branche qui doit recevoir le code** (ex: `main`) :
   `git checkout main`
2. **Lance la fusion** :
   `git merge feature-nom` -> "Prends tout ce qui est dans `feature-nom` et mets-le dans `main`."

---

## ⚠️ 3. Résoudre un Conflit

Un conflit arrive quand deux personnes (ou toi sur deux branches) ont modifié **la même ligne** du même fichier. Git s'arrête et te demande de choisir.

### Étape 1 : Identifier

Tape `git status`. Git te listera les fichiers en conflit sous la mention :
`both modified: index.html`

### Étape 2 : Choisir dans VS Code

Ouvre le fichier en conflit. Tu verras des balises bizarres et 4 options en haut du texte :

- **Accept Current Change** : Garde ta version (celle de la branche où tu es).
- **Accept Incoming Change** : Garde la version de la branche que tu essaies de ramener.
- **Accept Both Changes** : Garde les deux versions l'une après l'autre.
- **Compare Changes** : Affiche les deux côte à côte pour décider.

### Étape 3 : Valider la résolution

Une fois que tu as choisi et supprimé les balises `<<<< HEAD`, `====` et `>>>>` :

1. `git add .` -> "C'est bon, j'ai réparé les fichiers."
2. `git commit -m "fix: résolution des conflits"` -> "Je valide la fusion."

---

## 🛡️ 4. Les commandes de sécurité (En cas de panique)

| Commande                          | Utilité                                                                                                              |
| :-------------------------------- | :------------------------------------------------------------------------------------------------------------------- |
| `git merge --abort`               | **Annule tout.** Si le conflit est trop complexe, cette commande revient à l'état juste avant le début de la fusion. |
| `git checkout --ours <fichier>`   | Choisit automatiquement ta version pour ce fichier.                                                                  |
| `git checkout --theirs <fichier>` | Choisit automatiquement la version de l'autre pour ce fichier.                                                       |

---

## 💡 Le Workflow de Fusion Pro

1. `git checkout main` (Je me mets sur la branche principale).
2. `git pull` (Je récupère la version la plus propre du serveur).
3. `git merge ma-feature` (Je tente la fusion).
4. _Si conflit_ : Je règle dans VS Code, puis `git add .` et `git commit`.
5. `git push` (Je partage la fusion réussie).
