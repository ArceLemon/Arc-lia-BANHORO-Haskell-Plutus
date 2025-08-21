HC3T10 - Tâche avancée 10 : Vérifier si une chaîne est un palindrome (récursion, gardes)

```haskell
-- Vérifie si une chaîne est un palindrome
isPalindrome :: String -> Bool
isPalindrome str
  | length str <= 1 = True
  | head str == last str = isPalindrome (tail str)
  | otherwise = False

-- Fonction principale pour tester
main :: IO ()
main = do
    print (isPalindrome "racecar")
    print (isPalindrome "haskell")
    print (isPalindrome "madam")
```

### Explications ligne par ligne :

1. `-- Vérifie si une chaîne est un palindrome`  
   - Commentaire indiquant que `isPalindrome` détermine si une chaîne se lit pareil à l’envers. Ignoré par le compilateur, il documente l’objectif.

2. `isPalindrome :: String -> Bool`  
   - Signature de type spécifiant que la fonction prend un `String` et retourne un `Bool` (`True` si palindrome, `False` sinon). Pure et typée statiquement.

3. `isPalindrome str`  
   - Début de la définition avec `str` comme paramètre (chaîne à vérifier), immuable, préparant les gardes pour l’évaluation.

4. `  | length str <= 1 = True`  
   - Première garde : vérifie si la longueur de `str` est 0 ou 1 avec `length` et `<=`. Si vrai, retourne `True` (chaînes vides ou d’un caractère sont des palindromes par définition).

5. `  | head str == last str = isPalindrome (tail str)`  
   - Deuxième garde : vérifie si le premier caractère (`head str`) égale le dernier (`last str`) avec `==`. Si vrai, appelle récursivement `isPalindrome` sur le reste (`tail str`, sans le premier), réduisant la chaîne.

6. `  | otherwise = False`  
   - Garde par défaut avec `otherwise` (équivalent à `True`), retournant `False` si les caractères ne correspondent pas, arrêtant la récursion.

7. (Ligne vide)  
   - Sépare visuellement les définitions pour la lisibilité.

8. `-- Fonction principale pour tester`  
   - Commentaire indiquant que `main` teste `isPalindrome`.

9. `main :: IO ()`  
   - Signature de `main`, point d’entrée avec effet `IO` et retour vide (`()`).

10. `main = do`  
    - Début d’un bloc `do` pour séquencer les `print`.

11. `    print (isPalindrome "racecar")`  
    - Teste "racecar" : `head` = 'r', `last` = 'r', puis récursivement "aceca" jusqu’à `True`, affiche `True`.

12. `    print (isPalindrome "haskell")`  
    - Teste "haskell" : `head` = 'h', `last` = 'l', ne correspond pas, affiche `False`.

13. `    print (isPalindrome "madam")`  
    - Teste "madam" : `head` = 'm', `last` = 'm', puis "ada" jusqu’à `True`, affiche `True`.
