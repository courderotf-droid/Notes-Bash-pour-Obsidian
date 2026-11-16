Chaque commande renvoie un code de sortie, accessible avec `$?`.

- `0` : réussite.
- Valeur non nulle : échec ou situation particulière.

```bash
mkdir test
echo "$?"  # code de retour de mkdir
```

Il faut lire `$?` immédiatement : chaque nouvelle commande le remplace.

## Exploiter le résultat

```bash
if cp "$source" "$destination"; then
    echo "Copie réussie"
else
    echo "Échec de la copie" >&2
fi
```

Les opérateurs `&&` et `||` permettent également de réagir au résultat :

```bash
commande && echo "Succès"
commande || echo "Échec"
```

## Codes de sortie d'un script

```bash
exit 0
```

`exit` termine le script avec le code indiqué. Une fonction utilise plutôt `return`.

## Options de robustesse

```bash
set -o errexit
set -o nounset
set -o pipefail
```

Raccourci courant :

```bash
set -euo pipefail
```

Ces options peuvent aider, mais `set -e` a des règles de déclenchement subtiles et ne remplace pas une gestion explicite des erreurs. Les utiliser en comprenant leurs effets.

Voir [[Bonnes pratiques et sécurité - Bash]].
