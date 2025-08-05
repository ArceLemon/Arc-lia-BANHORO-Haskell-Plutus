HC2T6 - Tâche 6 : Comprendre Int vs Luge

En Haskell, les types `Int` et `Integer` diffèrent :
- `Int` est un entier signé de taille fixe (généralement 64 bits sur la plupart des systèmes modernes, avec une plage typique de \(-2^{63}\) à \(2^{63} - 1\)).
- `Integer` est un entier de précision arbitraire, qui peut représenter des nombres très grands sans limite de taille (au prix d'une consommation de mémoire accrue).

Je vais définir ces variables et tester l'expression demandée.

### Code
```haskell
-- Définition d'une variable de type Int avec 2^62
variableNombre :: Int
variableNombre = 2^62

-- Définition d'une variable de type Integer avec 2^127
bigNumber :: Integer
bigNumber = 2^127

-- Fonction principale pour tester
main :: IO ()
main = do
    print variableNombre
    print bigNumber
```

### Explications ligne par ligne :
1. ```haskell
   -- Définition d'une variable de type Int avec 2^62
   ```
   - Commentaire décrivant `variableNombre`.

2. ```haskell
   variableNombre :: Int
   ```
   - Signature de type, indique que `variableNombre` est de type `Int`.

3. ```haskell
   variableNombre = 2^62
   ```
   - Définit `variableNombre` comme \( 2^{62} \).
   - Sur un système 64 bits, \( 2^{62} \) (4 611 686 018 427 387 904) est dans la plage de `Int` (\(-2^{63}\) à \(2^{63} - 1\)), donc cela fonctionne.

4. ```haskell
   -- Définition d'une variable de type Integer avec 2^127
   ```
   - Commentaire décrivant `bigNumber`.

5. ```haskell
   bigNumber :: Integer
   ```
   - Signature de type, indique que `bigNumber` est de type `Integer`.

6. ```haskell
   bigNumber = 2^127
   ```
   - Définit `bigNumber` comme \( 2^{127} \) (170 141 183 460 469 231 731 687 303 715 884 105 728).
   - `Integer` peut gérer cette valeur massive sans problème grâce à sa précision arbitraire.

7. ```haskell
   -- Fonction principale pour tester
   ```
   - Commentaire décrivant `main`.

8. ```haskell
   main :: IO ()
   ```
   - Signature de type de `main`.

9-10. ```haskell
   main = do
   print variableNombre
   print bigNumber
   ```
   - Affiche les valeurs de `variableNombre` et `bigNumber`.

### Résultat de l’exécution :
Lors de l’exécution :
```
4611686018427387904
170141183460469231731687303715884105728
```

### Évaluation de `2^64 :: Int` dans GHCi
Maintenant, examinons l'expression `2^64 :: Int` comme demandé :

1. **Ouvrir GHCi** :
   - Dans un terminal, tapez :
     ```bash
     ghci
     ```

2. **Évaluer l'expression** :
   - Entrez :
     ```haskell
     2^64 :: Int
     ```
   - Résultat attendu : Une erreur, car \( 2^{64} \) (18 446 744 073 709 551 616) dépasse la plage maximale d'un `Int` sur un système 64 bits, qui est \( 2^{63} - 1 \) (9 223 372 036 854 775 807).

3. **Sortie dans GHCi** :
   - Vous obtiendrez une erreur comme :
     ```
     <interactive>:1:1: error:
         • Integer literal 18446744073709551616 out of range for Int
         • In the expression: 2 ^ 64 :: Int
   ```
   - Cela confirme que `Int` ne peut pas représenter \( 2^{64} \) en raison de sa limite supérieure.

### Explication :
- **Plage de `Int`** : Sur un système 64 bits, un `Int` est signé et va de \(-2^{63}\) (\(-9 223 372 036 854 775 808\)) à \(2^{63} - 1\) (\(9 223 372 036 854 775 807\)). \( 2^{64} \) est supérieur à cette limite, donc GHCi rejette l'expression.
- **Utilisation de `Integer`** : Si vous essayez `2^64 :: Integer`, cela fonctionnera, car `Integer` n'a pas de limite supérieure :
  ```haskell
  Prelude> 2^64 :: Integer
  18446744073709551616
  ```
