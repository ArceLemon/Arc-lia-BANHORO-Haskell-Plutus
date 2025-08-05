HC2T1 - Tâche 1 : Vérification des types dans GHCi

### Types attendus :
1. **42** :
   - Attendu : `Int`
   - Raison : En Haskell, un entier littéral comme `42` est typé comme `Int` par défaut, qui est un type d'entier sur 64 bits (ou 32 bits selon la plateforme) avec des limites définies.

2. **3.14** :
   - Attendu : `Double`
   - Raison : Une valeur avec une partie décimale comme `3.14` est typée comme `Double` en Haskell, qui est un type à virgule flottante de précision double.

3. **"Haskell"** :
   - Attendu : `[Char]` ou `String`
   - Raison : Une chaîne de caractères entre guillemets, comme `"Haskell"`, est typée comme une liste de caractères (`[Char]`), et Haskell définit `String` comme un synonyme de `[Char]`.

4. **"---------"** :
   - Attendu : `[Char]` ou `String`
   - Raison : Une chaîne de tirets, comme `"---------"`, est également une liste de caractères (`[Char]`), synonyme de `String`, car elle est entourée de guillemets.

5. **Vrai et faux** :
   - Attendu : Erreur ou non reconnu
   - Raison : Les termes `Vrai` et `faux` ne sont pas des mots-clés ou des valeurs valides en Haskell. En Haskell, les valeurs booléennes sont écrites `True` et `False` (avec une majuscule initiale). Cette expression pourrait provoquer une erreur de syntaxe ou ne pas être reconnue.

### Vérification dans GHCi :
Pour vérifier ces types, suivez ces étapes dans un terminal après avoir installé GHC :

1. **Ouvrir GHCi** :
   - Ouvrez un terminal et tapez :
     ```bash
     ghci
     ```
   - Vous devriez voir un invite comme `Prelude>`.

2. **Vérifier les types avec `:type` ou `:t`** :
   - Utilisation de la commande `:t` (ou `:type`) suivie de l'expression pour afficher son type.


     ```haskell
     :t 42
     :t 3.14
     :t "Haskell"
     :t "---------"
     :t Vrai
     :t faux
     ```

3. **Résultats attendus dans GHCi** :
   ```
ghci> :t 42
42 :: Int
ghci> :t 3.14
3.14 :: Double
ghci> :t "Haskell"
"Haskell" :: [Char]
ghci> :t "---------"
"---------" :: [Char]
ghci> :t Vrai
<interactive>:1:1: error: [GHC-88464]
    Data constructor not in scope: Vrai
```
### Explications supplémentaires :
- **Succès pour 42, 3.14, "Haskell", "---------"** :
  - Les types prédits correspondent aux conventions de Haskell. L'opérateur `::` dans GHCi indique le type d'une expression.
- **Échec pour Vrai et faux** :
  - Puisque `Vrai` et `faux` ne sont pas des valeurs valides (les booléens corrects sont `True` et `False`), GHCi signalera une erreur indiquant que ces identifiants ne sont pas définis. Si vous voulez vérifier les types des booléens corrects, essayez `:t True` et `:t False`, qui devraient retourner `True :: Bool` et `False :: Bool`.


### Conclusion :
Les types prédits sont corrects pour les expressions valides (`Int`, `Double`, `[Char]`), et l'erreur pour `Vrai` et `faux` est cohérente avec la syntaxe de Haskell.
