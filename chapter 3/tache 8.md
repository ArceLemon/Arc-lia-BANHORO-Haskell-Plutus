HC3T8 - Tâche avancée 8 : Calculer l’IMC et retourner la catégorie avec where

```haskell
-- Détermine la catégorie d'IMC à partir du poids et de la taille
bmiCategory :: Float -> Float -> String
bmiCategory weight height
  | bmi < 18.5 = "Insuffisance pondérale"
  | bmi >= 18.5 && bmi < 24.9 = "Normal"
  | bmi >= 25 && bmi < 29.9 = "Surpoids"
  | bmi >= 30 = "Obésité"
  where bmi = weight / height^2

-- Fonction principale pour tester
main :: IO ()
main = do
    print (bmiCategory 70 1.75)
    print (bmiCategory 90 1.8)
```

### Explications ligne par ligne :

1. `-- Détermine la catégorie d'IMC à partir du poids et de la taille`  
   - Commentaire indiquant que `bmiCategory` classe l'IMC (indice de masse corporelle) en fonction du poids (kg) et de la taille (m). Ignoré par le compilateur, il documente l'objectif.

2. `bmiCategory :: Float -> Float -> String`  
   - Signature de type spécifiant que la fonction prend deux `Float` (poids et taille) et retourne un `String` (catégorie IMC). Elle est pure et bénéficie de la vérification statique des types.

3. `bmiCategory weight height`  
   - Début de la définition avec `weight` (poids) et `height` (taille) comme paramètres immuables, préparant les gardes et la clause `where` pour le calcul.

4. `  | bmi < 18.5 = "Insuffisance pondérale"`  
   - Première garde : vérifie si `bmi` est inférieur à 18.5, retournant "Insuffisance pondérale" si vrai. Les gardes sont évaluées séquentiellement.

5. `  | bmi >= 18.5 && bmi < 24.9 = "Normal"`  
   - Deuxième garde : vérifie si `bmi` est entre 18.5 et 24.9 (inclusif/exclusif) avec `&&` (ET logique), retournant "Normal" si vrai.

6. `  | bmi >= 25 && bmi < 29.9 = "Surpoids"`  
   - Troisième garde : vérifie si `bmi` est entre 25 et 29.9, retournant "Surpoids" si vrai, après exclusion des catégories précédentes.

7. `  | bmi >= 30 = "Obésité"`  
   - Quatrième garde : vérifie si `bmi` est supérieur ou égal à 30, retournant "Obésité" si vrai, couvrant les cas restants.

8. `  where bmi = weight / height^2`  
   - Clause `where` définissant `bmi` comme le quotient du poids divisé par le carré de la taille (`height^2` avec `^` pour l'exponentiation). Calculé une fois pour toutes les gardes, assurant efficacité.

9. (Ligne vide)  
   - Sépare visuellement les définitions pour une meilleure lisibilité.

10. `-- Fonction principale pour tester`  
    - Commentaire indiquant que `main` teste `bmiCategory` avec des exemples.

11. `main :: IO ()`  
    - Signature de `main`, point d’entrée avec effet `IO` et retour vide (`()`), gérant l’affichage.

12. `main = do`  
    - Début d’un bloc `do` pour séquencer les actions `IO` (les `print`).

13. `    print (bmiCategory 70 1.75)`  
    - Teste avec 70 kg et 1.75 m : `bmi = 70 / (1.75^2) ≈ 22.86`, donne "Normal".

14. `    print (bmiCategory 90 1.8)`  
    - Teste avec 90 kg et 1.8 m : `bmi = 90 / (1.8^2) ≈ 27.78`, donne "Surpoids".

