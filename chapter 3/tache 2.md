HC3T2 - Tâche 2 : Déterminer la note à partir d’un score avec des gardes

CODE:

```haskell
-- Définit une fonction qui classe un score en note (A, B, C, D, F)
grade :: Int -> String
grade n
  | n >= 90 = "A"
  | n >= 80 = "B"
  | n >= 70 = "C"
  | n >= 60 = "D"
  | otherwise = "F"

-- Fonction principale pour tester
main :: IO ()
main = do
    print (grade 95)
    print (grade 72)
    print (grade 50)
```


EXPLICATION:

1. `-- Définit une fonction qui classe un score en note (A, B, C, D, F)`  
   - Ceci est un commentaire en Haskell. Les commentaires commencent par `--` et continuent jusqu'à la fin de la ligne.  
   - Ce commentaire sert de documentation pour la fonction suivante (`grade`). Il explique brièvement ce que fait la fonction : elle prend un score (un entier) et le classe en une note alphabétique basée sur des plages spécifiques (90+ pour "A", 80-89 pour "B", etc., et en dessous de 60 pour "F").  
   - Les commentaires sont ignorés par le compilateur GHC et n'ont aucun impact sur l'exécution du code. Ils sont cruciaux pour la lisibilité, surtout dans un langage concis comme Haskell, où le code est déclaratif. Cela aide les autres développeurs (ou vous-même plus tard) à comprendre l'intention sans analyser la logique interne.  
   - Exemple : Si ce code est partagé dans un dépôt GitHub comme le vôtre, ce commentaire fournit un aperçu rapide de la fonction sans exécuter le code.

2. `grade :: Int -> String`  
   - Ceci est la **signature de type** de la fonction `grade`. En Haskell, les signatures de type sont optionnelles mais fortement recommandées pour améliorer la clarté, aider à la détection d'erreurs de type au moment de la compilation, et documenter les attentes d'entrée/sortie.  
   - `grade` est le nom de la fonction. Les noms en Haskell commencent généralement par une minuscule (convention camelCase ou snake_case), et ici "grade" est descriptif, indiquant qu'il s'agit de noter un score.  
   - `::` est l'opérateur qui sépare le nom de la fonction de sa déclaration de type. Il se lit comme "a pour type" ou "est de type".  
   - `Int -> String` décrit le type : la fonction prend un argument de type `Int` (un entier signé, typiquement 32 ou 64 bits selon la plateforme, avec une plage comme -2^31 à 2^31-1) et retourne une valeur de type `String` (une chaîne de caractères, synonyme de `[Char]` en Haskell).  
   - Implications : Cela rend la fonction typée statiquement et pure. Si vous appelez `grade` avec un type incorrect (ex. un `Float`), le compilateur GHC lèvera une erreur avant l'exécution, favorisant la sécurité. La flèche `->` indique une fonction curryfiée, mais ici c'est une fonction unaire simple.

3. `grade n`  
   - Ceci commence la définition de la fonction `grade`. Le nom `grade` est suivi du paramètre `n` (un nom arbitraire, souvent court pour "number" ou "score").  
   - En Haskell, les fonctions sont définies par des équations, et cette ligne prépare les gardes (|). Sans `=`, cela indique que le corps suit sur les lignes indentées.  
   - `n` est un paramètre formel de type `Int` (inféré de la signature). Il est immutable : une fois lié à une valeur lors de l'appel, il ne peut pas être changé, reflétant la nature fonctionnelle pure de Haskell (pas de variables mutables comme en langages impératifs).  
   - Exemple : Lors d'un appel comme `grade 95`, `n` est lié à `95` pour cette évaluation, et la fonction calcule le résultat basé sur les gardes suivantes sans effets secondaires. L'évaluation est paresseuse : Haskell n'évalue `n` que si nécessaire.

4. `  | n >= 90 = "A"`  
   - Ceci est la première **garde** (guard) de la fonction. Les gardes commencent par `|` (pipe) et sont une façon idiomatique en Haskell de gérer des conditions multiples, similaire à un `switch` ou des `if` imbriqués, mais plus concis et déclaratifs.  
   - `n >= 90` est la condition booléenne : elle compare `n` à `90` avec l'opérateur `>=` (plus grand ou égal), qui retourne un `Bool` (`True` si `n` est au moins 90, `False` sinon). L'opérateur `>=` est infixe et fonctionne sur les types numériques comme `Int`.  
   - `= "A"` : Si la condition est `True`, la fonction retourne la chaîne `"A"`. Les guillemets doubles indiquent une littérale de type `String`.  
   - Indentation : Les gardes doivent être indentées par rapport à la ligne de définition (`grade n`), et Haskell est sensible à l'indentation (erreur si mal alignée). Les gardes sont évaluées de haut en bas : la première condition vraie est sélectionnée.  
   - Exemple : Pour `n = 95`, `95 >= 90` est `True`, donc retourne `"A"`. Cela gère les scores excellents (90 et plus).

5. `  | n >= 80 = "B"`  
   - Deuxième garde. Si la garde précédente est `False` (c'est-à-dire `n < 90`), on vérifie cette condition.  
   - `n >= 80` : Compare `n` à `80` avec `>=`, retourne `True` si `n` est entre 80 et 89 (car la garde précédente a filtré les valeurs supérieures ou égales à 90).  
   - `= "B"` : Retourne `"B"` si vrai.  
   - Exemple : Pour `n = 85`, la première garde est `False` (85 < 90), mais `85 >= 80` est `True`, donc retourne `"B"`. Cela illustre le flux séquentiel des gardes, évitant les conditions complexes comme `n >= 80 && n < 90`.

6. `  | n >= 70 = "C"`  
   - Troisième garde. S'exécute si les deux précédentes sont `False` (c'est-à-dire `n < 80`).  
   - `n >= 70` : Vérifie si `n` est entre 70 et 79.  
   - `= "C"` : Retourne `"C"` si vrai.  
   - Exemple : Pour `n = 72`, les gardes 1 et 2 sont `False` (72 < 90 et 72 < 80), mais `72 >= 70` est `True`, donc retourne `"C"`. Les gardes simplifient les conditions imbriquées et rendent le code plus lisible.

7. `  | n >= 60 = "D"`  
   - Quatrième garde. S'exécute si `n < 70`.  
   - `n >= 60` : Vérifie si `n` est entre 60 et 69.  
   - `= "D"` : Retourne `"D"` si vrai.  
   - Exemple : Pour `n = 65`, retourne `"D"`. Cela continue le pattern de classification descendante, efficace car Haskell arrête l'évaluation dès la première garde vraie (évaluation paresseuse).

8. `  | otherwise = "F"`  
   - Garde finale. `otherwise` est une constante booléenne spéciale en Haskell, équivalente à `True`, servant de catch-all (comme un `else` par défaut). Elle capture tous les cas non couverts par les gardes précédentes (ici, `n < 60`).  
   - `= "F"` : Retourne `"F"` pour les scores en dessous de 60.  
   - Sans cette garde, la fonction serait incomplète, et GHC signalerait une erreur comme "Non-exhaustive patterns" (patterns non exhaustifs), car tous les cas doivent être couverts en Haskell.  
   - Exemple : Pour `n = 50`, toutes les gardes précédentes sont `False`, donc `otherwise` s'applique et retourne `"F"`.

9. (Ligne vide)  
   - Une ligne vide pour séparer les définitions. En Haskell, les lignes vides sont ignorées et servent à structurer le code visuellement, en groupant les parties logiques (ici, séparation entre `grade` et `main`). Cela n'affecte pas la compilation mais améliore la lisibilité.

10. `-- Fonction principale pour tester`  
    - Un commentaire expliquant la fonction suivante (`main`). Il indique que cette fonction sert à tester `grade` avec des exemples spécifiques.  
    - Comme les commentaires précédents, il est ignoré par le compilateur mais aide à la maintenance et à la compréhension du code.

11. `main :: IO ()`  
    - Signature de type de la fonction `main`, qui est le point d'entrée d'un programme Haskell exécutable. GHC appelle automatiquement `main` lors de l'exécution.  
    - `IO ()` : Indique que `main` effectue des opérations d'entrée/sortie (IO) et retourne "rien" (`()` est le type vide, similaire à `void` en C). `IO` est une monade qui encapsule les effets secondaires (comme l'affichage avec `print`), permettant de garder le reste du code pur et sans effets.

12. `main = do`  
    - Définit le corps de `main` en commençant un bloc `do`. `do` est une notation syntaxique pour séquencer des actions dans une monade comme `IO`, rendant le code plus impératif en apparence tout en restant fonctionnel.  
    - Sans `do`, combiner plusieurs actions `IO` serait plus verbeux (avec des `>>=`). Ici, `do` permet d'écrire les `print` comme des instructions séquentielles.

13. `    print (grade 95)`  
    - Première action dans le bloc `do`. `print` est une fonction de la bibliothèque standard (`Prelude`) qui affiche une valeur dans la console (effet `IO`).  
    - `(grade 95)` : Appelle la fonction `grade` avec l'argument `95` (un `Int` positif >= 90). Cela évalue à `"A"`.  
    - `print` convertit la valeur en chaîne via la classe `Show` (implémentée pour `String`) et l'affiche suivie d'un saut de ligne.  
    - Indentation : Les actions dans `do` doivent être indentées de manière consistente.  
    - Exemple : Cela affichera `"A"` dans la console, testant le cas "A" (score élevé).

14. `    print (grade 72)`  
    - Deuxième action : Appelle `grade` avec `72` (entre 70 et 79), qui retourne `"C"`.  
    - `print` affiche `"C"`.  
    - Cela teste un cas intermédiaire, démontrant que les gardes filtrent correctement les plages.

15. `    print (grade 50)`  
    - Troisième action : Appelle `grade` avec `50` (en dessous de 60), qui retourne `"F"`.  
    - `print` affiche `"F"`.  
    - Cela complète les tests pour des cas variés (haut, moyen, bas), assurant que la fonction gère tous les scénarios. Sans ces tests, on pourrait manquer des bugs, mais en Haskell, la compilation statique aide déjà beaucoup.

