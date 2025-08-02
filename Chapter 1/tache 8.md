
```haskell
-- Applique une fonction deux fois à une valeur d'entrée
applyTwice :: (a -> a) -> a -> a
applyTwice f x = f (f x)

-- Fonction principale pour tester
main :: IO ()
main = do
    print (applyTwice (+1) 5)  -- Applique l'incrémentation deux fois
    print (applyTwice (*2) 3)  -- Applique le doublement deux fois
```

### Explication ligne par ligne :

1. ```haskell
   -- Applique une fonction deux fois à une valeur d'entrée
   ```
   - Commentaire décrivant la fonction `applyTwice`, qui applique une fonction donnée deux fois à une valeur.

2. ```haskell
   applyTwice :: (a -> a) -> a -> a
   ```
   - Signature de type de `applyTwice`.
   - `(a -> a) -> a -> a` indique que la fonction prend :
     - Une fonction de type `a -> a` (une fonction qui prend une valeur de type `a` et retourne une valeur du même type `a`).
     - Une valeur de type `a` (l'entrée à laquelle la fonction sera appliquée).
     - Retourne une valeur de type `a` (le résultat après deux applications de la fonction).
   - Le type générique `a` permet à `applyTwice` de fonctionner avec n'importe quel type, tant que la fonction fournie prend et retourne le même type.

3. ```haskell
   applyTwice f x = f (f x)
   ```
   - Définit la fonction `applyTwice` qui prend deux paramètres :
     - `f` : la fonction à appliquer.
     - `x` : la valeur d'entrée.
   - `f (f x)` applique `f` une première fois à `x`, puis applique `f` une seconde fois au résultat.
   - Exemple :
     - `applyTwice (+1) 5` calcule `(+1) ((+1) 5)` = `(+1) 6` = `7`.
     - `applyTwice (*2) 3` calcule `(*2) ((*2) 3)` = `(*2) 6` = `12`.

4. ```haskell
   -- Fonction principale pour tester
   ```
   - Commentaire décrivant la fonction `main`, utilisée pour tester `applyTwice`.

5. ```haskell
   main :: IO ()
   ```
   - Signature de type de `main`, le point d’entrée du programme, avec le type `IO ()` pour les actions d’entrée/sortie.

6. ```haskell
   main = do
   ```
   - Débute un bloc `do` pour séquencer plusieurs actions `IO`.

7. ```haskell
   print (applyTwice (+1) 5)  -- Applique l'incrémentation deux fois
   ```
   - Appelle `applyTwice` avec la fonction `(+1)` (incrémentation) et la valeur `5`.
   - Calcule `(+1) ((+1) 5)` = `(+1) 6` = `7`.
   - `print` affiche `7` dans la console.

8. ```haskell
   print (applyTwice (*2) 3)  -- Applique le doublement deux fois
   ```
   - Appelle `applyTwice` avec la fonction `(*2)` (doublement) et la valeur `3`.
   - Calcule `(*2) ((*2) 3)` = `(*2) 6` = `12`.
   - `print` affiche `12` dans la console.


