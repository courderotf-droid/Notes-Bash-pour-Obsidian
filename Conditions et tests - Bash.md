## Structure conditionnelle

```bash
if [[ "$age" -ge 18 ]]; then
    echo "Majeur"
elif [[ "$age" -gt 0 ]]; then
    echo "Mineur"
else
    echo "Âge invalide"
fi
```

`then` commence le bloc et `fi` le termine.

## Opérateurs numériques

| Opérateur | Signification |
|---|---|
| `-eq` | égal |
| `-ne` | différent |
| `-lt` | inférieur |
| `-le` | inférieur ou égal |
| `-gt` | supérieur |
| `-ge` | supérieur ou égal |

Dans `[[ ... ]]`, `==` et `!=` servent notamment aux comparaisons de chaînes.

## Tester les fichiers

```bash
[[ -e "$chemin" ]]  # existe
[[ -f "$chemin" ]]  # fichier ordinaire
[[ -d "$chemin" ]]  # répertoire
[[ -r "$chemin" ]]  # lisible
[[ -w "$chemin" ]]  # modifiable
[[ -x "$chemin" ]]  # exécutable
```

## Logique

```bash
if [[ -f "$fichier" && -r "$fichier" ]]; then
    cat "$fichier"
fi
```

- `&&` : ET logique.
- `||` : OU logique.
- `!` : négation.

Préférer `[[ ... ]]` à l'ancienne syntaxe `[ ... ]` dans les scripts Bash : elle est plus robuste et gère mieux certains cas.

Voir [[Codes de retour et erreurs - Bash]].
