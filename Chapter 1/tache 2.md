HC1T2 - Tâche 2 : Exemple de fonction pure

Voici une fonction Haskell pure pour calculer l'aire d'un cercle à partir de son rayon :

```haskell
circleArea :: Double -> Double
circleArea r = pi * r * r

main :: IO ()
main = print (circleArea 2)
```

Explications :
- **Signature de type** : `circleArea :: Double -> Double` indique que la fonction prend un `Double` (nombre à virgule flottante pour plus de précision) comme entrée (le rayon) et retourne un `Double` (l'aire).
- **Pureté** : La fonction est pure car elle dépend uniquement de son argument `r` et de la constante `pi` (définie dans le module standard de Haskell). Elle produit toujours le même résultat pour la même entrée, sans effets secondaires ni dépendance à un état externe.
- **Formule** : L'aire d'un cercle est calculée par la formule `π * r²`. Ici, `pi` est une constante intégrée dans Haskell, et `r * r` calcule le carré du rayon.
- **Exemple d'utilisation** : `circleArea 2` retourne environ `12.566370614359172` (π * 2²).


