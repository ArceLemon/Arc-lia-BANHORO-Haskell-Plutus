HC3T1 - Tâche 1 : Vérifier si un nombre est positif, négatif ou nul

CODE: 

```haskell
-- Définit une fonction qui vérifie si un nombre est positif, négatif ou nul
checkNumber :: Int -> String
checkNumber n =
    if n > 0 then "Positif"
    else if n < 0 then "Négatif"
    else "Zéro"

-- Fonction principale pour tester
main :: IO ()
main = do
    print (checkNumber 5)
    print (checkNumber (-3))
    print (checkNumber 0)
```

EXPLICATION:

1. `-- Définit une fonction qui vérifie si un nombre est positif, négatif ou nul`  
   - Ceci est un commentaire en Haskell. Les commentaires commencent par `--` et continuent jusqu'à la fin de la ligne.  
   - Ce commentaire sert de documentation pour la fonction suivante (`checkNumber`). Il explique brièvement ce que fait la fonction : elle vérifie si un nombre est positif (plus grand que 0), négatif (plus petit que 0), ou nul (égal à 0).  
   - Les commentaires sont ignorés par le compilateur GHC (Glasgow Haskell Compiler) et n'ont aucun impact sur l'exécution du code. Ils sont essentiels pour la lisibilité, surtout dans des projets plus grands, car Haskell encourage une programmation declarative où le code est concis, et les commentaires aident à comprendre l'intention.  
   - Exemple : Si quelqu'un lit ce code, ce commentaire donne un aperçu immédiat sans avoir à analyser la logique interne de la fonction.

2. `checkNumber :: Int -> String`  
   - Ceci est la **signature de type** de la fonction `checkNumber`. En Haskell, les signatures de type sont optionnelles mais fortement recommandées pour la clarté et pour aider le compilateur à détecter les erreurs de type.  
   - `checkNumber` est le nom de la fonction. Les noms en Haskell commencent généralement par une minuscule (convention), et ils doivent être descriptifs. Ici, "checkNumber" indique que la fonction vérifie un nombre.  
   - `::` est l'opérateur qui sépare le nom de la fonction de sa déclaration de type. Il se lit comme "a pour type".  
   - `Int -> String` décrit le type : la fonction prend un argument de type `Int` (un entier signé, typiquement 32 ou 64 bits selon la plateforme, avec une plage comme -2^31 à 2^31-1 ou plus large) et retourne une valeur de type `String` (une chaîne de caractères, qui est un synonyme de `[Char]` en Haskell).  
   - Implications : Cela rend la fonction pure et typée statiquement. Si vous essayez d'appeler `checkNumber` avec un type incorrect (ex. un `Float`), le compilateur lèvera une erreur avant l'exécution. Cela favorise la sécurité et la robustesse du code.

3. `checkNumber n =`  
   - Ceci commence la définition de la fonction `checkNumber`. Le nom `checkNumber` est suivi du paramètre `n` (un nom arbitraire pour l'argument, souvent court pour "number").  
   - L'opérateur `=` associe la fonction à son corps. En Haskell, les fonctions sont définies par des équations : `checkNumber n = expression` signifie que pour tout `n`, la fonction évalue l'expression qui suit.  
   - `n` est un paramètre formel de type `Int` (inféré de la signature). Il est immutable : une fois lié à une valeur lors de l'appel, il ne peut pas être changé. Cela reflète la nature fonctionnelle pure de Haskell, où il n'y a pas de variables mutables comme en langages impératifs (ex. Python ou C).  
   - Exemple : Si vous appelez `checkNumber 5`, `n` est lié à `5` pour cette évaluation, et la fonction calcule le résultat basé sur cela sans effets secondaires.

4. `    if n > 0 then "Positif"`  
   - Ceci est le début d'une structure conditionnelle `if-then-else` en Haskell. Contrairement à d'autres langages, `if` en Haskell est une expression (pas une instruction) et doit toujours avoir un `else`, car elle retourne une valeur.  
   - `if` introduit la condition.  
   - `n > 0` est la condition booléenne : elle compare `n` à `0` avec l'opérateur `>` (plus grand que), qui retourne un `Bool` (`True` si `n` est positif, `False` sinon). L'opérateur `>` est infixe et fonctionne sur les types numériques comme `Int`.  
   - `then "Positif"` : Si la condition est `True`, l'expression retourne la chaîne `"Positif"`. Notez que les guillemets doubles indiquent une littérale de type `String`.  
   - Indentation : Les espaces (ou tabulations) avant `if` indiquent que c'est la continuation de la ligne précédente. Haskell est sensible à l'indentation (comme Python), et une mauvaise indentation causerait une erreur de parsing. Ici, cela structure le corps de la fonction.

5. `    else if n < 0 then "Négatif"`  
   - Ceci est la première branche `else` de la structure conditionnelle. `else` est obligatoire et gère le cas où la condition précédente est `False`.  
   - `if n < 0` : Une nouvelle condition imbriquée. `n < 0` utilise l'opérateur `<` (plus petit que) pour vérifier si `n` est négatif, retournant un `Bool`.  
   - `then "Négatif"` : Si cette condition est `True`, retourne la chaîne `"Négatif"`.  
   - Imbrication : C'est un `if` imbriqué dans le `else`, ce qui permet de gérer plusieurs cas. En Haskell, on pourrait aussi utiliser des guards (`|`) pour plus de lisibilité dans des fonctions complexes, mais ici `if-then-else` est simple et explicite.  
   - Exemple : Si `n = -3`, la première condition (`n > 0`) est `False`, donc on passe à ce `else`, où `n < 0` est `True`, et on retourne `"Négatif"`.

6. `    else "Zéro"`  
   - Ceci est la branche finale `else` de la structure imbriquée. Elle gère le cas où ni `n > 0` ni `n < 0` n'est vrai, ce qui signifie que `n == 0`.  
   - `"Zéro"` : Retourne cette chaîne si `n` est nul. Pas besoin de `then` ici, car c'est la partie finale du `else`.  
   - Fermeture de l'expression : Cela termine la structure `if-then-else`, qui retourne toujours une `String`, satisfaisant la signature de type. Sans ce `else`, le compilateur signalerait une erreur car tous les chemins doivent retourner une valeur.  
   - Exemple : Pour `n = 0`, les deux conditions précédentes sont `False`, donc on retourne `"Zéro"`. Cela assure une couverture exhaustive des cas pour un `Int` (positif, négatif, ou nul).

7. (Ligne vide)  
   - Une ligne vide pour séparer les définitions. En Haskell, les lignes vides sont ignorées et servent à améliorer la lisibilité du code, en groupant logiquement les parties (ici, séparation entre la fonction `checkNumber` et `main`).

8. `-- Fonction principale pour tester`  
   - Un autre commentaire expliquant la fonction suivante (`main`). Il indique que cette fonction sert à tester `checkNumber` avec des exemples.  
   - Comme le premier commentaire, il est ignoré par le compilateur mais aide à la maintenance du code.

9. `main :: IO ()`  
   - Signature de type de la fonction `main`, qui est le point d'entrée d'un programme Haskell exécutable.  
   - `main` est un nom spécial : GHC l'appelle automatiquement lors de l'exécution.  
   - `IO ()` : Indique que `main` effectue des opérations d'entrée/sortie (IO) et retourne "rien" (`()` est le type vide, comme `void` dans d'autres langages). `IO` est une monade qui encapsule les effets secondaires (comme l'affichage), permettant de garder le reste du code pur.

10. `main = do`  
    - Définit le corps de `main` en commençant un bloc `do`. `do` est une notation syntaxique pour séquencer des actions dans une monade comme `IO`.  
    - Sans `do`, il serait plus difficile de combiner plusieurs actions `IO` (comme plusieurs `print`). `do` permet d'écrire du code qui ressemble à un style impératif, mais Haskell reste fonctionnel sous le capot.

11. `    print (checkNumber 5)`  
    - Première action dans le bloc `do`. `print` est une fonction de la bibliothèque standard (`Prelude`) qui affiche une valeur dans la console (effet `IO`).  
    - `(checkNumber 5)` : Appelle la fonction `checkNumber` avec l'argument `5` (positif). Cela évalue à `"Positif"`.  
    - `print` convertit la valeur en chaîne (via `show`) et l'affiche suivie d'un saut de ligne.  
    - Indentation : Les actions dans `do` doivent être indentées de manière consistente pour indiquer qu'elles font partie du bloc.  
    - Exemple : Cela affichera `"Positif"` dans la console.

12. `    print (checkNumber (-3))`  
    - Deuxième action : Appelle `checkNumber` avec `-3` (négatif), qui retourne `"Négatif"`.  
    - `print` affiche `"Négatif"`.  
    - Le signe négatif `-` devant `3` crée un entier négatif. En Haskell, les négatifs sont supportés nativement pour `Int`.  
    - Cela teste le cas négatif, démontrant que la fonction gère correctement les valeurs en dessous de 0.

13. `    print (checkNumber 0)`  
    - Troisième action : Appelle `checkNumber` avec `0` (nul), qui retourne `"Zéro"`.  
    - `print` affiche `"Zéro"`.  
    - Cela complète les tests pour les trois cas possibles, assurant une couverture exhaustive. Sans ce test, on pourrait manquer un bug si le `else` final était mal implémenté.

