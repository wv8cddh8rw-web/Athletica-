ATHLETICA 3.7.0 — Tableau de bord de progression musculaire

Contenu : index.html, manifest.webmanifest, sw.js, icon-192.png, icon-512.png, README.txt.

Nouveauté : rubrique « Calories » avec total hebdomadaire, total mensuel, moyenne par sortie, graphique des 8 dernières semaines et détail des 20 dernières sorties.

Les totaux utilisent uniquement les calories réellement renseignées dans les activités (import Decathlon Coach ou saisie manuelle). Les séances sans calories restent « Non renseigné » et ne sont pas assimilées à 0 kcal. La rubrique mesure les calories de séance connues, pas le déficit énergétique global ni une perte de graisse.

Compatibilité : la clé localStorage athletica-v1 est conservée. Les activités et données existantes ne sont pas supprimées ni migrées. Toutes les rubriques précédentes sont conservées ; une rubrique Calories est ajoutée.

Avant mise à jour : exporter une sauvegarde JSON et conserver précieusement athletica-sauvegarde.json.

Installation : décompresser le ZIP puis déposer les six fichiers de ce dossier à la racine du dépôt GitHub Pages, en remplaçant les fichiers correspondants. Ne pas téléverser le ZIP lui-même. La publication n'est effective qu'après le commit et le déploiement GitHub Pages.

Tests : vérifier le JavaScript, le manifeste et l'intégrité du ZIP. Faire ensuite un essai réel sur iPhone/iPad et vérifier que les activités avec calories apparaissent correctement.


ATHLETICA 3.5.1
- L’historique des courses est désormais trié automatiquement de la plus récente à la plus ancienne, selon la date puis l’heure de départ.
- Le tri est réappliqué après ajout, import, modification ou suppression. Les courses sans heure sont placées avant celles avec une heure le même jour.


Version 3.7.0 — Tableau de bord musculation : records personnels par exercice, séries validées par groupe musculaire sur les 7 derniers jours, progression hebdomadaire sur 8 semaines et amélioration des statistiques par exercice. La clé localStorage athletica-v1 est conservée pour préserver les données existantes.

Les statistiques reposent sur les séries validées. Le volume musculaire est compté en nombre de séries ; les charges ne sont pas additionnées entre haltères, machines et poids du corps car ces valeurs ne sont pas directement comparables.
