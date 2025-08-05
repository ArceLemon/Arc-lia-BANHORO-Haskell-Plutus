HC2T3 - Tâche 3 : Variables d'économie

En Haskell, les variables sont **immuables** par conception, ce qui signifie qu'une fois qu'une valeur est associée à un nom (via une définition avec `let` ou dans une fonction), elle ne peut pas être modifiée. Cela fait partie du paradigme fonctionnel de Haskell, où l'accent est mis sur l'absence d'effets secondaires et la pureté.

### Définition des variables immuables
En Haskell, les "variables" sont en réalité des **noms liés à des valeurs** (souvent appelés bindings). Voici comment définir les variables demandées :

```haskell
-- Définition des valeurs immuables
myAge :: Int
myAge = 25

piValue :: Double
piValue = 3.14159

salutation :: String
salutation = "Hello, Haskell!"

isHaskellFun :: Bool
isHaskellFun = True

-- Fonction principale pour tester
main :: IO ()
main = do
    print myAge
    print piValue
    print salutation
    print isHaskellFun
```

### Explication des définitions :
1. **myAge :: Int**
   - Déclare `myAge` comme une valeur de type `Int` avec la valeur `25`.
   - Une fois définie, cette valeur ne peut pas être changée.

2. **piValue :: Double**
   - Déclare `piValue` comme une valeur de type `Double` avec la valeur `3.14159`.
   - Immuable après définition.

3. **salutation :: String**
   - Déclare `salutation` comme une valeur de type `String` (synonyme de `[Char]`) avec la valeur `"Hello, Haskell!"`.
   - Immuable.

4. **isHaskellFun :: Bool**
   - Déclare `isHaskellFun` comme une valeur de type `Bool` avec la valeur `True`.
   - Immuable.

5. **main :: IO ()**
   - Définit une fonction principale pour afficher les valeurs avec `print`.

### Tentative de modification
En Haskell, il n'est pas possible de réassigner une valeur à un nom déjà défini dans le même scope. Essayons de modifier une variable (par exemple, `myAge`) et observons le résultat :

#### Tentative 1 : Réassignation directe
Ajoutons une tentative de modification dans le code :
```haskell
myAge = 30  -- Erreur : Redéfinition de myAge
```
- Si vous essayez cela dans le même fichier ou scope, GHC signalera une erreur comme :
  ```
  Multiple declarations of ‘myAge’
  ```
- En Haskell, une fois qu'un nom est lié à une valeur (via `=`), vous ne pouvez pas le réaffecter. Cela viole les règles d'immutabilité.

#### Tentative 2 : Utilisation de `let` dans un bloc `do`
Modifions le code pour tenter une réassignation dans `main` avec `let` :
```haskell
main :: IO ()
main = do
    print myAge
    let myAge = 30  -- Erreur : myAge est déjà défini
    print myAge
```
- Résultat : Cela provoquera une erreur de compilation :
  ```
  Not in scope: ‘myAge’
  ```
  ou
  ```
  Multiple declarations of ‘myAge’
  ```
- La raison est que `let` dans un bloc `do` ne peut pas réassigner une variable globale ; il crée une nouvelle liaison locale, mais ici, cela entre en conflit avec la définition globale.

#### Tentative 3 : Utilisation d'une référence mutable (impossible sans monade)
Haskell permet des références mutables avec des monades comme `IO` ou `ST`, mais cela nécessite une approche différente (par exemple, avec `IORef`). Cependant, pour des débutants, cela dépasse le cadre d'une variable immuable simple. Essayons une version incorrecte pour illustrer :
```haskell
import Data.IORef

main :: IO ()
main = do
    myAgeRef <- newIORef 25
    print =<< readIORef myAgeRef
    writeIORef myAgeRef 30  -- Modification via IORef
    print =<< readIORef myAgeRef
```
- Cela fonctionnerait (affichant `25` puis `30`), mais cela utilise une référence mutable (`IORef`), ce qui est une exception aux variables immuables et nécessite une compréhension des monades.

### Résultat observé
- **Sans monade** : Toute tentative de réassignation directe (comme `myAge = 30`) échoue avec une erreur de compilation.
- **Avec monade** : La modification est possible uniquement avec des structures comme `IORef`, mais cela sort du paradigme des variables immuables simples et nécessite une gestion explicite dans `IO`.

### Conclusion
- En Haskell, les variables comme `myAge`, `piValue`, `salutation`, et `isHaskellFun` sont **immuables** par défaut. Vous ne pouvez pas les modifier après leur définition dans le même scope.
