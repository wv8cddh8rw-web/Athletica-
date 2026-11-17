ATHLETICA 3.8.0 — Refonte Musculation, Progression et personnalisation

Contenu : index.html, manifest.webmanifest, sw.js, icon-192.png, icon-512.png, README.txt.

NOUVEAUTÉS 3.8.0

MUSCULATION
- Les répétitions et charges de la dernière séance connue sont préremplies exercice par exercice au démarrage d'une séance.
- Les séries restent modifiables et cochables une par une.
- Ajout, suppression et réorganisation des séries pendant une séance.
- Temps de repos modifiable directement dans la séance ; le minuteur démarre automatiquement lorsqu'une série est validée.
- Affichage de la dernière performance sous chaque exercice et comparaison indicative en kg/répétitions.
- Historique des performances regroupé par exercice. Les séries identiques sont regroupées visuellement.
- Graphique de progression par exercice : seules les séries de 8 répétitions ou plus alimentent la courbe de charge.
- L'ancien journal de séries n'est plus affiché. Les données historiques restent conservées et sont toujours utilisées pour reconstituer les performances.
- Les séances et séries validées sont conservées dans les structures existantes gymSessions et gym ; elles ne sont pas fusionnées ni supprimées.

ACCUEIL ET OBJECTIFS
- Compteur de séances de musculation sur la semaine en cours.
- Les semaines commencent désormais le dimanche dans les statistiques et graphiques hebdomadaires.
- La dernière course affiche distance, allure et durée totale.
- Temps total de course de la semaine à la place de l'allure moyenne.
- Objectifs mensuels multiples : séances totales, course, musculation, distance courue ou temps de course. Ajout, modification et suppression.
- Phrases de motivation quotidiennes, stables pendant la journée, avec possibilité d'ajouter, modifier et supprimer des phrases.

PROGRESSION
- La page Historique devient Progression.
- Régularité, course, musculation, records personnels et comparaison avec la période précédente.
- Filtres Mois, 3 mois et Année.
- Les records de course 1/3/5/10 km s'appuient uniquement sur les traces GPS ou splits disponibles.

FONDS D'ÉCRAN
- Sélection indépendante par page, ou retour au fond classique.
- Quatre catégories uniquement, avec deux photographies par catégorie : football (moments iconiques de Maradona), athlétisme (Usain Bolt), course (marathon), musculation (haltérophilie).
- Photographies hébergées sur Wikimedia Commons ; crédits et liens de licence affichés dans Réglages. Une connexion internet est nécessaire pour charger les photos.

COMPATIBILITÉ ET DONNÉES
- La clé localStorage athletica-v1 est conservée.
- Aucune séance, série, activité, chaussure, mensuration ou programme n'est supprimé ou migré destructivement.
- Les anciennes données gym et gymSessions sont conservées séparément ; les fonctions de dédoublonnage existantes continuent de les rapprocher à l'affichage.
- Les préférences et objectifs de cette version sont inclus dans les nouvelles sauvegardes JSON.
- Aucun serveur, abonnement ou service externe de synchronisation n'est requis.

AVANT MISE À JOUR
1. Exporter une sauvegarde JSON depuis ATHLETICA.
2. Conserver le fichier athletica-sauvegarde.json dans un emplacement sûr.
3. Décompresser ce ZIP et téléverser les six fichiers du dossier athletica-3-8-0 à la racine du dépôt GitHub Pages, en remplaçant les fichiers correspondants. Ne pas téléverser le ZIP lui-même.
4. Commit/push puis attendre le déploiement GitHub Pages.
5. Vérifier l'application sur iPhone/iPad. Ne pas effacer Safari ni le stockage local.

TESTS EFFECTUÉS
- Intégrité du ZIP source 3.7.0.
- Vérification syntaxique JavaScript avec Node.js.
- Contrôle de conservation de la clé localStorage athletica-v1 et des structures de données.
- Les tests interactifs complets sur iPhone/iPad et import réel restent à effectuer après déploiement.
