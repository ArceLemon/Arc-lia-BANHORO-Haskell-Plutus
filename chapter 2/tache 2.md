HC2T2 - Tâche 2 : Signatures de fonctions

CODE:

```haskell
-- Ajoute deux entiers
ajouter :: Int -> Int -> Int
ajouter x y = x + y

-- Vérifie si un entier est pair
isEven :: Int -> Int -> Bool
isEven n1 n2 = n1==n2 

-- Concatène deux chaînes de caractères
concatStrings :: String -> String -> String
concatStrings s1 s2 = s1 ++ s2

-- Fonction principale pour tester
main :: IO ()
main = do
    print (ajouter 3 5)
    print (isEven 4 6)
    print (isEven 7 7)
    print (concatStrings "Hello, " "World!")
```


### Explications ligne par ligne :

1. ```haskell
   -- Ajoute deux entiers
   ```
   - Commentaire décrivant la fonction `ajouter`.

2. ```haskell
   ajouter :: Int -> Int -> Int
   ```
   - Signature de type de `ajouter`.
   - Prend deux `Int` comme arguments (`x` et `y`) et retourne un `Int` (leur somme).

3. ```haskell
   ajouter x y = x + y
   ```
   - Implémentation de `ajouter`.
   - Additionne `x` et `y` avec l'opérateur `+`.
   - Exemple : `ajouter 3 5` retourne `8`.

4. ```haskell
   -- Vérifie si un entier est pair
   ```
   - Commentaire décrivant la fonction `isEven`.

5. ```haskell
   isEven :: Int -> Bool
   ```
   - Signature de type de `isEven`.
   - Prend un `Int` (`n`) et retourne un `Bool` (vrai si pair, faux sinon).

6. ```haskell
   isEven n1 n2 = n1 == N2
   ```
   - Implémentation de `isEven`.
   - Compare les 02 nombres avec `== ` : si égal, alors true.
   - Exemple : `isEven 4 6` retourne `False`, `isEven 7 7` retourne `True`.

7. ```haskell
   -- Concatène deux chaînes de caractères
   ```
   - Commentaire décrivant la fonction `concatStrings`.

8. ```haskell
   concatStrings :: String -> String -> String
   ```
   - Signature de type de `concatStrings`.
   - Prend deux `String` (`s1` et `s2`) et retourne un `String` (leur concaténation).
   - Note : `String` est un synonyme de `[Char]` en Haskell.

9. ```haskell
   concatStrings s1 s2 = s1 ++ s2
   ```
   - Implémentation de `concatStrings`.
   - Utilise l'opérateur `++` pour concaténer `s1` et `s2`.
   - Exemple : `concatStrings "Hello, " "World!"` retourne `"Hello, World!"`.

10. ```haskell
    -- Fonction principale pour tester
    ```
    - Commentaire décrivant la fonction `main`.

11. ```haskell
    main :: IO ()
    ```
    - Signature de type de `main`, le point d’entrée du programme, avec le type `IO ()` pour les actions d’entrée/sortie.

12. ```haskell
    main = do
    ```
    - Débute un bloc `do` pour séquencer plusieurs actions `IO`.

13. ```haskell
    print (ajouter 3 5)
    ```
    - Teste `ajouter` avec `3` et `5`, affiche `8`.

14. ```haskell
    print (isEven 4)
    ```
    - Teste `isEven` avec `4`, affiche `True`.

15. ```haskell
    print (isEven 7)
    ```
    - Teste `isEven` avec `7`, affiche `False`.

16. ```haskell
    print (concatStrings "Hello, " "World!")
    ```
    - Teste `concatStrings` avec `"Hello, "` et `"World!"`, affiche `"Hello, World!"`.

### Résultat de l’exécution :
Lors de l’exécution, le programme affiche :
```
8
False
True
"Hello, World!"
```
