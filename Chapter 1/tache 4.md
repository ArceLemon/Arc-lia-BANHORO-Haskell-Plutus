HC1T4 - Tâche 4 : Composer une fonction pour traiter des données de joueurs



```haskell
import Data.List (sortBy)
import Data.Ord (comparing)

-- Extrait les noms des joueurs d'une liste de tuples (nom, score)
extractPlayers :: [(String, Int)] -> [String]
extractPlayers players = map fst players

-- Trie la liste des joueurs par score décroissant
sortByScore :: [(String, Int)] -> [(String, Int)]
sortByScore players = sortBy (\(_, s1) (_, s2) -> compare s2 s1) players

-- Retourne les trois meilleurs joueurs
topThree :: [(String, Int)] -> [(String, Int)]
topThree players = take 3 players

-- Compose les fonctions pour obtenir les noms des trois meilleurs joueurs
getTopThreePlayers :: [(String, Int)] -> [String]
getTopThreePlayers = extractPlayers . topThree . sortByScore

-- Fonction principale pour tester les trois fonctions séparément
main :: IO ()
main = do
    print (extractPlayers [("Alice", 100), ("Bob", 50), ("Charlie", 75), ("David", 90)])
    print (sortByScore [("Alice", 100), ("Bob", 50), ("Charlie", 75), ("David", 90)])
    print (topThree (sortByScore [("Alice", 100), ("Bob", 50), ("Charlie", 75), ("David", 90)]))
```




### Explication ligne par ligne :

1. ```haskell
   import Data.List (sortBy)
   ```
   - Cette ligne importe la fonction `sortBy` du module `Data.List`.
   - `sortBy` est utilisée dans `sortByScore` pour trier une liste selon une fonction de comparaison personnalisée.
   - L'importation explicite `(sortBy)` limite l'importation à cette seule fonction pour éviter des conflits potentiels.

2. ```haskell
   import Data.Ord (comparing)
   ```
   - Importe la fonction `comparing` du module `Data.Ord`.
   - Bien que `comparing` ne soit plus utilisé dans cette version corrigée de `sortByScore`, il était présent dans la version précédente et pourrait être utile pour d'autres implémentations. Il est conservé ici pour compatibilité, mais pourrait être supprimé sans affecter ce code.

3. ```haskell
   -- Extrait les noms des joueurs d'une liste de tuples (nom, score)
   ```
   - Un commentaire décrivant la fonction `extractPlayers`, qui va extraire les noms (premiers éléments des tuples) d’une liste de tuples `(nom, score)`.

4. ```haskell
   extractPlayers :: [(String, Int)] -> [String]
   ```
   - Déclare la **signature de type** de la fonction `extractPlayers`.
   - `[(String, Int)]` indique une liste de tuples où chaque tuple contient une chaîne (`String`) pour le nom et un entier (`Int`) pour le score.
   - `[String]` indique que la fonction retourne une liste de chaînes (les noms des joueurs).

5. ```haskell
   extractPlayers players = map fst players
   ```
   - Définit la fonction `extractPlayers`.
   - `players` est le paramètre représentant la liste de tuples.
   - `map fst players` applique la fonction `fst` (qui extrait le premier élément d’un tuple) à chaque tuple de la liste `players`.
   - Exemple : pour `[("Alice", 100), ("Bob", 50)]`, `map fst` retourne `["Alice", "Bob"]`.

6. ```haskell
   -- Trie la liste des joueurs par score décroissant
   ```
   - Commentaire décrivant la fonction `sortByScore`, qui trie la liste de tuples par score en ordre décroissant.

7. ```haskell
   sortByScore :: [(String, Int)] -> [(String, Int)]
   ```
   - Signature de type de `sortByScore`.
   - Prend une liste de tuples `(String, Int)` et retourne une liste de tuples du même type, triée par score.

8. ```haskell
   sortByScore players = sortBy (\(_, s1) (_, s2) -> compare s2 s1) players
   ```
   - Définit `sortByScore` en utilisant `sortBy` pour trier la liste `players`.
   - `sortBy` prend une fonction de comparaison `\(_, s1) (_, s2) -> compare s2 s1` :
     - `(_, s1)` et `(_, s2)` déstructurent les tuples pour extraire les scores (`s1` et `s2`), ignorant les noms (`_`).
     - `compare s2 s1` compare les scores en ordre décroissant (en inversant `s1` et `s2` pour obtenir les plus grands scores en premier).
   - Exemple : pour `[("Alice", 100), ("Bob", 50), ("Charlie", 75), ("David", 90)]`, retourne `[("Alice", 100), ("David", 90), ("Charlie", 75), ("Bob", 50)]`.

9. ```haskell
   -- Retourne les trois meilleurs joueurs
   ```
   - Commentaire décrivant la fonction `topThree`, qui extrait les trois premiers éléments d’une liste.

10. ```haskell
    topThree :: [(String, Int)] -> [(String, Int)]
    ```
    - Signature de type de `topThree`.
    - Prend une liste de tuples et retourne une liste de tuples (jusqu’à trois éléments).

11. ```haskell
    topThree players = take 3 players
    ```
    - Définit `topThree` en utilisant `take 3` pour extraire les trois premiers éléments de `players`.
    - Si la liste a moins de trois éléments, elle retourne la liste entière.
    - Exemple : pour `[("Alice", 100), ("David", 90), ("Charlie", 75), ("Bob", 50)]`, retourne `[("Alice", 100), ("David", 90), ("Charlie", 75)]`.

12. ```haskell
    -- Compose les fonctions pour obtenir les noms des trois meilleurs joueurs
    ```
    - Commentaire décrivant `getTopThreePlayers`, qui combine les fonctions précédentes.

13. ```haskell
    getTopThreePlayers :: [(String, Int)] -> [String]
    ```
    - Signature de type de `getTopThreePlayers`.
    - Prend une liste de tuples et retourne une liste de chaînes (les noms des trois meilleurs joueurs).

14. ```haskell
    getTopThreePlayers = extractPlayers . topThree . sortByScore
    ```
    - Définit `getTopThreePlayers` en composant les trois fonctions avec l’opérateur `.`.
    - L’opérateur `.` applique les fonctions de droite à gauche : d’abord `sortByScore`, puis `topThree`, puis `extractPlayers`.
    - Exemple : pour `[("Alice", 100), ("Bob", 50), ("Charlie", 75), ("David", 90)]`, retourne `["Alice", "David", "Charlie"]`.

15. ```haskell
    -- Fonction principale pour tester les trois fonctions séparément
    ```
    - Commentaire décrivant `main`, qui teste `extractPlayers`, `sortByScore`, et `topThree`.

16. ```haskell
    main :: IO ()
    ```
    - Signature de type de `main`, le point d’entrée du programme, qui effectue des actions d’entrée/sortie (`IO ()`).

17. ```haskell
    main = do
    ```
    - Débute un bloc `do` pour séquencer plusieurs actions `IO` (ici, trois appels à `print`).

18. ```haskell
    print (extractPlayers [("Alice", 100), ("Bob", 50), ("Charlie", 75), ("David", 90)])
    ```
    - Applique `extractPlayers` à la liste de test et affiche le résultat avec `print`.
    - Résultat : `["Alice", "Bob", "Charlie", "David"]`.

19. ```haskell
    print (sortByScore [("Alice", 100), ("Bob", 50), ("Charlie", 75), ("David", 90)])
    ```
    - Applique `sortByScore` à la liste de test et affiche le résultat.
    - Résultat : `[("Alice", 100), ("David", 90), ("Charlie", 75), ("Bob", 50)]`.

20. ```haskell
    print (topThree (sortByScore [("Alice", 100), ("Bob", 50), ("Charlie", 75), ("David", 90)]))
    ```
    - Applique `sortByScore` à la liste de test, puis `topThree` au résultat, et affiche avec `print`.
    - Résultat : `[("Alice", 100), ("David", 90), ("Charlie", 75)]`.

### Résultat de l’exécution :
Lors de l’exécution, le programme affiche :
```
["Alice","Bob","Charlie","David"]
[("Alice",100),("David",90),("Charlie",75),("Bob",50)]
[("Alice",100),("David",90),("Charlie",75)]
```

