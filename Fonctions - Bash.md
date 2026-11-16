Une fonction regroupe des commandes réutilisables.

## Déclaration et appel

```bash
dire_bonjour() {
    local nom="$1"
    echo "Bonjour $nom"
}

dire_bonjour "Francis"
```

- `$1`, `$2`, etc. désignent les arguments.
- `local` limite une variable à la fonction.
- L'appel s'effectue par le nom de la fonction.

## Valeur de retour

En Bash, le code de retour d'une fonction est un entier entre 0 et 255. `return` transmet ce code, pas une chaîne de caractères.

```bash
verifier_fichier() {
    [[ -f "$1" ]]
}

if verifier_fichier "config.txt"; then
    echo "Fichier présent"
fi
```

Pour produire une valeur textuelle, utiliser généralement `printf` puis une substitution de commande :

```bash
nom_fichier() {
    printf '%s\n' "rapport.txt"
}

fichier=$(nom_fichier)
```

Voir [[Entrées et arguments - Bash]] et [[Codes de retour et erreurs - Bash]].
