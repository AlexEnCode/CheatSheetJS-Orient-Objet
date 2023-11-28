# Programmation Orientée Objet (POO) en JavaScript
## Classes et Objets

### Définition d'une classe

```JS
class NomDeLaClasse {
    constructor(parametres) {
        // Initialisation des attributs de l'instance
        this.attribut_instance = parametres;
    }

    // Méthodes de classe
    nomMethode() {
        // Corps de la méthode
    }
}
```

## Instanciation d'un objet


L'instanciation d'un objet en JavaScript fait référence au processus de création d'une occurrence particulière d'une classe ou d'un type d'objet. En d'autres termes, lorsque vous avez défini une classe, vous pouvez créer des objets spécifiques basés sur cette classe, et ce processus est appelé instanciation.
``` JS
// Création d'une instance de la classe
const objet = new NomDeLaClasse(parametres);
```
## Attributs et Méthodes
### Attributs de classe
Les attributs de classe sont des variables partagées par toutes les instances d'une classe. Ces attributs sont définis avec le mot-clé static. Ils appartiennent à la classe elle-même plutôt qu'à une instance spécifique.

``` JS
class MaClasse {
    static attribut_classe = valeur;
}
```
### Attributs d'instance
Les attributs d'instance sont des variables associées à chaque instance particulière d'une classe. Chaque instance d'une classe peut avoir ses propres valeurs pour ces attributs. Par exemple, dans le contexte d'un objet représentant une personne, l'attribut nom peut être un attribut d'instance.
``` JS
class MaClasse {
    constructor(parametre) {
        this.attribut_instance = parametre;
    }
}
```
### Méthodes
Les méthodes sont des fonctions définies à l'intérieur d'une classe et sont associées aux objets créés à partir de cette classe. Les méthodes peuvent accéder aux attributs de l'instance ainsi qu'à d'autres méthodes de la classe.



``` JS
class MaClasse {
    methode(parametres) {
        // Corps de la méthode
    }
}
```
## Héritage
L'héritage d'objet en JavaScript fait référence à la capacité pour un objet de partager les propriétés et les méthodes d'un autre objet. Il permet la création d'une hiérarchie entre les objets, où un objet peut hériter des caractéristiques d'un autre. En JavaScript, l'héritage est basé sur le prototype, et la liaison entre les objets est réalisée à l'aide du prototype.
### Définition d'une classe héritée
``` JS
class ClasseFille extends ClasseMere {
    methodeFille() {
        // Appel de la méthode de la classe mère
        super.methodeMere();
    }
}
```
### Appel de méthodes de la classe mère
``` JS
class ClasseFille extends ClasseMere {
    methodeFille() {
        // Appel de la méthode de la classe mère
        super.methodeMere();
    }
}
```
## Encapsulation

L'encapsulation consiste à regrouper les données (attributs) et les méthodes qui agissent sur ces données au sein d'une même unité, appelée classe. En JavaScript, bien que le langage ne fournisse pas de véritable support pour les attributs privés ou protégés, l'encapsulation peut être partiellement réalisée en utilisant des conventions de nommage ou en utilisant les closures.
### Attributs privés
```JS
class MaClasse {
    #attributPrive;

    constructor() {
        this.#attributPrive = valeur;
    }

    getAttributPrive() {
        return this.#attributPrive;
    }

    setAttributPrive(nouvelleValeur) {
        this.#attributPrive = nouvelleValeur;
    }
}
```
## Polymorphisme

Le polymorphisme permet à des objets de différentes classes d'être traités de manière uniforme s'ils possèdent une méthode commune. En JavaScript, cela peut être obtenu en redéfinissant des méthodes dans les sous-classes, permettant à ces sous-classes de partager une interface commune.
### Surcharge de méthodes


La surcharge de méthode, telle qu'elle est comprise dans certains langages de programmation, n'est pas directement prise en charge en JavaScript. La surcharge de méthode consiste à définir plusieurs méthodes dans une même classe avec des signatures différentes, c'est-à-dire des paramètres différents.

Cependant, JavaScript ne gère pas la surcharge de méthode de manière explicite comme certains langages le font, comme Java ou C#. En JavaScript, lorsqu'une méthode est définie plusieurs fois dans une même classe avec le même nom, la dernière définition écrase les précédentes. Les méthodes sont donc redéfinies plutôt que surchargées.
exemple : 
```JS
class Exemple {
    // Méthode initiale
    maMethode(parametre) {
        console.log(`Version initiale avec un paramètre : ${parametre}`);
    }

    // Redéfinition de la méthode avec un paramètre différent
    maMethode(parametre1, parametre2) {
        console.log(`Redéfinition avec deux paramètres : ${parametre1}, ${parametre2}`);
    }
}

const exemple = new Exemple();

// Appel de la méthode
exemple.maMethode("Premier");  // Affiche "Redéfinition avec deux paramètres : Premier, undefined"
```
Dans cet exemple, la deuxième définition de maMethode a remplacé la première. Lorsque vous appelez la méthode avec un seul paramètre, JavaScript ne génère pas d'erreur, mais le deuxième paramètre est undefined.


### Redéfinition de méthodes
```JS
class ClasseMere {
    methode() {
        // Corps de la méthode
    }
}

class ClasseFille extends ClasseMere {
    methode() {
        // Corps de la méthode redéfinie
    }
}
```
N'oubliez pas que JavaScript est un langage à prototype, et bien que les classes aient été introduites dans ECMAScript 6, l'héritage se fait toujours via des prototypes en interne. Adaptation possible pour les environnements Node.js et les navigateurs modernes.