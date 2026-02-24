# TP1_Web2_2026

# TP JavaScript 1 — Variables, Types et DOM (Rappel)
---

## Objectifs pédagogiques

À l'issue de ce TP, vous serez capable de :
- Intégrer du JavaScript dans une page HTML via la balise `<script>`
- Déclarer des variables avec `let` et des constantes avec `const`
- Utiliser les méthodes d'affichage : `console.log`, `alert`, `prompt`, `innerHTML`
- Appliquer les règles de nommage et les conventions JavaScript (camelCase)
- Manipuler des valeurs primitives (nombres, chaînes, booléens)

---

## Structure de fichiers attendue

```
tp-javascript/
├── index.html          ← fichier de départ (fourni)
├── exercice1.html
├── exercice2.html
├── exercice3.html
├── exercice4.html
├── exercice5.html
├── exercice6.html
├── exercice7.html
```

---

## Fichier de départ `index.html`

Copiez ce fichier de départ pour chaque exercice :

```html
<!DOCTYPE html>
<html lang="fr">
  <head>
    <meta charset="UTF-8" />
    <title>TP JavaScript</title>
  </head>
  <body>
    <h1>Exercice X</h1>
    <!-- Votre contenu HTML ici -->

    <script>
      // Votre code JavaScript ici
    </script>
  </body>
</html>
```

**Rappel :** Ouvrez la **console du navigateur** (`F12` → onglet *Console*) pour voir les messages `console.log`. C'est votre meilleur outil de débogage !

---

## Exercices

---

### Exercice 1 — Hello, console ! 

**Objectif :** Intégrer du JavaScript dans une page HTML et utiliser `console.log`.

Créez un fichier `exercice1.html` contenant une page HTML valide.  
Dans la balise `<script>` placée **avant la fermeture du `<body>`**, écrivez le code JavaScript suivant :

1. Affichez le message `"Bonjour, monde !"` dans la console.
2. Affichez votre prénom dans la console.
3. Affichez le résultat de `7 + 3` dans la console.
4. Affichez le résultat de `10 * 4 - 5` dans la console.

**Résultat attendu dans la console :**
```
Bonjour, monde !
[votre prénom]
10
35
```

**À retenir :** `console.log()` accepte plusieurs arguments séparés par des virgules : `console.log("résultat :", 10)`.

---

### Exercice 2 — 

**Objectif :** Déclarer et initialiser des variables avec `let`.

Créez `exercice2.html`. Dans le `<script>`, déclarez les variables suivantes avec `let` en respectant la convention **camelCase** :

| Variable              | Valeur initiale        |
|-----------------------|------------------------|
| Votre prénom          | `"Mariem"` (ou le vôtre)|
| Votre âge             | `20`                   |
| Votre ville           | `"Marrakech"`          |
| Votre taille (en m)   | `1.75`                 |
| Vous aimez le JS ?    | `true`                 |

Ensuite :
1. Affichez chaque variable dans la console avec un libellé explicite.  
   Exemple : `console.log("Prénom :", prenom);`
2. Modifiez la valeur de votre âge (simulez un anniversaire : `age = age + 1`).
3. Affichez à nouveau l'âge pour vérifier la modification.

**Résultat attendu dans la console :**
```
Prénom : Mariem
Âge : 20
Ville : Marrakech
Taille : 1.75
Aime le JS : true
Nouvel âge : 21
```

> **Règle :** Utilisez `let` et non `var`. Vérifiez que vos noms de variables sont en camelCase.

---

### Exercice 3 —

**Objectif :** Utiliser `const` pour les valeurs qui ne doivent pas changer.

Créez `exercice3.html`. Vous êtes en train de développer une mini-calculatrice de prix pour une boutique.

1. Déclarez une constante `TAUX_TVA` avec la valeur `0.20` (TVA à 20 %).
2. Déclarez une variable `prixHT` avec la valeur de votre choix (ex. `150`).
3. Calculez le prix TTC avec la formule : `prixTTC = prixHT + (TAUX_TVA * prixHT)`
4. Affichez dans la console :  
   `"Prix HT : 150 € | TVA (20%) : 30 € | Prix TTC : 180 €"`  
   *(en utilisant les variables, pas les valeurs en dur)*
5. Tentez de modifier `TAUX_TVA` dans votre code. Que se passe-t-il dans la console ?

>  **Template literals :** Utilisez les backticks pour composer vos messages :  
> `` console.log(`Prix TTC : ${prixTTC} €`); ``

>  **Convention :** Les constantes utilisent le SCREAMING_SNAKE_CASE : `TAUX_TVA`, `MAX_VALEUR`.

---

### Exercice 4 —

**Objectif :** Utiliser `window.prompt`, `window.alert` et `window.confirm`.

Créez `exercice4.html`. Ce script doit interagir avec l'utilisateur au chargement de la page.

Écrivez le programme suivant **dans l'ordre** :

1. Demandez le prénom de l'utilisateur avec `prompt("Quel est votre prénom ?")` et stockez la réponse dans une variable `prenom`.
2. Demandez son âge avec `prompt("Quel est votre âge ?")` et stockez dans une variable `age`.
3. Convertissez l'âge en nombre avec `Number(age)` (car `prompt` renvoie toujours une chaîne).
4. Calculez l'année de naissance approximative : `anneeNaissance = 2025 - age`.
5. Affichez une alerte : `"Bonjour [prénom] ! Vous êtes né(e) vers [annee]."`.
6. Demandez à l'utilisateur s'il veut voir ses informations dans la console avec `confirm("Afficher dans la console ?")`.
7. Si l'utilisateur clique **OK** (`true`), affichez dans la console : prénom, âge et année de naissance.

>  `prompt()` retourne `null` si l'utilisateur clique sur "Annuler". En situation réelle, il faudrait le gérer !

---

### Exercice 5 

**Objectif :** Modifier le contenu d'éléments HTML avec `innerHTML`.

Créez `exercice5.html`. Construisez une fiche de présentation dynamique.

**Structure HTML à créer dans le `<body>` :**

```html
<h1>Ma fiche de présentation</h1>
<p id="nomComplet">...</p>
<p id="age">...</p>
<p id="ville">...</p>
<p id="presentation">...</p>
```

**Dans le `<script>` (après les éléments HTML) :**

1. Déclarez les variables : `prenom`, `nom`, `age`, `ville` avec vos informations.
2. Utilisez `document.getElementById("nomComplet").innerHTML` pour afficher `"Prénom NOM"` dans le paragraphe correspondant.
3. Faites de même pour afficher l'âge et la ville.
4. Dans le paragraphe `"presentation"`, affichez une phrase complète :  
   `"Je m'appelle [prénom] [nom], j'ai [age] ans et j'habite à [ville]."`
5. Changez dynamiquement le titre de la page (`<title>`) avec :  
   `document.title = "Fiche de " + prenom;`

> `document.querySelector("#nomComplet").innerHTML` fonctionne également !

---

### Exercice 6 — Nommage et débogage

**Objectif :** Identifier et corriger des erreurs de nommage de variables.

Créez `exercice6.html` et copiez le code JavaScript ci-dessous **tel quel** dans le `<script>`.  
Ouvrez la console : vous verrez des erreurs. Corrigez **toutes** les erreurs de nommage et de syntaxe.

```javascript
// Code à corriger — NE PAS modifier la logique, seulement les noms et la syntaxe

let 1erPrix = 100;
let deuxieme prix = 80;
let prix-minimum = 50;
let var = 200;
let PrixMaximum = 300;
let prix_moyen = (1erPrix + deuxieme prix + prix-minimum + var + PrixMaximum) / 5;

console.log("Prix moyen : " + prix_moyen);
console.log("Le prix minimum est : " + prix-minimum);
```

Une fois les erreurs corrigées, appliquez les **conventions camelCase** à toutes les variables qui ne les respectent pas, puis affichez dans la console :
- Le prix moyen
- Le prix minimum
- Le prix maximum

---

### Exercice 7 

**Objectif :** Combiner variables, constantes, calculs et affichage HTML.

Créez `exercice7.html`. Vous allez créer un mini-calculateur de propriétés d'un cercle.

**Structure HTML :**

```html
<h1> Calculatrice de cercle</h1>
<div id="rayon"></div>
<div id="perimetre"></div>
<div id="surface"></div>
```

**Dans le `<script>` :**

1. Déclarez une constante `PI` avec la valeur `Math.PI`.
2. Demandez le rayon du cercle à l'utilisateur via `prompt` et convertissez-le en nombre.
3. Calculez :
   - Le **périmètre** : `2 * PI * rayon`
   - La **surface** : `PI * rayon * rayon`
4. Affichez dans les `<div>` correspondants :
   - `"Rayon : [valeur] cm"`
   - `"Périmètre : [valeur arrondie à 2 décimales] cm"` — utilisez `.toFixed(2)`
   - `"Surface : [valeur arrondie à 2 décimales] cm²"`

> Pour arrondir : `(3.14159).toFixed(2)` renvoie `"3.14"` (c'est une chaîne !)

## Ressources utiles

- [MDN — Variables JavaScript](https://developer.mozilla.org/fr/docs/Learn/JavaScript/First_steps/Variables)
- [MDN — Types de données](https://developer.mozilla.org/fr/docs/Web/JavaScript/Data_structures)
- [MDN — document.getElementById](https://developer.mozilla.org/fr/docs/Web/API/Document/getElementById)
- [MDN — Template literals](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Template_literals)
