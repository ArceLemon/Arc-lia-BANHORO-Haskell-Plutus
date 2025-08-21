HC3T9 - Tâche avancée 9 : Trouver le maximum de trois nombres avec let

```haskell
-- Retourne le maximum de trois nombres entiers
maxOfThree :: Int -> Int -> Int -> Int
maxOfThree a b c = let max1 = max a b
                       max2 = max max1 c
                   in max2

-- Fonction principale pour tester
main :: IO ()
main = do
    print (maxOfThree 10 20 15)
    print (maxOfThree 5 25 10)
```

### Explications ligne par ligne :

1. `-- Retourne le maximum de trois nombres entiers`  
   - Commentaire expliquant que `maxOfThree` trouve le plus grand parmi trois `Int`. Ignoré par le compilateur, il documente l'intention.

2. `maxOfThree :: Int -> Int -> Int -> Int`  
   - Signature de type indiquant que la fonction prend trois `Int` (a, b, c) et retourne un `Int` (le maximum). Elle est pure et typée statiquement.

3. `maxOfThree a b c =`  
   - Début de la définition avec `a`, `b`, et `c` comme paramètres immuables, préparant l'utilisation de `let` pour les calculs intermédiaires.

4. `    let max1 = max a b`  
   - Utilise `let` pour définir `max1` comme le maximum de `a` et `b` avec la fonction standard `max` (de `Prelude`). Cela stocke une valeur intermédiaire pour éviter de recalculer.

5. `        max2 = max max1 c`  
   - Définit `max2` comme le maximum de `max1` (le plus grand entre `a` et `b`) et `c`, continuant la logique pour inclure le troisième nombre.

6. `    in max2`  
   - `in` conclut la clause `let` et retourne `max2`, qui est le maximum global des trois nombres. Cette expression est pure, dépendant uniquement des entrées.

7. (Ligne vide)  
   - Sépare visuellement les définitions pour une meilleure lisibilité.

8. `-- Fonction principale pour tester`  
   - Commentaire indiquant que `main` teste `maxOfThree`.

9. `main :: IO ()`  
   - Signature de `main`, point d’entrée avec effet `IO` et retour vide (`()`), gérant l’affichage.

10. `main = do`  
    - Début d’un bloc `do` pour séquencer les `print`.

11. `    print (maxOfThree 10 20 15)`  
    - Teste avec 10, 20, 15 : `max 10 20 = 20`, puis `max 20 15 = 20`, affiche `20`.

12. `    print (maxOfThree 5 25 10)`  
    - Teste avec 5, 25, 10 : `max 5 25 = 25`, puis `max 25 10 = 25`, affiche `25`.

