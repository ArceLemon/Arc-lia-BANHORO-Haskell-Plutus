HC2T7 - Tâche 7 : Expressions booléennes

### Expressions booléennes quintaires

1. **"Vrai en contact &&"** (interprété comme une expression avec cinq termes utilisant `&&` et retournant `True`) :
   - Expression : `True && True && True && True && True`
   - Explication : Utilise l'opérateur `&&` (ET) pour combiner cinq valeurs `True`. Puisque tous les termes sont `True`, le résultat est `True`.

2. **"Faux en utilisant ||"** (interprété comme une expression avec cinq termes utilisant `||` et retournant `False`) :
   - Expression : `False || False || False || False || False`
   - Explication : Utilise l'opérateur `||` (OU) pour combiner cinq valeurs `False`. Puisque tous les termes sont `False`, le résultat est `False`.

3. **"Vrai en contact not"** (interprété comme une expression avec cinq termes utilisant `not` et retournant `True`) :
   - Expression : `not False && not False && not False && not False && not False`
   - Explication : Utilise `not` pour inverser cinq valeurs `False`, donnant cinq `True`, puis les combine avec `&&`. Le résultat est `True` car tous les termes sont `True` après négation.

4. **"Une comparaison qui retourne Faux"** (interprété comme une expression avec cinq comparaisons ou termes logiques retournant `False`) :
   - Expression : `1 < 2 && 3 > 4 && 5 == 6 && 7 /= 8 && 9 < 10`
   - Explication : Combine cinq comparaisons :
     - `1 < 2` est `True` (1 est inférieur à 2).
     - `3 > 4` est `False` (3 n'est pas supérieur à 4).
     - `5 == 6` est `False` (5 n'est pas égal à 6).
     - `7 /= 8` est `True` (7 est différent de 8).
     - `9 < 10` est `True` (9 est inférieur à 10).
     - Avec `&&`, le résultat est `False` car au moins une comparaison est `False`.

### Code pour tester
Voici un programme Haskell pour évaluer ces expressions :

```haskell
-- Fonction principale pour tester les expressions booléennes
main :: IO ()
main = do
    print (True && True && True && True && True)          -- Expression 1
    print (False || False || False || False || False)     -- Expression 2
    print (not False && not False && not False && not False && not False)  -- Expression 3
    print (1 < 2 && 3 > 4 && 5 == 6 && 7 /= 8 && 9 < 10) -- Expression 4
```

### Explications ligne par ligne :
1-4. ```haskell
    print (True && True && True && True && True)          -- Expression 1
    print (False || False || False || False || False)     -- Expression 2
    print (not False && not False && not False && not False && not False)  -- Expression 3
    print (1 < 2 && 3 > 4 && 5 == 6 && 7 /= 8 && 9 < 10) -- Expression 4
    ```
   - Chaque `print` évalue et affiche le résultat de l'expression correspondante.

### Résultat de l’exécution :
Lors de l’exécution, le programme affiche :
```
True
False
True
False
```

### Notes :
- **Correction** : J'ai remplacé "Vrai" et "Faux" par `True` et `False`, qui sont les syntaxes correctes en Haskell. J'ai aussi interprété "en contact" comme une conjonction implicite.
- **Quintaires** : Chaque expression utilise cinq termes (cinq booléens ou comparaisons) comme demandé.
- **Test dans GHCi** : Vous pouvez vérifier individuellement :
  ```haskell
  Prelude> True && True && True && True && True
  True
  Prelude> False || False || False || False || False
  False
  Prelude> not False && not False && not False && not False && not False
  True
  Prelude> 1 < 2 && 3 > 4 && 5 == 6 && 7 /= 8 && 9 < 10
  False
  ```
