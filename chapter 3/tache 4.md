HC3T4 - Tâche 4 : Calculer l’aire d’un triangle avec la formule de Héron

```haskell
-- Calcule l'aire d'un triangle à partir de ses trois côtés en utilisant la formule de Héron
triangleArea :: Float -> Float -> Float -> Float
triangleArea a b c = let s = (a + b + c) / 2
                     in sqrt (s * (s - a) * (s - b) * (s - c))

-- Fonction principale pour tester
main :: IO ()
main = do
    print (triangleArea 3 4 5)
    print (triangleArea 7 8 9)
```

### Explications ligne par ligne :

1. `-- Calcule l'aire d'un triangle à partir de ses trois côtés en utilisant la formule de Héron`  
   - Commentaire en Haskell (débutant par `--`) qui explique le but de la fonction suivante (`triangleArea`). Il indique que la fonction calcule l'aire d'un triangle en utilisant la formule de Héron, basée sur les longueurs des trois côtés. Ce commentaire est ignoré par le compilateur GHC mais est essentiel pour la documentation et la compréhension du code.

2. `triangleArea :: Float -> Float -> Float -> Float`  
   - Signature de type de la fonction `triangleArea`. Elle déclare que la fonction prend trois arguments de type `Float` (nombres à virgule flottante, permettant des décimales) et retourne un `Float`.  
   - Les flèches `->` indiquent une fonction curryfiée, où chaque argument est appliqué séquentiellement. Par exemple, `triangleArea 3 4 5` est équivalent à `(triangleArea 3 4) 5`.  
   - Le type `Float` est choisi pour gérer les résultats décimaux (comme l'aire), bien que `Double` pourrait offrir plus de précision. Cela garantit une vérification statique des types par le compilateur.

3. `triangleArea a b c =`  
   - Début de la définition de la fonction `triangleArea` avec les paramètres `a`, `b`, et `c`, représentant les longueurs des trois côtés du triangle. Ces noms sont arbitraires mais descriptifs.  
   - L'opérateur `=` associe la fonction à son corps, qui sera défini avec une expression utilisant `let`.  
   - Les paramètres sont immuables (car Haskell est purement fonctionnel), et leur valeur est déterminée à l'appel de la fonction.

4. `    let s = (a + b + c) / 2`  
   - Utilise une expression `let` pour définir une variable locale `s`, le demi-périmètre du triangle. `let` permet de nommer une sous-expression dans un scope local, évitant de répéter le calcul.  
   - `(a + b + c)` calcule le périmètre total en additionnant les trois côtés avec l'opérateur `+`.  
   - `/ 2` divise ce total par 2 pour obtenir le demi-périmètre (`s`), utilisant l'opérateur `/` pour les flottants.  
   - Exemple : Pour `a = 3`, `b = 4`, `c = 5`, `s = (3 + 4 + 5) / 2 = 12 / 2 = 6.0`.  
   - La portée de `s` est limitée à l'expression qui suit `in`, et sa valeur est calculée paresseusement uniquement si nécessaire.

5. `    in sqrt (s * (s - a) * (s - b) * (s - c))`  
   - `in` termine la clause `let` et spécifie l'expression qui utilise `s`. Cette ligne applique la formule de Héron : l'aire est la racine carrée (`sqrt`) du produit `s * (s - a) * (s - b) * (s - c)`.  
   - `sqrt` est une fonction de la bibliothèque standard (`Prelude`) qui calcule la racine carrée d'un `Float`.  
   - Les soustractions `s - a`, `s - b`, et `s - c` calculent les différences entre le demi-périmètre et chaque côté, nécessaires pour la formule.  
   - Les multiplications `*` combinent ces termes. Par exemple, pour `s = 6`, `a = 3`, `b = 4`, `c = 5`, on obtient `6 * (6 - 3) * (6 - 4) * (6 - 5) = 6 * 3 * 2 * 1 = 36`, et `sqrt 36 = 6.0`.  
   - Cette expression est pure : elle dépend uniquement de `a`, `b`, et `c`, sans effets secondaires.

6. (Ligne vide)  
   - Une ligne vide séparant les définitions, ignorée par le compilateur mais améliorant la lisibilité en structurant le code visuellement.

7. `-- Fonction principale pour tester`  
   - Commentaire indiquant que la fonction suivante (`main`) sert à tester `triangleArea` avec des exemples. Il est ignoré par GHC mais aide à la compréhension.

8. `main :: IO ()`  
   - Signature de type de `main`, le point d'entrée standard d'un programme Haskell. `IO ()` indique que `main` effectue des opérations d'entrée/sortie (comme l'affichage) et retourne une unité vide (`()`), similaire à `void` dans d'autres langages.

9. `main = do`  
   - Début d'un bloc `do` pour séquencer les actions `IO`. `do` permet d'écrire des séquences d'opérations (comme plusieurs `print`) de manière impérative, bien que Haskell reste fonctionnel en interne.

10. `    print (triangleArea 3 4 5)`  
    - Première action : appelle `triangleArea` avec les côtés 3, 4, 5 (un triangle rectangle 3-4-5). Le résultat est `6.0` (car \( \sqrt{6 \cdot 3 \cdot 2 \cdot 1} = \sqrt{36} = 6.0 \)).  
    - `print` affiche ce résultat sous forme de chaîne via la classe `Show`, suivi d'un saut de ligne.

11. `    print (triangleArea 7 8 9)`  
    - Deuxième action : appelle `triangleArea` avec 7, 8, 9 (un triangle valide, mais non rectangle). Le résultat est approximativement `26.832815` (calculé via \( s = 12, \sqrt{12 \cdot 5 \cdot 4 \cdot 3} \approx 26.832815 \)).  
    - `print` affiche cette valeur décimale, testant un cas plus complexe.

