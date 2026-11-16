Les processus utilisent généralement trois flux standards :

- `stdin` (0) : entrée standard.
- `stdout` (1) : sortie standard.
- `stderr` (2) : sortie d'erreur.

## Redirections

```bash
commande > sortie.txt       # écrase le fichier
commande >> sortie.txt      # ajoute à la fin
commande < entree.txt       # lit depuis un fichier
commande 2> erreurs.txt     # redirige stderr
commande > tout.txt 2>&1    # redirige stdout et stderr
commande &> tout.txt        # forme Bash équivalente
```

`/dev/null` permet d'ignorer une sortie :

```bash
commande 2>/dev/null
```

## Pipelines

Le caractère `|` transmet la sortie standard d'une commande à l'entrée standard de la suivante :

```bash
ps aux | grep firefox
```

Exemple de traitement :

```bash
cat journal.log | grep "ERROR" | wc -l
```

Ici, `grep` filtre les lignes et `wc -l` les compte. On peut simplifier :

```bash
grep "ERROR" journal.log | wc -l
```

## Attention au code de retour

Par défaut, le code de retour d'un pipeline est celui de sa dernière commande. Avec `set -o pipefail`, le pipeline échoue si une commande échoue (selon la première commande en échec à droite).

Voir [[Codes de retour et erreurs - Bash]].
