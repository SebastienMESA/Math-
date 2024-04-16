# "Il nous emmerdent les Math...()"

## Le Math.random()

- **Math.random()** nous permet de générer un nombre aléatoire entre 0 **inclus** et 1 **exclus** :

```Javascript
const random = Math.random();

console.log(random) // => ( **JE SUIS LA CONSOLE** exemple 1 : 0.0155949863, exemple 2 : 0.84321563)
```

- Du coup, si on veut un nombre aléatoire entre 0 **inclus** et 10 **exclus** ? Comment qu'on fait donc ? 

Et bien il suffit de multiplier notre **Math.random()** par 10 

si on reprends les exemples ci-dessus mais en multipliant par 10 :

```Javascript
const random = Math.random() * 10;

console.log(random) // => ( **JE SUIS LA CONSOLE** exemple 1 : 0.155949863, exemple 2 : 8.4321563)
```

## Le Math.floor() et le Math.ceil()


- **Math.floor()** permet d'arrondir à l'entier **inférieur**, par exemple :

```Javascript
// EXEMPLE 1

const nombreDécimal = 4.45659834

console.log(Math.floor(nombreDécimal)) // => ( **JE SUIS LA CONSOLE** : 4)

//EXEMPLE 2

const nombreDécimal = 5.9999999999

console.log(Math.floor(nombreDécimal)) // => ( **JE SUIS LA CONSOLE** : 5)
```

- A l'inverse **Math.ceil()** permet d'arrondir à l'entier **supérieur**, par exemple :

```Javascript
//EXEMPLE 1

const nombreDécimal = 4.45659834
console.log(Math.ceil(nombreDécimal)) // => ( **JE SUIS LA CONSOLE** : 5)

//EXEMPLE 2 

const nombreDécimal = 5.00000001
console.log(Math.ceil(nombreDécimal)) // => ( **JE SUIS LA CONSOLE** : 6)
```

_* POUR INFO : En anglais, floor veut dire le sol, le "par-terre" ce qu'il y a sous nos pieds. Ceiling veut dire le plafond. Ça peut aider pour se souvenir_


## Combiner Math.random() avec Math.floor() et Math.ceil()

- Combiner les fonctions **Math.random()** avec **Math.floor()** et **Math.ceil()** nous permets d'obtenir des nombres **ENTIERS** aléatoires ! (youpi)

![gif kaamelot "Qu'est-ce que voulez vous dire Sire ?"](https://kaamelott-gifboard.fr/gifs/que-voulez-vous-dire.gif)

Essayons de générer aléatoirement un nombre entier compris entre 0 **inclus** et 10 **exclus**
Avec ce qu'on a vu au-dessus en faite on sait déjà le faire :

```Javascript
//EXEMPLE

const random = Math.random() * 10;
console.log(random) // => ( **JE SUIS LA CONSOLE** exemple 1 : 1.245657156, exemple 2 : 8.02126374)

console.log(Math.floor(random)) // => ( **JE SUIS LA CONSOLE** exemple 1 : 1, exemple 2 : 8)
```

Mais du coup si on ne veut pas s'embêter avec des variables qui nous donnent des nombres décimaux dont on se fout, on peut tout faire d'un coup :

```Javascript
//EXEMPLE 

const randomInteger = Math.floor(Math.random() * 10)
console.log(randomInteger) // => ( **JE SUIS LA CONSOLE** exemple 1 : 1, exemple 2 : 8)
```
### _"Ok cool, mais moi je veux générer aléatoirement un nombre entier compris entre 0 **inclus** et 10 **inclus**"_

**Math.random() * 10**,comme on l'a vu, ne donnera jamais 10. Le plus grand chiffre qu'elle pourra donner c'est 9.999999...

DONC **Math.floor(Math.random() * 10)** donnera au maximum 9 (_puisque Math.floor(9.9999999) = 9_) 

De la même façon **Math.floor(Math.random() * 11)** donnera au maximum 10.

En code parce que c'est plus joli :

```Javascript
const randomInteger = Math.floor(Math.random() * 11)
```
La variable (constante) randomInteger nous fournira toujours un nombre entier compris entre 0 et 10.

### _"Super mais, le 0 il m'embête, je ne veux pas que ça tombe sur 0, je veux générer un nombre aléatoire entre 1 **inclus** et 10 **inclus** maintenant"_

Rien de plus simple, on a vu un tout petit peu au dessus quelque chose comme ça :
```Javascript
const randomInteger = Math.floor(Math.random() * 10)
```
La variable randomInteger juste au dessus nous donne un nombre entier compris entre 0 et 9, c'est quasiement ce qu'on veut ! Il y'a juste un +1 a mettre quelque part... Mais ou donc qu'il faut le mettre ?

Pour paraphraser, randomInteger nous donnera au minimum 0 et au maximum 9, ne suffirait-il pas d'ajouter 1 au résultat final pour générer un nombre entre 1 et 10 ?

Je vous propose donc ça : 

```Javascript
const randomInteger = Math.floor(Math.random() * 10) + 1
```

### _"Et le Math.ceil() dans tout ça ?"_

Et bien il doit avoir son utilité, c'est sûr, mais à vrai dire j'en sais rien. Je n'ai tout simplement pas assez d'expèrience pour vous dire à quoi il pourrait servir mais on sait qu'il existe et on l'oublie pas (on l'aime bien au village quoi)