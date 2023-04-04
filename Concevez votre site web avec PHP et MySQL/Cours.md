
## Règles du PHP

On peut :

* Insérez une balise PHP au milieu du code HTML
* On peut placer une balise PHP n'importe où dans le code
* Une ligne se términe par "**;**"

## Reconnaître une balise PHP

Les différents types de balise pour du PHP :

```
<?php ?>
<? ?> 
<% %> 
<?= ?>
```
## Types

Sous PHP les types sont :

* string
* int
* float
* bool
* NULL

Mais à la déclaration les types n'ont pas besoin d'être déclaré, PHP le fait automatiquement

Le string peut être définie sous les formes :

* "texte"
* 'texte'

## Variables 

Une variable est définie par "**$variable**"

Cela donne :

```
<?php
$variable = "truc"; 
$variable = 23; 
$variable = 23.2; 
?>
```

Pour concaténer une variable l'on utilise "**.**"
Ce qui donne :

```
<?php
$fullname = 'Baptiste';
echo 'Bonjour ' . $fullname . ' et bienvenue sur le site !'; 
?>
```

## Conditions
### Et, Ou, Non, Egal, Comparaisons

Sous PHP les condiotions logiques sont :

* Et (&&)
* Ou (||)
* Non (!)
* Egal (==) (Fonctionne même pour les string)
* Comparaisons (>, <, >=, <=)


### If, Else, Elseif

```
<?php
$condition = "Oui";

if ($condition == "Oui") {
    // instructions à exécuter quand on est autorisé à entrer
}
elseif ($condition == "Non") {
    // instructions à exécuter quand on n'est pas autorisé à entrer
}
else {
    echo "Euh, je ne comprends pas ton choix, tu peux me le rappeler s'il te plaît ?";
}
?>
```

### If sur une balise

L'ont peut utiliser une condition pour l'affichage d'une balise précise <br>
La syntaxe pour utiliser la condition diffère un peu :

* Il n'y a pas d'accolade.
* On ajoute  :  après la parenthèse fermante de l'instruction  if  .
* Et il faut ajouter une instruction  endif;

Ce qui donne :
```
<?php $condition = true; ?>

<?php if ($condition): ?>      <!-- Ne pas oublier le ":" -->

<h1>Texte à afficher</h1>

<?php endif; ?>       <!-- Ni le ";" après le endif -->
```

### Switch

Dans le cas où on veut faire un If avec beaucoup de comparaison égale (==), switch permet de faire cela :<br>
*Le switch ne peut tester que l'égalité. Cela ne marche pas avec les autres symboles :< > <= >= !=*

```
<?php
$grade = 10;

switch ($grade) // on indique sur quelle variable on travaille
{ 
    case 0: // dans le cas où $grade vaut 0
        echo "Tu es vraiment un gros nul !!!";
    break;
    
    case 5: // dans le cas où $grade vaut 5
        echo "Tu es très mauvais";
    break;
    
    case 7: // dans le cas où $grade vaut 7
        echo "Tu es mauvais";
    break;
    
    case 10: // etc. etc.
        echo "Tu as pile poil la moyenne, c'est un peu juste…";
    break;
    
    case 12:
        echo "Tu es assez bon";
    break;
    
    case 16:
        echo "Tu te débrouilles très bien !";
    break;
    
    case 20:
        echo "Excellent travail, c'est parfait !";
    break;
    
    default:
        echo "Désolé, je n'ai pas de message à afficher pour cette note";
}
?>
```

Pour faire switch : 

* On indique au début du switch sur quelle variable on travaille, ici $grade
* On utilise des case pour analyser chaque cas : case 0 ,case 10 , etc. 
* Le mot-clé default à la fin est un peu l'équivalent du else

Mais contrairement aux elseif ,  PHP ne s'arrête pas là et continue à lire les instructions des cases qui suivent !<br>
**Pour empêcher cela, utilisez l'instruction break !**

### Ternaires

Il existe une autre forme de condition, beaucoup moins fréquente, ll s'agit de ce qu'on appelle les ternaires.

Un ternaire est une condition condensée qui sert à faire deux choses sur une seule ligne :

* Tester la valeur d'une variable dans une condition.
* Affecter une valeur à une variable selon que la condition est vraie ou non.

Il y à 2 façons d'en faire :

```
<?php
$userAge = 24;

$isAdult = ($userAge >= 18) ? true : false;

// Ou mieux, dans ce cas précis
$isAdult = ($userAge >= 18);
?>
```

## Regroupement de fonctions

### echo()

L'instruction echo, on écrit l'instruction "**echo**" suivie du texte à afficher entre guillemets. <br>
Il faut savoir qu'on a aussi le droit de demander d'afficher des balises. Par exemple, le code suivant fonctionne :

```
<?php echo "Ceci est du <strong>texte</strong>"; ?>
```

Pour utiliser des guillemets ont protège en utilisant un antislash

```
<?php echo "Cette ligne a été écrite \"uniquement\" en PHP."; ?>
```

### infos(

**infos** permet de faire script pour afficher les informations relatives à PHP pour le serveur web ; cela va nous donner toutes les informations de PHP

```
<?php

phpinfo(;
```