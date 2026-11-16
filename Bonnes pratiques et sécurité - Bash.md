## Écrire des scripts fiables

- Toujours protéger les expansions : `"$variable"`.
- Préférer `[[ ... ]]` pour les tests Bash.
- Utiliser `printf` plutôt que `echo` pour une sortie précisément contrôlée.
- Vérifier les arguments et les fichiers avant de les utiliser.
- Envoyer les messages d'erreur sur `stderr` : `printf 'Erreur\n' >&2`.
- Donner des noms explicites aux variables et fonctions.
- Commenter les choix non évidents, pas chaque ligne.
- Tester les cas limites : espaces, fichiers absents, arguments vides et permissions insuffisantes.

## Éviter les commandes destructrices

Ne jamais construire une commande à exécuter à partir d'une chaîne non fiable avec `eval`.

Éviter les suppressions trop larges ou les chemins non vérifiés :

```bash
rm -rf "$dossier"
```

Avant une suppression, vérifier que la variable est définie et contient bien le chemin attendu.

## Débogage

```bash
bash -n script.sh   # vérifie la syntaxe sans exécuter
bash -x script.sh   # affiche les commandes exécutées
```

On peut aussi activer le traçage dans le script avec `set -x`, puis le désactiver avec `set +x`.

## Outils de vérification

- **ShellCheck** : détecte de nombreuses erreurs et mauvaises pratiques dans les scripts shell.
- **shfmt** : formate automatiquement les scripts.

Attention : un script Bash doit être exécuté avec Bash. `/bin/sh` peut désigner un autre shell, avec une syntaxe différente.
