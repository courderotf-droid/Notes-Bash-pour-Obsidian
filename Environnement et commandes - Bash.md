Bash est un *shell* : il interprète les commandes saisies dans un terminal et peut exécuter des scripts.

## Commandes courantes

| Commande | Fonction |
|---|---|
| `pwd` | Afficher le répertoire courant |
| `ls -la` | Lister les fichiers, y compris cachés |
| `cd chemin` | Changer de répertoire |
| `mkdir dossier` | Créer un répertoire |
| `cp source destination` | Copier |
| `mv source destination` | Déplacer ou renommer |
| `rm fichier` | Supprimer |
| `cat fichier` | Afficher le contenu |
| `less fichier` | Lire un fichier page par page |
| `grep motif fichier` | Rechercher un motif |
| `find chemin -name 'motif'` | Rechercher des fichiers |
| `man commande` | Consulter le manuel |

## Aide et commandes intégrées

- `commande --help` : aide succincte, lorsqu'elle existe.
- `help` : aide sur les commandes intégrées de Bash.
- `type commande` : indique comment Bash interprète une commande.
- `which programme` : localise généralement un exécutable dans le `PATH`.

Certaines commandes, comme `cd`, sont intégrées au shell : elles doivent modifier l'environnement du shell courant.

Voir [[Structure d'un script - Bash]] et [[Redirections et pipelines - Bash]].
