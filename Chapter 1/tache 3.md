HC1T3 - Tâche 3 : Vérifier si un nombre est supérieur à 18

```haskell
greaterThan18 :: Int -> Bool
greaterThan18 x = x > 18

main :: IO ()
main = print (greaterThan18 20)
```

Explications :
- **Signature de type** : `greaterThan18 :: Int -> Bool` indique que la fonction prend un entier (`Int`) en entrée et retourne un booléen (`Bool`) en sortie.
- **Pureté** : La fonction est pure, car elle dépend uniquement de son argument `x` et produit toujours le même résultat pour la même entrée, sans effets secondaires.
- **Logique** : L'expression `x > 18` compare `x` à 18 et retourne `True` si `x` est supérieur à 18, sinon `False`.
- **Exemple d'utilisation** : 
  - `greaterThan18 20` retourne `True`.
  - `greaterThan18 18` retourne `False`.
  - `greaterThan18 10` retourne `False`.

