ATHLETICA — Version 2.0

INSTALLATION / MISE À JOUR
1. Décompresser ce ZIP.
2. Ouvrir le dépôt GitHub Pages Athletica-.
3. Remplacer les fichiers existants par ceux du dossier athletica (index.html, manifest.webmanifest, sw.js et icônes).
4. Commit les modifications.
5. Ouvrir le site dans Safari et actualiser. Si l’ancienne version reste affichée, fermer l’application installée puis rouvrir le site.

NOUVEAUTÉS COURSE À PIED
- Saisie de la durée au format mm:ss ou h:mm:ss.
- Heure de départ, FC moyenne, calories, météo, température, chaussures.
- Échauffement (durée et distance).
- Douleur au genou sur 10 et localisation.
- Temps de passage par kilomètre et FC moyenne par kilomètre.
- Statistiques de distance, temps, nombre de sorties et calories par semaine ou par mois.
- Filtres par période, chaussures et type de séance.
- Records 1, 3, 5, 10 km et semi-marathon. Les records exacts sur segments glissants sont calculés à partir des tracés GPX horodatés. La saisie manuelle des splits ne permet de calculer que les segments alignés sur les kilomètres saisis.
- Planning des prochaines séances, édition et transfert d’une séance planifiée vers le formulaire de course.
- Modification et suppression des courses.
- Import de fichiers GPX et Excel Decathlon Coach (.xls / .xlsx).

IMPORT DECATHLON COACH
Sur le site Decathlon Coach, ouvre une activité puis utilise Actions > Exporter en Excel, ou l’option d’export GPX. Dans ATHLETICA, choisis le fichier, analyse-le, vérifie l’aperçu et confirme l’ajout.
L’import Excel utilise la bibliothèque SheetJS chargée depuis un CDN et nécessite une connexion Internet au moment de l’import. Le GPX est traité directement dans le navigateur. Le format Excel de Decathlon contient plusieurs feuilles (Export, Résumé, Laps) ; les champs reconnus sont préremplis, mais il faut vérifier les valeurs importées car les variantes d’export peuvent différer.

DONNÉES
Les données sont conservées localement sur l’appareil dans le navigateur (localStorage). Il n’y a pas de synchronisation cloud. Utilise régulièrement Exporter pour sauvegarder tes données JSON. La mise à jour de l’application ne supprime pas les données locales existantes.
