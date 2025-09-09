# Initialisation d'un dépôt avec SSH


Ce guide explique comment créer un dépôt GitHub et le pousser depuis votre machine locale en utilisant SSH, avec toutes les commandes nécessaires et la gestion des erreurs courantes.

---

## 1. Vérifier si vous avez déjà une clé SSH

```
ls ~/.ssh/
```

Si vous voyez id_ed25519 et id_ed25519.pub (ou id_rsa), vous avez déjà une clé.

Sinon, créez-en une nouvelle.

## 2. Créer une clé SSH (si nécessaire)

```
ssh-keygen -t ed25519 -C "votre_email@example.com"
```

Appuyez sur Entrée pour accepter le chemin par défaut : ~/.ssh/id_ed25519.

Mettez éventuellement une passphrase pour plus de sécurité.

## 3. Ajouter la clé SSH à l’agent

```
ssh-add ~/.ssh/id_ed25519
```
Si vous avez une passphrase, Git vous la demandera.

## 4. Ajouter la clé publique à GitHub

```
cat ~/.ssh/id_ed25519.pub
```
Aller sur GitHub → Settings → SSH and GPG keys → New SSH key

Donner un nom à la clé (ex : PC de ______)

Coller la clé publique et enregistrer.

## 5. Ajouter la clé publique à GitHub

Créez un nouveau dépôt sur GitHub (ne pas initialiser avec README si vous avez déjà un projet local).

## 6. Initialiser le dépôt local et connecter SSH

```
cd /chemin/vers/votre/projet
git init
git remote add origin git@github.com:VotreNomUtilisateur/NomDuDepot.git
```

## 7. Initialiser le dépôt local et connecter SSH

```
git add .
git commit -m "Initial commit"
```

## 8. Pousser vers GitHub

```
git push -u origin master
```

## 9. Tester la connexion SSH

Pour vérifier que GitHub reconnaît votre clé :
```
ssh -T git@github.com
```

Réponse attendue :
```
Hi VotreNomUtilisateur! You've successfully authenticated, but GitHub does not provide shell access.
```

⚠️ Erreurs courantes

| Erreur | Cause probable | Solution |
|--------|----------------|----------|
| `Permission denied (publickey)` | GitHub ne connaît pas votre clé publique | Ajouter la clé publique dans GitHub |
| `No such file or directory` | Mauvais nom de fichier pour la clé | Vérifier avec `ls ~/.ssh/` et utiliser le bon nom (`id_ed25519`) |
| `unknown key type id_ed25519` | Mauvaise syntaxe de commande `ssh-keygen` | Utiliser la commande correcte : `ssh-keygen -t ed25519 -C "email"` |

🔑 Astuces

Une seule clé SSH peut servir pour tous vos dépôts GitHub sur le même compte.

Pour les dépôts existants utilisant HTTPS, changez l’URL en SSH :
```
git remote set-url origin git@github.com:VotreNomUtilisateur/NomDuDepot.git
```