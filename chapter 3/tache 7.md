HC3T7 - Tâche avancée 7 : Déterminer la saison en fonction du mois avec des gardes

```haskell
-- Retourne la saison correspondant à un mois donné
season :: Int -> String
season month
  | month == 12 || month == 1 || month == 2 = "Hiver"
  | month == 3 || month == 4 || month == 5 = "Printemps"
  | month == 6 || month == 7 || month == 8 = "Été"
  | month == 9 || month == 10 || month == 11 = "Automne"

-- Fonction principale pour tester
main :: IO ()
main = do
    print (season 3)
    print (season 7)
    print (season 11)
```

### Explications ligne par ligne :

1. `-- Retourne la saison correspondant à un mois donné`  
   - Commentaire expliquant que `season` associe un mois (1-12) à une saison. Ignoré par le compilateur, il documente l'intention.

2. `season :: Int -> String`  
   - Signature de type indiquant que `season` prend un `Int` (mois) et retourne un `String` (saison). Pure et typée statiquement.

3. `season month`  
   - Début de la définition avec `month` comme paramètre (mois de 1 à 12), immuable, préparant les gardes.

4. `  | month == 12 || month == 1 || month == 2 = "Hiver"`  
   - Première garde : vérifie si `month` est 12, 1 ou 2 avec `==` (égalité) et `||` (OU logique), retournant "Hiver" si vrai.

5. `  | month == 3 || month == 4 || month == 5 = "Printemps"`  
   - Deuxième garde : vérifie si `month` est 3, 4 ou 5, retournant "Printemps" si vrai, après avoir exclu les mois d’hiver.

6. `  | month == 6 || month == 7 || month == 8 = "Été"`  
   - Troisième garde : vérifie si `month` est 6, 7 ou 8, retournant "Été" si vrai, après les saisons précédentes.

7. `  | month == 9 || month == 10 || month == 11 = "Automne"`  
   - Quatrième garde : vérifie si `month` est 9, 10 ou 11, retournant "Automne" si vrai, couvrant les mois restants.

8. (Ligne vide)  
   - Sépare visuellement les définitions pour la lisibilité.

9. `-- Fonction principale pour tester`  
   - Commentaire indiquant que `main` teste `season`.

10. `main :: IO ()`  
    - Signature de `main`, point d’entrée avec effet `IO` et retour vide (`()`).

11. `main = do`  
    - Début d’un bloc `do` pour séquencer les `print`.

12. `    print (season 3)`  
    - Teste mois 3, tombe dans "Printemps", affiche "Printemps".

13. `    print (season 7)`  
    - Teste mois 7, tombe dans "Été", affiche "Été".

14. `    print (season 11)`  
    - Teste mois 11, tombe dans "Automne", affiche "Automne".

