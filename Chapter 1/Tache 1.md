HC1T1 - Tâche 1 : Composition de fonctions

CODE: 
```haskell
-- Multiplie un nombre par 2
double :: Int -> Int
double x = x * 2

-- Augmente un nombre de 1
incrementation :: Int -> Int
incrementation x = x + 1

-- Composition de double puis increment
doubleThenIncrement :: Int -> Int
doubleThenIncrement = incrementation . double

-- Fonction principale
main :: IO ()
main = do
    print (double 2)
    print (incrementation 2)
    print (doubleIncrement 2)
```   


`EXPLICATION: 



```haskell
-- Multiplie un nombre par 2
```
- Un commentaire en Haskell, commençant par `--`, qui décrit la fonction suivante. Il indique que la fonction va multiplier un nombre par 2.

```haskell
double :: Int -> Int
```
- Déclare la **signature de type** de la fonction `double`.
- `::` indique une déclaration de type.
- `Int -> Int` signifie que la fonction prend un entier (`Int`) en entrée et retourne un entier (`Int`) en sortie.

```haskell
double x = x * 2
```
- Définit la fonction `double`, qui prend un paramètre `x` (un entier).
- L'expression `x * 2` multiplie `x` par 2 et retourne le résultat.
- Par exemple, `double 2` retourne `2 * 2 = 4`.

```haskell
-- Augmente un nombre de 1
```
- Un commentaire décrivant la fonction suivante, qui augmente un nombre de 1.

```haskell
incrementer :: Int -> Int
```
- Déclare la signature de type de la fonction `incrementer`.
- Comme pour `double`, elle prend un `Int` et retourne un `Int`.

```haskell
incrementer x = x + 1
```
- Définit la fonction `incrementer`, qui prend un paramètre `x` (un entier).
- L'expression `x + 1` ajoute 1 à `x` et retourne le résultat.
- Par exemple, `incrementer 2` retourne `2 + 1 = 3`.

```haskell
-- Composition de double puis increment
```
- Un commentaire expliquant que la fonction suivante combine `double` et `incrementer` via la composition.

```haskell
doubleIncrement :: Int -> Int
```
- Déclare la signature de type de la fonction `doubleIncrement`.
- Elle prend un `Int` et retourne un `Int`, comme les fonctions précédentes.

```haskell
doubleIncrement = incrementer . double
```
- Définit la fonction `doubleIncrement` en utilisant l'**opérateur de composition** `.`.
- L'opérateur `.` combine deux fonctions : `(f . g) x` signifie `f (g x)`.
- Ici, `incrementer . double` signifie que `double` est appliqué en premier, puis `incrementer` sur le résultat.
- Par exemple, pour `x = 2`, `doubleIncrement 2` calcule `incrementer (double 2)` = `incrementer (4)` = `4 + 1 = 5`.

```haskell
-- Fonction principale
```
- Un commentaire indiquant que la fonction suivante est la fonction principale du programme.

```haskell
main :: IO ()
```
- Déclare la signature de type de la fonction `main`, qui est le point d'entrée d'un programme Haskell.
- `IO ()` indique que la fonction effectue des opérations d'entrée/sortie (IO) et ne retourne aucune valeur significative (le type `()` représente "vide" ou "rien").

```haskell
main = do
```
- Marque le début d'un bloc `do`, utilisé pour séquencer des actions dans le contexte des entrées/sorties en Haskell.

```haskell
    print (double 2)
```
- Applique la fonction `double` à la valeur `2`, ce qui donne `double 2 = 4`.
- La fonction `print` affiche le résultat dans la console.
- `print` convertit automatiquement la valeur en une chaîne de caractères et l'affiche, suivie d'un saut de ligne.
- Cette ligne affichera donc `4` dans la console.

```haskell
    print (incrementer 2)
```
- Applique la fonction `incrementer` à la valeur `2`, ce qui donne `incrementer 2 = 3`.
- `print` affiche le résultat dans la console.
- Cette ligne affichera donc `3` dans la console.

```haskell
    print (doubleIncrement 2)
```
- Applique la fonction `doubleIncrement` à la valeur `2`, ce qui donne `doubleIncrement 2 = incrementer (double 2) = incrementer 4 = 5`.
- `print` affiche le résultat dans la console.
- Cette ligne affichera donc `5` dans la console.

### Résultat d'exécution
Quand ce programme est exécuté, il affiche dans la console :
```
4
3
5
```
- Chaque appel à `print` affiche une ligne distincte, correspondant aux résultats de `double 2`, `incrementer 2`, et `doubleIncrement 2`.

### Résumé
- Les fonctions `double`, `incrementer`, et `doubleIncrement` définissent des transformations sur des entiers : multiplication par 2, ajout de 1, et leur composition.
- La fonction `doubleIncrement` utilise la composition pour appliquer `double` puis `incrementer`.
- La fonction `main` teste ces trois fonctions avec la valeur `2` et affiche leurs résultats à l'aide de `print`.
- Ce code illustre des concepts fondamentaux de Haskell : fonctions pures, composition de fonctions, et gestion des entrées/sorties avec `IO`.
