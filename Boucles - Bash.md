## Boucle `for`

Parcourt une liste d'éléments :

```bash
for fichier in *.txt; do
    echo "$fichier"
done
```

Boucle sur une séquence numérique :

```bash
for i in {1..5}; do
    echo "$i"
done
```

## Boucle `while`

Répète tant que la condition est vraie :

```bash
compteur=0

while [[ "$compteur" -lt 5 ]]; do
    echo "$compteur"
    ((compteur++))
done
```

## Boucle `until`

Répète jusqu'à ce que la condition devienne vraie :

```bash
until [[ -f "terminé.txt" ]]; do
    sleep 1
done
```

## Contrôler une boucle

- `break` : quitte immédiatement la boucle.
- `continue` : passe à l'itération suivante.

Éviter de parcourir les fichiers avec `for fichier in $(ls)` : les espaces et caractères spéciaux dans les noms provoquent des erreurs. Préférer les motifs comme `*.txt` ou `find` selon le besoin.
