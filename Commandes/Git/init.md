
# Initialisation d'un dépôt

Ce guide t'explique comment relier ton projet local à un dépôt GitHub et pousser tes modifications.

## 1. Vérifier l'installation de Git

Avant de commencer, vérifie que Git est installé sur ton ordinateur. Ouvre un terminal et tape la commande suivante :

```sh
git --version
```

Si Git n'est pas installé, tu peux le télécharger ici : [https://git-scm.com/downloads](https://git-scm.com/downloads).

## 2. Aller dans le dossier de ton projet

Ouvre un terminal et navigue vers ton dossier de projet avec la commande suivante :

```sh
cd "chemin/vers/ton/projet"
```

Par exemple, si ton projet est dans `C:\Users\TonNom\Documents\TonProjet`, exécute :

```sh
cd "C:\Users\TonNom\Documents\TonProjet"
```

## 3. Initialiser un dépôt Git (si ce n'est pas déjà fait)

Si ce n'est pas encore un dépôt Git, exécute cette commande pour l'initialiser :

```sh
git init
```

## 4. Ajouter un dépôt distant

Vérifie si un dépôt distant est déjà configuré en exécutant :

```sh
git remote -v
```

Si un dépôt distant incorrect est configuré, supprime-le avec la commande :

```sh
git remote remove origin
```

Ensuite, ajoute ton dépôt GitHub en exécutant la commande suivante :

```sh
git remote add origin https://github.com/TonCompteGithub/TonRepository
```

## 5. Configurer ton identité Git

Si Git te demande d'indiquer ton identité, configure ton nom et ton email en exécutant ces commandes :

```sh
git config --global user.name "Ton Nom"
git config --global user.email "ton.email@example.com"
```

Remplace "Ton Nom" et "ton.email@example.com" par ton nom et ton adresse email associés à GitHub.

### Vérifier la configuration

Tu peux vérifier que ton nom et email sont correctement configurés avec cette commande :

```sh
git config --global --list
```

Cela devrait afficher quelque chose comme :

```
user.name=Ton Nom
user.email=ton.email@example.com
```

## 6. Ajouter et commit des fichiers

Ajoute tous les fichiers à Git avec la commande suivante :

```sh
git add .
```

ou 

```sh
git add -p
```

Puis, effectue un commit :

```sh
git commit -m "Initial commit"
```

## 7. Pousser vers GitHub

Si c'est la première fois que tu pousses vers GitHub, tu dois forcer la mise à jour avec :

```sh
git branch -M main
git push -u origin main
```

Si tu avais déjà un dépôt avec un historique, tu peux essayer de récupérer les modifications avec :

```sh
git pull origin main --rebase
git push origin main
```

## 8. Vérifier sur GitHub

## Remarque

Si tu rencontres une erreur d'authentification, utilise un [token d'accès personnel (PAT)](https://github.com/settings/tokens) au lieu de ton mot de passe :

1. Va dans **Paramètres GitHub → Developer settings → Personal access tokens → Tokens (classic)**.
2. Clique sur **Generate new token → Classic token**.
3. Donne un nom au token, choisis une date d’expiration, et sélectionne au minimum la permission `repo`.
4. Clique sur **Generate token** et copie-le immédiatement.
5. Lors du prochain `git push`, entre ton **nom d’utilisateur GitHub** comme nom d’utilisateur et colle le **PAT** comme mot de passe.
6. Pour ne pas avoir à le saisir à chaque push, exécute :  
   ```sh
   git config --global credential.helper store