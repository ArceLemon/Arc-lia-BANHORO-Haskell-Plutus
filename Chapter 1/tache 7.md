HC1T7 - Tâche 7 : Conversion Fahrenheit/Celsius

```haskell
-- Convertit des degrés Fahrenheit en Celsius
fToC :: Double -> Double
fToC f = (f - 32) * 5 / 9

-- Fonction principale pour tester
main :: IO ()
main = print (fToC 68)
```


### Explication ligne par ligne :

1. ```haskell
   -- Convertit des degrés Fahrenheit en Celsius
   ```
   - Commentaire décrivant la fonction `fToC`, qui effectue la conversion de Fahrenheit en Celsius.

2. ```haskell
   fToC :: Double -> Double
   ```
   - Signature de type de `fToC`.
   - `Double -> Double` indique que la fonction prend un nombre à virgule flottante (`Double`) pour la température en Fahrenheit et retourne un `Double` pour la température en Celsius.
   - `Double` est utilisé pour permettre des calculs précis avec des valeurs décimales.

3. ```haskell
   fToC f = (f - 32) * 5 / 9
   ```
   - Définit la fonction `fToC` qui prend un paramètre `f` (température en Fahrenheit).
   - La formule de conversion est `(f - 32) * 5 / 9` :
     - Soustrait 32 à la température Fahrenheit.
     - Multiplie le résultat par 5.
     - Divise par 9 pour obtenir la température en Celsius.
   - Exemple : `fToC 68` calcule `(68 - 32) * 5 / 9 = 36 * 5 / 9 ≈ 20.0`.

4. ```haskell
   -- Fonction principale pour tester
   ```
   - Commentaire décrivant la fonction `main`, utilisée pour tester `fToC`.

5. ```haskell
   main :: IO ()
   ```
   - Signature de type de `main`, le point d’entrée du programme, avec le type `IO ()` pour les actions d’entrée/sortie.

6. ```haskell
   main = print (fToC 68)
   ```
   - Appelle `fToC 68` (qui retourne `20.0`) et affiche le résultat avec `print`.
   - `print` convertit la valeur en chaîne et l’affiche dans la console.





