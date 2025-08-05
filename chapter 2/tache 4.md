HC2T4 - Tâche 4 : Notation préfixe et infixe

- **Notation préfixe** : En Haskell, la notation préfixe implique d'utiliser une fonction ou un opérateur comme le premier élément, suivi de ses arguments entre parenthèses. Par exemple, `(+ 5 3)` au lieu de `5 + 3`.
- **Notation infixe** : La notation infixe place l'opérateur entre les deux opérandes, comme dans `7 + 2` ou `True && False`.

### Solutions

#### Notation préfixe pour les expressions données :
1. **5 et 3** :
   - Interprétation : Addition de 5 et 3.
   - Notation préfixe : `(+) 5 3`
   - Explication : L'opérateur `+` est placé en premier, suivi des opérandes `5` et `3` entre parenthèses.

2. **10 et 4** :
   - Interprétation : Addition de 10 et 4.
   - Notation préfixe : `(+) 10 4`
   - Explication : Similaire à l'exemple précédent, `(+) 10 4` représente `10 + 4`.

3. **Vrai et faux** :
   - Interprétation : Conjonction logique de `True` et `False` (en corrigeant "Vrai" et "faux" en `True` et `False`, qui sont les valeurs booléennes en Haskell).
   - Notation préfixe : `(&&) True False`
   - Explication : L'opérateur logique `&&` (ET) est placé en premier, suivi des valeurs booléennes `True` et `False`.

#### Notation infixe pour les fonctions données :
Les expressions "7 2", "6 5", et "Vrai faux" semblent être des appels de fonctions sans opérateur explicite. En Haskell, pour convertir cela en notation infixe, nous devons supposer un opérateur ou une fonction binaire. Puisque aucun opérateur n'est spécifié, je vais supposer une opération courante comme l'addition pour les nombres et la conjonction pour les booléens, en les plaçant entre les opérandes.

1. **7 2** :
   - Interprétation : Addition de 7 et 2.
   - Notation infixe : `7 + 2`
   - Explication : L'opérateur `+` est placé entre `7` et `2`.

2. **6 5** :
   - Interprétation : Addition de 6 et 5.
   - Notation infixe : `6 + 5`
   - Explication : L'opérateur `+` est placé entre `6` et `5`.

3. **Vrai faux** :
   - Interprétation : Conjonction logique de `True` et `False` (en corrigeant "Vrai" et "faux" en `True` et `False`).
   - Notation infixe : `True && False`
   - Explication : L'opérateur `&&` est placé entre `True` et `False`.



### Code d'exemple pour tester

```haskell
-- Fonction principale pour tester
main :: IO ()
main = do
    print ((+) 5 3)          -- Notation préfixe : 8
    print ((+) 10 4)         -- Notation préfixe : 14
    print ((&&) True False)  -- Notation préfixe : False
    print (7 + 2)            -- Notation infixe : 9
    print (6 + 5)            -- Notation infixe : 11
    print (True && False)    -- Notation infixe : False
```

### Résultat attendu :
```
8
14
False
9
11
False
```
