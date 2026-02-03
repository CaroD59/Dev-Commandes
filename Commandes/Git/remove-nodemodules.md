# 🧹 Tuto : Retirer `node_modules` de Git (sans tout casser)

Il arrive souvent qu'on oublie le `.gitignore` et qu'on "push" par erreur des milliers de fichiers inutiles. Voici la procédure pour nettoyer ton dépôt distant (GitHub) tout en gardant tes fichiers localement.

## 1. Vérifier le `.gitignore`

Avant tout, assure-toi que ton fichier `.gitignore` contient bien la ligne suivante pour éviter que le problème ne revienne :

```text
node_modules/
.env*
```

---

## 2. Retirer les fichiers de l'index Git

Cette commande supprime les dossiers du suivi de Git, mais ne les supprime pas de ton ordinateur.

```bash
# Pour le dossier node_modules du serveur
git rm -r --cached dossier-back/node_modules

# Si tu en as un dans le client
git rm -r --cached dossier-client/node_modules

# Pour les fichiers d'environnement (sécurité)
git rm --cached .env
git rm --cached dossier-back/.env-copy
```

---

## 3. Enregistrer les changements

Maintenant, il faut dire à Git que ces fichiers ne doivent plus exister sur le dépôt.

```bash
git add .
git commit -m "chore: stop tracking node_modules and secret files"
```

---

## 4. Envoyer vers GitHub

```bash
git push origin master
```

## 💡 Pourquoi faire ça ?

Légèreté : Ton dépôt GitHub passera de plusieurs Mo (voire Go) à quelques Ko.

Vitesse : Les git pull et git push seront instantanés.

Sécurité : On ne push JAMAIS de mots de passe ou de clés API (fichiers .env).

Note : Si quelqu'un d'autre travaille sur le projet, il devra faire un npm install après avoir récupéré tes changements pour recréer son propre dossier node_modules localement.
