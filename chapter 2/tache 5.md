HC2T5 - Tâche 5 : et utiliser des fonctions

```haskell
-- Calcule l'aire d'un cercle à partir de son rayon
cercleArea :: Float -> Float
cercleArea r = pi * r * r

-- Retourne la valeur maximale parmi trois entiers
maxOfThree :: Int -> Int -> Int -> Int
maxOfThree x y z = max (max x y) z

-- Fonction principale pour tester
main :: IO ()
main = do
    -- Tests pour cercleArea
    print (cercleArea 2.0)    -- Rayon 2.0
    print (cercleArea 5.5)    -- Rayon 5.5
    print (cercleArea 0.0)    -- Rayon 0.0

    -- Tests pour maxOfThree
    print (maxOfThree 3 7 1)  -- 3, 7, 1
    print (maxOfThree 10 10 5) -- 10, 10, 5
    print (maxOfThree 15 8 12) -- 15, 8, 12
```

### Explications ligne par ligne :

1. ```haskell
   -- Calcule l'aire d'un cercle à partir de son rayon
   ```
   - Commentaire décrivant la fonction `cercleArea`.

2. ```haskell
   cercleArea :: Float -> Float
   ```
   - Signature de type de `cercleArea`.
   - Prend un `Float` (`r`, le rayon) et retourne un `Float` (l'aire).

3. ```haskell
   cercleArea r = pi * r * r
   ```
   - Implémentation de `cercleArea`.
   - Utilise la constante `pi` (définie dans le préambule de Haskell) et la formule \( \pi \cdot r^2 \).
   - Exemple : `cercleArea 2.0` retourne environ `12.566371` (car \( \pi \cdot 2^2 \approx 12.566371 \)).

4. ```haskell
   -- Retourne la valeur maximale parmi trois entiers
   ```
   - Commentaire décrivant la fonction `maxOfThree`.

5. ```haskell
   maxOfThree :: Int -> Int -> Int -> Int
   ```
   - Signature de type de `maxOfThree`.
   - Prend trois `Int` (`x`, `y`, `z`) et retourne un `Int` (la valeur maximale).

6. ```haskell
   maxOfThree x y z = max (max x y) z
   ```
   - Implémentation de `maxOfThree`.
   - Utilise la fonction standard `max` de manière imbriquée : d'abord trouve le maximum de `x` et `y`, puis compare avec `z`.
   - Exemple : `maxOfThree 3 7 1` retourne `7` (car `max 3 7 = 7`, puis `max 7 1 = 7`).

7. ```haskell
   -- Fonction principale pour tester
   ```
   - Commentaire décrivant la fonction `main`.

8. ```haskell
   main :: IO ()
   ```
   - Signature de type de `main`, le point d’entrée du programme.

9. ```haskell
   main = do
   ```
   - Débute un bloc `do` pour séquencer les actions `IO`.

10-15. ```haskell
    print (cercleArea 2.0)    -- Rayon 2.0
    print (cercleArea 5.5)    -- Rayon 5.5
    print (cercleArea 0.0)    -- Rayon 0.0
    print (maxOfThree 3 7 1)  -- 3, 7, 1
    print (maxOfThree 10 10 5) -- 10, 10, 5
    print (maxOfThree 15 8 12) -- 15, 8, 12
    ```
    - Tests pour `cercleArea` avec des rayons 2.0, 5.5, et 0.0.
    - Tests pour `maxOfThree` avec les triplets (3, 7, 1), (10, 10, 5), et (15, 8, 12).
    - Chaque `print` affiche le résultat calculé.
