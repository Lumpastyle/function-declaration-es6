# Nouvelles déclarations des fonctions

## Déclaration de fonction

Une fonction est une procédure JavaScript, un ensemble d'instructions effectuant une tâche ou calculant une valeur.
La définition / déclaration / instruction d’une fonction peut se faire de différentes manières qui reviennent au même résultat.

Pour déclarer une fonction il faut nécessairement le mot clé function aussi appelé constructeur suivi par:
le nom de la variable
une liste d’arguments à passer à la fonction, exemple (a,b)
les instructions JavaScript définissant la fonction entre 
{}`.

Il existe les fonctions appelées qui se construisent de cette manière :

```javascript
function multiplier(x, y) {
   return x * y;
}
```

Il existe les fonctions appelées qui se construisent de cette manière :

```javascript
var multiplier = function(x, y) {
   return x * y;
}
```

La déclaration d’une fonction se construit avec ce qu’on appelle un mot clé: function aussi appelé constructeur.

Voici l’exemple d’une fonction définie grâce au constructeur et assigné à une variable :

```javascript
var multiplier = new Function("x", "y", "return x * y;");
```

L’exemple suivant est l’expression de fonction d’une fonction assignée à une variable :

```javascript
var multiplier = function function_nom(x, y) {
   return x * y;
}
```

Une fonction peut renvoyer un résultat avec return et peut être déclarée après son utilisation. 
Les fonctions sont d’ailleurs prioritairement lu par JavaScript, avant le reste.

Voici deux exemples de fonctions qui ont exactement le même effet:

```javascript
function addition(a,b){
    return a + b;
}
addition(1,2);
```

```javascript
addition (1,2);
function addition(a,b){
   sum =  a + b;
}
```

## Portée d'une fonction

Les variables définies dans une fonction sont accessibles uniquement dans cette fonction. Elles n’existent que dans la portée de la fonction. 


```javascript
var malili = function faire() {
   // les instructions de la fonction
};
```

Cependant, une fonction peut accéder aux variables et fonctions qui appartiennent à la portée dans laquelle elle est définie. 

Une récursion est une fonction qui s’appelle elle-même. Une récursion est semblable à une boucle.

```javascript
function boucle(x) {
  if (x >= 10) // "x >= 10" représente la condition d'arrêt (équivalent à "!(x < 10)")
    return;
  // faire quelque chose
  boucle(x + 1); // l'appel récursif
}
boucle(0);
```

Une fonction peut être imbriquée au sein d’une autre fonction. La fonction interne est privée par rapport à la fonction qui la contient. 
C’est une fermeture (closure). Ainsi la fonction interne peut utiliser des arguments et des variables de la fonction externe alors que la fonction externe ne peut pas utiliser de variables et d’arguments de la fonction interne.


```javascript
function ajouteCarrés(a, b) {
  function carré(x) {
    return x * x;
  }
  return carré(a) + carré(b);
}
```

Lorsque deux variables ont le même nom et appartiennent à la même portée, il y a conflit. 

La portée la plus interne, l’emportera par rapport à la portée externe. C’est la chapine de portée. 

### Méthodes

Une fonction à l'intérieur d'un objet Javascript est appellé une `Méthode`.

Définition de méthode en ES5 :
```javascript
var object1 = {
	toto: function() {
	/* Code de la fonction */
    }
}
```

Nouvelle définition de méthode en ES6 :
```javascript
var object1 = {
	toto() {
	/* Code de la fonction */
    }
}
```

## Fonctions fléchées

Les fonctions fléchées offrent une syntaxe raccourcie des fonctions en utilisant la syntaxe `=>`

Définition de fonction en ES5 :
```javascript
var myFn = function(x) {
    return x + 1
}
```

Nouvelle définition de fonction en ES6 :
```javascript
const myFn = (x) => {
  return x + 1
}
```

Peut aussi s’écrire ainsi (plus concis): `const myFn = (x) => x + 1`

> Parenthèses non nécessaires quand il n'y a qu'un seul argument
`param => expression`

> Une fonction sans paramètre peut s'écrire avec un couple de parenthèses
`() => { instructions }`

> Si notre expression mérite d'être sur plusieurs lignes, on peut aussi utiliser des parenthèses :
`const myFn = x => (
   x +
   1 // Ici multi lignes
 )`
 
 ### Origine de la conception des fonctions fléchées
 
1. La syntaxe est plus courte

Sans la syntaxe des fonctions fléchées 
```javascript
var a2 = a.map(function(s){ return s.length });
```

Avec, on a quelque chose de plus concis
```javascript
var a3 = a.map( s => s.length );
```

2. Pas de liaison pour `this`

Les fonctions fléchées n’ont pas de `this`.

À l'inverse des fonctions normales, les fonctions fléchées partagent le même this lexical que leur scope parent. Du coup, le `this` que vous pourrez utiliser dans votre corps de fonction fléchée est celui du code parent :

```javascript
const Someone = {
  name: “Sara”,
  friends: [],
  printFriends() {
    this._friends.forEach(f =>
      console.log(this._name + " knows " + f)
      // `this` ne réfère pas à la fonction fléchée du forEach !
    )
  }
}
```

il peut être possible de ne plus avoir besoin du `bind() aussi souvent que ça pouvait être le cas.


###### Contributeurs :

Sara Attallah Gherardi

Aurélie Baliry

Anthony Dias

Marie-Lise Ton