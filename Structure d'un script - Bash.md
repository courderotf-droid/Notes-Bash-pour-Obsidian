Un script est un fichier texte contenant une suite de commandes.

## Exemple minimal

```bash
#!/usr/bin/env bash

echo "Bonjour"
```

- `#!` introduit le *shebang*, qui indique l'interpréteur.
- `/usr/bin/env bash` recherche Bash dans le `PATH`.
- Les lignes commençant par `#` sont des commentaires, sauf le shebang.

## Exécution

```bash
chmod +x script.sh
./script.sh
```

Ou sans rendre le fichier exécutable :

```bash
bash script.sh
```

La seconde méthode lance explicitement Bash. Le shebang est surtout utilisé lors de l'exécution directe.

## Séparateurs

```bash
commande1
commande2
commande1; commande2
commande1 && commande2
commande1 || commande2
```

- Nouvelle ligne ou `;` : sépare les commandes.
- `&&` : exécute la seconde si la première réussit.
- `||` : exécute la seconde si la première échoue.

Voir [[Codes de retour et erreurs]].
