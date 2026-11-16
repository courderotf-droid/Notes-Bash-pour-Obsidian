## Arguments du script

Pour un script lancé ainsi :

```bash
./script.sh alpha beta
```

| Paramètre  | Contenu                                                           |
| ---------- | ----------------------------------------------------------------- |
| `$0`       | Nom ou chemin du script                                           |
| `$1`, `$2` | Premier et deuxième arguments                                     |
| `$#`       | Nombre d'arguments                                                |
| `"$@"`     | Tous les arguments, séparément                                    |
| `"$*"`     | Tous les arguments regroupés en une seule chaîne entre guillemets |
|            |                                                                   |

Pour transmettre fidèlement tous les arguments à une autre commande, préférer `"$@"`.

## Lire une saisie

```bash
read -r -p "Ton nom : " nom
printf 'Bonjour %s\n' "$nom"
```

`-r` empêche l'interprétation des barres obliques inversées. `-p` affiche une invite.

## Parcourir les arguments

```bash
for argument in "$@"; do
    printf 'Argument : %s\n' "$argument"
done
```

## Options

Pour les options courtes, `getopts` permet de les analyser proprement :

```bash
while getopts ":f:v" option; do
    case "$option" in
        f) fichier="$OPTARG" ;;
        v) verbeux=true ;;
        :) echo "Valeur manquante pour -$OPTARG" >&2; exit 2 ;;
        \?) echo "Option inconnue : -$OPTARG" >&2; exit 2 ;;
    esac
done
```

Voir [[Fonctions - Bash]].
