Les guillemets déterminent comment Bash interprète les espaces, variables et caractères spéciaux.

## Guillemets doubles

```bash
nom="Francis"
echo "Bonjour $nom"
```

Les variables et substitutions de commandes sont développées. Les espaces restent protégés.

## Guillemets simples

```bash
echo 'Le texte $nom reste littéral'
```

Aucune expansion de variable ou de commande n'est effectuée.

## Sans guillemets

```bash
echo Bonjour
```

Les expansions non protégées peuvent subir le découpage en mots et l'expansion des motifs (`*`, `?`, `[...]`). C'est une source fréquente de bugs.

## Échappement

La barre oblique inversée `\` neutralise généralement le caractère spécial qui suit :

```bash
echo "Prix : \$5"
echo "Un espace : fichier\ important.txt"
```

## Règle pratique

Mettre les expansions entre guillemets doubles presque systématiquement :

```bash
cp "$source" "$destination"
```

Cela évite qu'un chemin contenant des espaces soit interprété comme plusieurs arguments. Voir [[Variables et expansions - Bash]].
