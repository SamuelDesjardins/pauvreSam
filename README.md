# Travail pratique 3 (20% du Tp Synthèse)

Date de remise : 18 décembre 2020

## Problème 1 (2/50 points du Tp Synthèse)

Matière : Héritage

Compléter le code suivant

```java
// Classe de base Point  (un point avec abscisse x, ordonnée y)
public class Point 
{
    // "protected" veut dire accessible dans les classes dérivées
    protected int x;
    protected int y;
    
    public Point(int x, int y)
    {
        /* ...::: À COMPLÉTER :::...
         *
         * initialiser x et y
         */
    }
    
    public Point()
    {
        /* ...::: À COMPLÉTER :::...
         *
         * Appeler Point(int, int) pour initialiser à zéro les coordonnées du point à zéro.
         */
    }

    // Redéfinition de Object.equals()
    @Override
    public boolean equals(Point autre)
    {
        /* ...::: À COMPLÉTER :::... */
    }

    public boolean different(Point autre) 
    {
        /* ...::: À COMPLÉTER :::...
         * 
         * utiliser equals()
         */
    }

    public void translater(int unite)
    {
        /* ...::: À COMPLÉTER :::...
         *
         * NOTES : Pour une translation, il faudrait dx & dy, alors 
         * c'est difficile de comprendre ce que le prof veut ici....
         */
    }

    public void afficher(String nom)
    {
        System.out.println("Point " + nom + " : <" + x + ", " + y + ">");
    }
}

// Héritage simple : un Point qui possède une couleur et qui peut être visible ou non.
public class PointColoreVisible extends Point
{
    private int couleur;
    private boolean visible = true;

    // constructeur #1
    public PointColoreVisible(int abs, int ord, int c)
    {
        /** ...::: À COMPLÉTER :::...
         * 
         * Utiliser le constructeur de la superclasse.
         * Ne pas oublier la couleur.
         */
    }

    // constructeur #2
    public PointColoreVisible(int abs, int ord, int c, boolean v)
    {
        /** ...::: À COMPLÉTER :::...
         * 
         * Utiliser le constructeur de CETTE classe-ci.
         * Ne pas oublier la couleur et l'attribut "visible".
         */
    }

    // Redéfinition de Point.afficher()
    @Override
    public void afficher(String nom)
    {
        System.out.println("\nLe point " + nom);
        System.out.println( (visible ? "est lisible":"non visible") );
        System.out.println("valeur de couleur  : " + couleur);
        System.out.println("abscisse : " + x);
        System.out.println("ordonnee : " + y);
        System.out.println();
    }

    public void afficher(String nom, String bidon)
    {
        System.out.println();
        /** ...::: À COMPLÉTER :::...
         * 
         * ABSOLUMENT IMPOSSIBLE de comprendre ce que le prof veut ici.
         * Le prof laisse la note "appel de la méthode afficher() de la superclasse",
         * mais aucune idée pourquoi quelqu'un voudrait faire ça. Aucune idée à quoi
         * sert la String "bidon".
         * 
         * Mon meilleur guess serait de caller super.afficher(), mais ça fait
         * vraiment aucun sens, surtout quand tu viens juste de bien 
         * définir PointColoreVisible.afficher().
         */
        System.out.println( (visible ? "est lisible":"non visible") );
        System.out.println("valeur de couleur  : " + couleur);
        System.out.println();
    }
}

public class Tester
{
    public static void main (String[] args)
    {
        /** ...::: À COMPLÉTER :::...
         * 
         * 1. Création Point p1 à [12, 6].
         * 2. Afficher p1.
         * 3. Création d’un Point p2 par défaut.
         * 4. Afficher p2.
         * 5. Création d’un PointColoreVisible p3 à [5, 8] et de couleur 12.
         * 6. Afficher p3.
         * 7. Création d’un PointColoreVisible p4 à [25, 12], de couleur 3 et NON-VISIBLE.
         * 8. Afficher p4.
         * 9. création d’un Point p5 à [12, 6].
         */

        if (/* appel à la méthode equals() de la classe Point */) {
            System.out.println("p1 est identique a p5");
        }
        if (/* appel à la méthode different() de la classe Point */) {
            System.out.println("p1 est different de p2");	      
        }

        /** Notes : c'est absolument absurde de faire if (p1.equals(p2)) { ... } if (p1.different(p2)) { ... }
         * 
         * C'est genre du 1ere sesssion : if (p1.equals(p2)) { ... } else { ... }
         * 
         * Même pour des raisons pédagogiques genre "un example pour expliquer l'héritage" ça fait aucun sens.
         */
      
        /** ...::: À COMPLÉTER :::...
         * 
         * 1. Translater le p3 de 10 unités.
         * 2. Appel de la méthode afficher(String nom, String bidon) de PointColoreVisible pour p3
         */
    }
}
```

L'exécution devrait produire le résultat suivant : 

```
Point p1 : <12, 6>
Point p2 : <0, 0>

Le point p3
est lisible
valeur de couleur  : 12
abscisse : 5
ordonnee : 8

Le point p4
non visible
valeur de couleur  : 3
abscisse : 25
ordonnee : 12

p1 est identique a p5
p1 est different de p2
```

## Problème 2 (3/50 points du Tp Synthèse)

Matière : Héritage

Concevoir un programme qui utilise l’héritage. Votre programme devra contenir les classes suivantes :

```java
class Rectangle (la super-classe) {
    private int longueur;
    private int largeur;

    /** ...::: À COMPLÉTER :::...
     * 
     * Ajouter les éléments suivants :
     * 
     * 1. Un constructeur par défaut.
     * 2. Un constructeur qui peut initialiser les attributs private à des valeurs arbitraires.
     * 3. Une méthode perimetre().
     * 4. Une méthode afficher() qui affiche des détails sur un rectangle : longueur, largeur et périmètre.
     */
}
```

```java
class Carre /* une sous-classe de Rectangle */ {
    private int cote;
    
    /** ...::: À COMPLÉTER :::...
     * 
     * Ajouter les éléments suivants :
     * 
     * 1. Un constructeur par défaut.
     * 2. Un constructeur qui peut initialiser l’attribut private à une valeur arbitraire.
     *    Il doit utiliser le constructeur de la super-classe.
     * 3. Une méthode surface() pour claculer l'aire.
     * 4. Une méthode afficher(String nom) qui affiche des détails sur un carré : nom, coté,
     *    périmètre, et surface.
     * 5. Une méthode afficher() surdéfinition de la méthode afficher() de Rectangle. Elle
     *    fait appel à la méthode afficher() de Rectangle.
     * 
     * NOTES : Difficile de savoir ce que #5 veut dire.
     */
}
```

```java
class TestHeritage {
    /** ...::: À COMPLÉTER :::...
     * 
     * Crée un carré.
     * 
     * Ses caractéristiques seront ensuite affichées selon l’exécution fournie : d’abord en tant qu’un
     * carré et après en tant qu’un rectangle. À noter que la classe Rectangle ne dispose pas de méthode
     * pour le calcul de la surface.
     * 
     * NOTES : ??? I guess qu'il veut que tu créer un Carre mais que tu appelles explicitement les méthodes
     * de Rectangle dessus. Une très mauvaise idée.
     */
}
```

L'exécution devrait produire le résultat suivant :

```
En tant qu'un carre : 
Carre c1 (methode d'affichage d'un carre)
Cote : 5
Perimetre : 20
Surface   : 25
En tant que rectangle : < longueur : 5, largeur : 5>
Perimetre : 20
Surface   : 25
```

## Problème 3 (7/50 points du Tp Synthèse)

Matière : Héritage, polymorphisme

Concevoir un programme qui utilise l’héritage et le polymorphisme pour la gestion d’un concessionnaire d’autos.

Votre programme devra contenir les classes suivantes :

1. La classe `Auto` qui contient des champs et des méthodes pour une description initiale d’une voiture :
    1. la disponibilité
    2. la couleur
    3. le prix (voir le fichier AutoEtud.java fourni).
2. Les classes `Ford`, `Mazda`, `Chrysler` et `Mercedes`. Elles seront des sous-classes de la classe `Auto` (voir le fichier fourni pour la classe `Ford`). Ces classes fourniront les champs et les méthodes nécessaires pour décrire complètement une voiture. Dans ces classes, vous devrez redéfinir les méthodes suivantes de la super classe Auto:
    1. `estDisponible()` : afficherer les messages suivants :
        - Si le nombre de voitures en stock et 0 : « _Voiture à commander !!_ »
        - Si la voiture n’est pas préparée : « _Voiture en stock, mais pas prête !!_ »
        - La méthode `estDisponible()` de la super-classe doit être utilisée.
    2. `afficher()` : afficher les informations sur la marque, le modèle et l’année de fabrication (champs privés de chaque classe dérivée). La méthode `afficher()` de la super-classe doit aussi être utilisée.

3. La classe principale `TestAuto` qui créera un tableau de 4 objets de type `Auto`. Chaque élément `Auto` du tableau représentera une référence sur des objets de type `Ford`, `Chrysler`, `Mazda` et `Mercedes` respectivement (utilisez le polymorphisme). Elle affichera ensuite les autos du tableau avec la méthode `afficher()` (redéfinie dans chaque sous classe) pour obtenir les informations complètes sur les objets du tableau.

__EN PLUS__, vous devrez modifier le prix initial de chaque voiture en ajoutant 2000 $ si l’année est 2020 ou en diminuant le prix initial de 500 $ si l’année est 2019.

## Problème 4 (8/50 points du Tp Synthèse)

Matière : Classes abstraites et interface

Concevoir un programme qui utilise l’héritage, le polymorphisme et les interfaces. Votre programme aura les classes suivantes:

1. `interface Comparable` : Voir le fichier fourni.
2. `class PersInterf implements Comparable` : Compléter le fichier fourni. Dans cette classe vous allez redéfinir la méthode `toString()` afin d'afficher les champs privés. Cette classe ne contient pas de méthode d'affichage. La méthode `plusPetit()` fera la comparaison des tailles des personnes.
3. `class RectInterf implements Comparable` : Compléter le fichier fourni. Dans cette classe vous allez redéfinir la méthode `toString()` afin d'afficher les champs privés. Cette classe ne contient pas de méthode d'affichage. La méthode `plusPetit()` fera la comparaison des surfaces des rectangles.
4. `class Tri` : Suivre les indications du fichier fourni.
5. `class TestInterface` : Compléter le fichier fourni.

L'exécution devrait produire le résultat suivant : 

```
Liste des PersInterfs avant le tri
M mesure 1.75 metre et pese 65.3 kgs
F mesure 1.62 metre et pese 69.1 kgs
F mesure 1.89 metre et pese 76.5 kgs
M mesure 1.45 metre et pese 50.3 kgs
M mesure 1.77 metre et pese 90.1 kgs

Liste des PersInterfs apres le tri
M mesure 1.45 metre et pese 50.3 kgs
F mesure 1.62 metre et pese 69.1 kgs
M mesure 1.75 metre et pese 65.3 kgs
M mesure 1.77 metre et pese 90.1 kgs
F mesure 1.89 metre et pese 76.5 kgs

Liste des RectInterfs avant le tri selon la surface : 
<longueur : 12, 5, surface : 60>
<longueur : 9, 6, surface : 54>
<longueur : 60, 12, surface : 720>
<longueur : 5, 12, surface : 60>

Liste des RectInterfs apres selon la surface : 
<longueur : 9, 6, surface : 54>
<longueur : 12, 5, surface : 60>
<longueur : 5, 12, surface : 60>
<longueur : 60, 12, surface : 720>
*/
