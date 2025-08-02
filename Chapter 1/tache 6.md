HC1T6 - Tâche 6 : Utilisation de signatures de type

Voici une fonction Haskell pure pour additionner deux entiers :

```haskell
-- Additionne deux entiers
addNumbers :: Int -> Int -> Int
addNumbers x y = x + y

-- Fonction principale pour tester
main :: IO ()
main = print (addNumbers 3 5)
```


### Explication ligne par ligne :

1. ```haskell
   -- Additionne deux entiers
   ```
   - Commentaire décrivant la fonction `addNumbers`, qui additionne deux entiers.

2. ```haskell
   addNumbers :: Int -> Int -> Int
   ```
   - Signature de type de `addNumbers`.
   - `Int -> Int -> Int` indique que la fonction prend deux entiers (`Int`) comme arguments et retourne un entier (`Int`).

3. ```haskell
   addNumbers x y = x + y
   ```
   - Définit la fonction `addNumbers` qui prend deux paramètres, `x` et `y`.
   - L’expression `x + y` calcule la somme des deux entiers.
   - Exemple : `addNumbers 3 5` retourne `8`.

4. ```haskell
   -- Fonction principale pour tester
   ```
   - Commentaire décrivant la fonction `main`, utilisée pour tester `addNumbers`.

5. ```haskell
   main :: IO ()
   ```
   - Signature de type de `main`, le point d’entrée du programme, avec le type `IO ()` pour les actions d’entrée/sortie.

6. ```haskell
   main = print (addNumbers 3 5)
   ```
   - Appelle `addNumbers 3 5` (qui retourne `8`) et affiche le résultat avec `print`.
   - `print` convertit la valeur en chaîne et l’affiche dans la console.



### Notes :
- **Pureté** : `addNumbers` est une fonction pure, car elle dépend uniquement de ses arguments `x` et `y` et produit toujours le même résultat pour les mêmes entrées, sans effets secondaires.
- **Test** : Vous pouvez tester d’autres valeurs en modifiant les arguments dans `main`, par exemple `print (addNumbers 10 20)` pour obtenir `30`.
- **GHCi** : Pour tester dans GHCi :
  ```haskell
  :l AddNumbers.hs
  main
  ```
  Ou directement : `addNumbers 3 5` pour obtenir `8`.

Si vous avez besoin d’une modification (par exemple, utiliser `Double` au lieu de `Int` ou ajouter plus de tests), faites-le-moi savoir !
