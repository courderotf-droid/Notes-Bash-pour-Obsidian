## Déclarer une variable

```bash
nom="Francis"
age=17
```

Aucun espace n'est autorisé autour de `=` lors d'une affectation.

Pour lire une variable, préfixer son nom par `$` :

```bash
echo "$nom"
echo "${nom}"
```

Les accolades délimitent explicitement le nom :

```bash
fichier="rapport"
echo "${fichier}.txt"
```

## Variables d'environnement

Une variable ordinaire n'est pas automatiquement transmise aux programmes lancés par le script.

```bash
export LANG="fr_FR.UTF-8"
```

`export` rend la variable disponible dans l'environnement des processus enfants.

## Commandes et calculs

```bash
date_actuelle=$(date)
nombre=$((5 + 3))
```

- `$(...)` exécute une commande et récupère sa sortie standard.
- `$((...))` effectue une expansion arithmétique entière.

Éviter l'ancienne syntaxe avec accents graves : `` `commande` ``.

## Tableaux indexés

```bash
fruits=("pomme" "poire" "kiwi")
echo "${fruits[0]}"
echo "${fruits[@]}"
echo "${#fruits[@]}"  # nombre d'éléments
```

Toujours entourer `"${fruits[@]}"` de guillemets pour préserver chaque élément comme argument distinct.

Voir [[Guillemets et échappement - Bash]].
