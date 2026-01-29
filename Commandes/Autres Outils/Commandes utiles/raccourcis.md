# 🚀 Cheat Sheet Ultime : HTML, CSS, JS & React (TS)

Ce guide contient les raccourcis **Emmet** (natifs) et les **Snippets** (extensions) pour booster ta vitesse de développement sous VS Code.

## 💬 1. Raccourcis pour les COMMENTAIRES

C'est le raccourci le plus important. VS Code détecte automatiquement le type de fichier pour mettre les bons symboles.

| Action                                | Windows/Linux         | macOS                 |
| :------------------------------------ | :-------------------- | :-------------------- |
| **Commenter / Décommenter**           | `Ctrl` + `/`          | `Cmd` + `/`           |
| **Commentaire de bloc (multi-ligne)** | `Alt` + `Shift` + `A` | `Opt` + `Shift` + `A` |

### Exemples par langage :

- **HTML :** ``
- **CSS / JS :** `/* Mon commentaire */`
- **JS (Ligne seule) :** `// Mon commentaire`
- **React (JSX) :** `{/* Mon commentaire */}`

---

## 🏗️ 2. HTML (Emmet)

_Tape l'abréviation puis `Tab` ou `Entrée`._

| Abréviation     | Résultat                                      |
| :-------------- | :-------------------------------------------- |
| `!`             | Génère la structure complète HTML5            |
| `link:css`      | `<link rel="stylesheet" href="style.css">`    |
| `script:src`    | `<script src=""></script>`                    |
| `div.container` | `<div class="container"></div>`               |
| `div#main`      | `<div id="main"></div>`                       |
| `ul>li*5`       | Une liste `ul` contenant 5 `li`               |
| `input:t`       | `<input type="text">`                         |
| `input:b`       | `<input type="button">`                       |
| `div>p+span`    | Un `p` et un `span` à l'intérieur d'une `div` |

---

## 🎨 3. CSS (Emmet)

_À taper directement dans un fichier `.css` ou `.scss`._

| Abréviation | Résultat                            |
| :---------- | :---------------------------------- |
| `df`        | `display: flex;`                    |
| `jcc`       | `justify-content: center;`          |
| `aic`       | `align-items: center;`              |
| `fxd`       | `flex-direction: column;`           |
| `pos:a`     | `position: absolute;`               |
| `tac`       | `text-align: center;`               |
| `m10`       | `margin: 10px;`                     |
| `p10-20`    | `padding: 10px 20px;`               |
| `bg+`       | `background: #fff url() no-repeat;` |
| `bdb+`      | `border-bottom: 1px solid #000;`    |

---

## ⚛️ 4. React & TypeScript (ES7+ Snippets)

_Nécessite l'extension : **ES7+ React/Redux/React-Native snippets**._

### Création de Composants

| Abréviation | Résultat                                                     |
| :---------- | :----------------------------------------------------------- |
| `rfce`      | Composant fonctionnel exporté normalement                    |
| `rafce`     | Composant (Arrow Function) exporté en default                |
| `tsrafce`   | **React + TypeScript** (Arrow Function avec type `React.FC`) |
| `rconst`    | Constructeur de classe (si besoin de vieux code)             |

### Hooks & Logique

| Abréviation | Résultat                                                 |
| :---------- | :------------------------------------------------------- |
| `ust`       | `const [state, setState] = useState(initialState)`       |
| `uef`       | `useEffect(() => { ... }, [])`                           |
| `ucl`       | `useCallback(() => { ... }, [])`                         |
| `clg`       | `console.log(object)`                                    |
| `clo`       | `console.log('object', object)` (plus rapide pour debug) |

---

## ⌨️ 5. Raccourcis Clavier (Général)

| Action                                 | Windows/Linux         | macOS                 |
| :------------------------------------- | :-------------------- | :-------------------- |
| **Commenter / Décommenter**            | `Ctrl` + `/`          | `Cmd` + `/`           |
| **Commentaire de bloc**                | `Alt` + `Shift` + `A` | `Opt` + `Shift` + `A` |
| **Formater le document**               | `Alt` + `Shift` + `F` | `Opt` + `Shift` + `F` |
| **Déplacer la ligne**                  | `Alt` + `↑` ou `↓`    | `Opt` + `↑` ou `↓`    |
| **Copier la ligne en bas**             | `Shift` + `Alt` + `↓` | `Shift` + `Opt` + `↓` |
| **Sélectionner l'occurrence suivante** | `Ctrl` + `D`          | `Cmd` + `D`           |
