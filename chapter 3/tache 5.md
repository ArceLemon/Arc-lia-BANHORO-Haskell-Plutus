HC3T5 - Tâche 5 : Déterminer le type d’un triangle avec des gardes

```haskell
-- Classifie le type d'un triangle en fonction de ses côtés
triangleType :: Float -> Float -> Float -> String
triangleType a b c
  | a == b && b == c = "Équilatéral"
  | a == b || b == c || a == c = "Isocèle"
  | otherwise = "Scalène"

-- Fonction principale pour tester
main :: IO ()
main = do
    print (triangleType 3 3 3)
    print (triangleType 5 5 8)
    print (triangleType 6 7 8)
```

### Explications ligne par ligne :

1. `-- Classifie le type d'un triangle en fonction de ses côtés`  
   - Commentaire expliquant que `triangleType` détermine si un triangle est équilatéral, isocèle ou scalène en analysant les longueurs des côtés. Ignoré par le compilateur, il sert de documentation.

2. `triangleType :: Float -> Float -> Float -> String`  
   - Signature de type indiquant que la fonction prend trois arguments de type `Float` (longueurs des côtés) et retourne un `String`. Le type `Float` permet des décimales, et la fonction est pure avec vérification statique des types.

3. `triangleType a b c`  
   - Début de la définition avec les paramètres `a`, `b`, et `c` (longueurs des côtés). Ces noms sont immuables et représentent les trois côtés d’un triangle, préparant les gardes pour l’évaluation.

4. `  | a == b && b == c = "Équilatéral"`  
   - Première garde : vérifie si tous les côtés sont égaux (`a == b && b == c`) avec les opérateurs `==` (égalité) et `&&` (ET logique). Si vrai, retourne `"Équilatéral"` (triangle avec trois côtés égaux). Les gardes sont évaluées de haut en bas, et la première condition vraie est retenue.

5. `  | a == b || b == c || a == c = "Isocèle"`  
   - Deuxième garde : vérifie si au moins deux côtés sont égaux (`a == b || b == c || a == c`) avec `||` (OU logique). Si vrai, retourne `"Isocèle"` (triangle avec deux côtés égaux). Cette condition suit l’équilatéral pour éviter les chevauchements.

6. `  | otherwise = "Scalène"`  
   - Garde par défaut avec `otherwise` (équivalent à `True`), capturant tous les cas non couverts (aucun côté égal). Retourne `"Scalène"` (triangle avec trois côtés différents). Assure l’exhaustivité des cas.

7. (Ligne vide)  
   - Sépare visuellement les définitions, améliorant la lisibilité sans effet sur le code.

8. `-- Fonction principale pour tester`  
   - Commentaire indiquant que `main` teste `triangleType` avec des exemples.

9. `main :: IO ()`  
   - Signature de `main`, point d’entrée avec effet `IO` et retour vide (`()`), gérant l’affichage.

10. `main = do`  
    - Début d’un bloc `do` pour séquencer les actions `IO` (les `print`).

11. `    print (triangleType 3 3 3)`  
    - Affiche le résultat pour (3, 3, 3), où `a == b && b == c` est vrai, donnant `"Équilatéral"`.

12. `    print (triangleType 5 5 8)`  
    - Affiche le résultat pour (5, 5, 8), où `a == b` est vrai, donnant `"Isocèle"`.

13. `    print (triangleType 6 7 8)`  
    - Affiche le résultat pour (6, 7, 8), où aucun côté n’est égal, donnant `"Scalène"`.

