```haskell
-- Vérifie si une année est bissextile
isLeapYear :: Int -> Bool
isLeapYear year = if year `mod` 400 == 0
                  then True
                  else if year `mod` 100 == 0
                       then False
                       else if year `mod` 4 == 0
                            then True
                            else False

-- Fonction principale pour tester
main :: IO ()
main = do
    print (isLeapYear 2000)
    print (isLeapYear 1900)
    print (isLeapYear 2024)
```

Explications ligne par ligne :

1. `-- Vérifie si une année est bissextile`  
   - Commentaire expliquant que `isLeapYear` détermine si une année est bissextile selon les règles du calendrier grégorien. Ignoré par le compilateur, il sert de documentation.

2. `isLeapYear :: Int -> Bool`  
   - Signature de type indiquant que la fonction prend un `Int` (l'année) et retourne un `Bool` (`True` pour bissextile, `False` sinon). Elle est pure et typée statiquement.

3. `isLeapYear year =`  
   - Début de la définition avec le paramètre `year` (année à vérifier). L'opérateur `=` associe la fonction à une expression `if-then-else`, et `year` est immuable.

4. `    if year `mod` 400 == 0`  
   - Première condition : utilise `mod` (opérateur infixe pour le modulo) pour vérifier si `year` est divisible par 400 (reste 0). Les backticks (`) permettent d'utiliser `mod` en notation infixe.

5. `    then True`  
   - Si la condition est `True`, retourne `True` (année bissextile, ex. 2000, car divisible par 400 prime sur les autres règles).

6. `    else if year `mod` 100 == 0`  
   - Sinon, vérifie si `year` est divisible par 100. Si oui, entre dans une sous-condition.

7. `         then False`  
   - Si divisible par 100 mais pas par 400 (vu que la première condition a échoué), retourne `False` (ex. 1900 n’est pas bissextile).

8. `    else if year `mod` 4 == 0`  
   - Sinon, vérifie si `year` est divisible par 4, condition suivante des règles bissextiles.

9. `         then True`  
   - Si divisible par 4 (et pas par 100, car conditions précédentes échouées), retourne `True` (ex. 2024 est bissextile).

10. `    else False`  
    - Sinon (non divisible par 4), retourne `False`, couvrant tous les cas restants.

11. (Ligne vide)  
    - Sépare visuellement les définitions pour une meilleure lisibilité.

12. `-- Fonction principale pour tester`  
    - Commentaire indiquant que `main` teste `isLeapYear`.

13. `main :: IO ()`  
    - Signature de `main`, point d’entrée avec effet `IO` et retour vide (`()`).

14. `main = do`  
    - Début d’un bloc `do` pour séquencer les `print`.

15. `    print (isLeapYear 2000)`  
    - Teste 2000 (divisible par 400), affiche `True`.

16. `    print (isLeapYear 1900)`  
    - Teste 1900 (divisible par 100 mais pas 400), affiche `False`.

17. `    print (isLeapYear 2024)`  
    - Teste 2024 (divisible par 4 mais pas 100), affiche `True`.

