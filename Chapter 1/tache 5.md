HC1T5 - Tâche 5 : Paresse en Haskell

### Code
```haskell
-- Génère une liste infinie de nombres entiers à partir de 1
infiniteNumbers :: [Int]
infiniteNumbers = [1..]

-- Extrait les n premiers éléments de la liste infinie
takeFirstN :: Int -> [Int]
takeFirstN n = take n infiniteNumbers

-- Fonction principale pour tester
main :: IO ()
main = do
    print (takeFirstN 5)
    print (takeFirstN 10)
```

### Explication ligne par ligne

1. ```haskell
   -- Génère une liste infinie de nombres entiers à partir de 1
   ```
   - Commentaire décrivant la fonction `infiniteNumbers`, qui crée une liste infinie de nombres.

2. ```haskell
   infiniteNumbers :: [Int]
   ```
   - Signature de type de `infiniteNumbers`.
   - `[Int]` indique que la fonction retourne une liste d’entiers.

3. ```haskell
   infiniteNumbers = [1..]
   ```
   - Définit `infiniteNumbers` comme une liste infinie commençant à 1.
   - La syntaxe `[1..]` est un raccourci Haskell pour générer une liste infinie `[1, 2, 3, ...]`.
   - Grâce à l’évaluation paresseuse, Haskell ne calcule que les éléments nécessaires lorsqu’ils sont utilisés.

4. ```haskell
   -- Extrait les n premiers éléments de la liste infinie
   ```
   - Commentaire décrivant la fonction `takeFirstN`, qui extrait les `n` premiers éléments.

5. ```haskell
   takeFirstN :: Int -> [Int]
   ```
   - Signature de type de `takeFirstN`.
   - Prend un entier `Int` (le nombre d’éléments à extraire) et retourne une liste d’entiers `[Int]`.

6. ```haskell
   takeFirstN n = take n infiniteNumbers
   ```
   - Définit `takeFirstN` en utilisant la fonction standard `take`, qui extrait les `n` premiers éléments d’une liste.
   - Applique `take n` à `infiniteNumbers` pour obtenir les `n` premiers nombres.
   - Exemple : `takeFirstN 5` retourne `[1, 2, 3, 4, 5]`.

7. ```haskell
   -- Fonction principale pour tester
   ```
   - Commentaire décrivant la fonction `main`, qui teste `takeFirstN`.

8. ```haskell
   main :: IO ()
   ```
   - Signature de type de `main`, le point d’entrée du programme, avec le type `IO ()` pour les actions d’entrée/sortie.

9. ```haskell
   main = do
   ```
   - Débute un bloc `do` pour séquencer plusieurs actions `IO`.

10. ```haskell
    print (takeFirstN 5)
    ```
    - Appelle `takeFirstN 5` pour extraire les 5 premiers éléments de `infiniteNumbers` (soit `[1, 2, 3, 4, 5]`) et affiche le résultat avec `print`.

11. ```haskell
    print (takeFirstN 10)
    ```
    - Appelle `takeFirstN 10` pour extraire les 10 premiers éléments (soit `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`) et affiche le résultat.



### Notes
- **Pureté** : `infiniteNumbers` et `takeFirstN` sont des fonctions pures. `infiniteNumbers` définit une liste infinie, mais grâce à l’évaluation paresseuse, seuls les éléments demandés par `take` sont calculés.
- **Évaluation paresseuse** : Haskell ne génère pas l’intégralité de la liste infinie, ce qui rend l’utilisation de `infiniteNumbers` sûre et efficace.
- **Flexibilité** : Vous pouvez modifier `takeFirstN` pour extraire un nombre différent d’éléments en changeant l’argument `n`.
- **Alternative** : Si vous voulez une liste infinie commençant à un autre nombre ou avec un pas différent, vous pouvez redéfinir `infiniteNumbers`, par exemple :
  - `[0..]` pour commencer à 0.
  - `[2,4..]` pour les nombres pairs.



