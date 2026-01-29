# 📥 Git Clone : HTTPS, SSH & Dossier Personnalisé

Le clonage permet de copier un projet distant sur ton PC. Tu peux choisir la méthode de connexion et le nom du dossier de destination.

---

## 🔗 1. HTTPS vs SSH (Les deux méthodes)

| Méthode   | Commande                                     | Avantage                                             |
| :-------- | :------------------------------------------- | :--------------------------------------------------- |
| **HTTPS** | `git clone https://github.com/user/repo.git` | Simple, fonctionne partout sans config.              |
| **SSH**   | `git clone git@github.com:user/repo.git`     | Pas de mot de passe à taper (nécessite une clé SSH). |

---

## 📁 2. Choisir le nom du dossier (Renommer)

Si tu ne précises rien, Git crée un dossier au nom du dépôt. Pour changer cela, ajoute simplement le **nom souhaité** à la fin.

### Syntaxe :

`git clone <URL_DU_REPO> <NOM_DU_DOSSIER>`

### Exemples concrets :

- **En HTTPS :**
  `git clone https://github.com/react/react.git mon-code-react`
  _(Le projet React sera téléchargé dans un dossier nommé "mon-code-react")_

- **En SSH :**
  `git clone git@github.com:react/react.git test-unitaire`
  _(Le projet sera téléchargé dans un dossier nommé "test-unitaire")_

- **Dans le dossier actuel (Dossier déjà créé) :**
  `git clone <URL> .`
  _(⚠️ Attention : Le dossier où tu te trouves doit être vide)_

---

## ⚙️ 3. Pourquoi utiliser le nom du dossier ?

1. **Organisation :** Tu veux appeler ton dossier `v3-final` au lieu de `project-repo`.
2. **Éviter les doublons :** Tu as déjà un dossier avec le même nom dans ton répertoire.
3. **Multi-clonage :** Tu clones le même projet deux fois pour comparer deux branches différentes dans deux dossiers séparés.

---

## 💡 Résumé du Workflow Rapide

1. **Copie l'URL** (HTTPS ou SSH) sur GitHub.
2. **Ouvre ton terminal** dans ton dossier de travail (ex: `Documents/Dev`).
3. **Tape la commande :**
   `git clone git@github.com:ton-pseudo/ton-repo.git nouveau-nom`
4. **Accède au projet :**
   `cd nouveau-nom`
5. **Ouvre dans VS Code :**
   `code .`
