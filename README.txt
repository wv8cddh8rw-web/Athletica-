ATHLETICA 3.8.2 — Import FIT contrôlé, mesures individuelles et archivage complet

Contenu : index.html, manifest.webmanifest, sw.js, icon-192.png, icon-512.png, README.txt.

NOUVEAUTÉS 3.8.0 CONSERVÉES + IMPORT FIT 3.8.2

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
3. Décompresser ce ZIP et téléverser les six fichiers du dossier athletica-3-8-2 à la racine du dépôt GitHub Pages, en remplaçant les fichiers correspondants. Ne pas téléverser le ZIP lui-même.
4. Commit/push puis attendre le déploiement GitHub Pages.
5. Vérifier l'application sur iPhone/iPad. Ne pas effacer Safari ni le stockage local.

TESTS EFFECTUÉS
- Intégrité du ZIP source 3.7.0.
- Vérification syntaxique JavaScript avec Node.js.
- Contrôle de conservation de la clé localStorage athletica-v1 et des structures de données.
- Les tests interactifs complets sur iPhone/iPad et import réel restent à effectuer après déploiement.


IMPORT D'ACTIVITÉS — 3.8.2
- Import de fichiers .FIT uniquement dans le module d'activités. GPX, TCX, Excel, CSV et XML ne sont plus acceptés par cet importeur.
- Décodage avec le SDK JavaScript officiel Garmin FIT, version épinglée 21.221.0.
- Contrôle du type FIT, de la longueur déclarée et des sommes de contrôle avant lecture/enregistrement.
- Refus d'un fichier corrompu, incomplet, d'un sport non course ou d'un fichier multi-session qui risquerait de mélanger les activités. Si les horodatages ou distances ne sont pas monotones, les splits sont désactivés plutôt que reconstruits de manière hasardeuse.
- Le résumé FIT (distance, temps actif/écoulé, FC moyenne/maximale, calories, dénivelé, vitesses, tours, fabricant/produit) est conservé lorsqu'il existe. Les points horodatés/distances exploitables sont intégrés à la trace.
- Les splits kilométriques sont reconstruits uniquement quand des distances cumulées et horodatages existent. Les champs absents restent non renseignés ; aucun zéro ou valeur estimée ne les remplace.
- Le fichier FIT n'est pas réécrit. Son empreinte SHA-256, son CRC, sa taille et son nom sont conservés dans les détails de la séance pour repérer les réimports à l'identique.
- L'import affiche un aperçu avant validation. Une empreinte identique est bloquée ; une activité proche déclenche une confirmation.
- En cas d'échec du stockage, la nouvelle activité est retirée de la mémoire et aucune séance déjà enregistrée n'est remplacée.
- Le décodeur Garmin est épinglé à une version précise et chargé dynamiquement depuis le CDN ESM. Le Service Worker ne peut pas mettre ce module cross-origin en cache ; une connexion Internet est nécessaire pour le charger si le cache HTTP du navigateur ne le possède pas déjà.

PROTECTION DES DONNÉES
- La clé localStorage athletica-v1 est inchangée. Aucune migration destructive n'est effectuée.
- Les anciennes activités, leurs traces, leurs splits, les programmes, les séances et les séries de musculation restent inchangés.
- Une sauvegarde JSON avant mise à jour est obligatoire par précaution. Le code ne peut pas garantir l'absence absolue de bogue sur chaque fichier FIT ou appareil : les tests réels avec tes fichiers FIT et sur iPhone/iPad restent nécessaires avant de considérer l'importeur validé en production.


CORRECTIONS DE L'IMPORT FIT — 3.8.2
- FC moyenne utilisée dans ATHLETICA : moyenne arithmétique des valeurs heartRate individuelles valides (30–240 bpm) des messages record. Si aucun point FC n'est présent, repli sur la valeur de résumé FIT, avec la provenance conservée.
- FC maximale utilisée : maximum des valeurs heartRate individuelles valides ; la FC max du résumé FIT reste conservée séparément.
- Le résumé FIT original n'est jamais écrasé : moyenne/maximale de session, durée, distance, calories, dénivelé et autres champs restent dans le message session original archivé.
- Tous les messages décodés du FIT sont archivés dans fitData.messages (record, session, lap, activity, fileId et autres types présents), avec les champs inconnus retournés par le décodeur. Les horodatages sont sérialisés en ISO.
- Tous les points de trace exploitables sont conservés dans track ; aucune réduction à un point toutes les 3 secondes. Les messages record d'origine sont également conservés intégralement dans l'archive des messages.
- Les splits kilométriques complets sont calculés à partir des distances cumulées et horodatages des records, avec les horodatages de début/fin de session lorsqu'ils sont présents. Le reliquat final est affiché séparément comme segment partiel (il n'est jamais présenté comme un kilomètre complet). La FC par split est calculée selon les horodatages et inclut les records FC même lorsqu'un record ne contient pas de distance. En l'absence de données cohérentes, les splits restent vides plutôt que d'être estimés.
- Seuls les FIT de 256 Ko ou moins sont acceptés, afin que le fichier original complet soit conservé octet pour octet en base64 dans fitData.originalFileBase64 et reste présent dans la sauvegarde JSON. Les fichiers plus volumineux sont refusés sans modifier les données ; il faut les conserver séparément et produire un export FIT plus léger.
- Le Service Worker ne prétend plus mettre en cache le décodeur CDN cross-origin. Le premier décodage FIT nécessite une connexion pour charger le SDK Garmin épinglé ; si le chargement échoue, l'import est refusé sans modifier les données.
- Clé localStorage athletica-v1 conservée. Sauvegarde JSON et fusion existantes compatibles.

VALIDATION DE RÉFÉRENCE DU FICHIER FOURNI (FIT Decathlon Coach du 18/11/2026)
- Taille : 14 956 octets ; en-tête FIT valide ; taille déclarée cohérente ; CRC d'en-tête et CRC final vérifiés.
- 1 session, 1 lap, 565 messages record, 1 fileId et 1 activity.
- Distance de session : 6 351 m (6,351 km). Durée active et écoulée : 2 129 s (35 min 29 s).
- Calories : 385 kcal. Dénivelé positif : 43 m ; négatif : 37 m.
- 428 mesures de fréquence cardiaque individuelles valides : moyenne arithmétique exacte 171,411 bpm (affichage arrondi 171 bpm) ; maximum individuel 209 bpm.
- Valeurs du résumé FIT conservées séparément : moyenne 163 bpm, maximum 205 bpm. L'application affiche 171/209 car cela correspond aux mesures individuelles et à la valeur 171 affichée par Decathlon Coach sur l'iPhone.
- 161 positions GPS ; 421 points avec distance cumulée dans la trace ; les 565 messages record sont conservés dans l’archive complète. Les coordonnées de la trace sont converties des semicircles FIT en degrés, tandis que les valeurs originales sont également conservées.
- Le calcul pondéré dans le temps donne environ 171,59 bpm ; il est archivé séparément à titre de contrôle, mais n'est pas utilisé comme moyenne affichée afin de reproduire la moyenne de points affichée par Decathlon Coach.

LIMITES DE VALIDATION
- Le fichier FIT fourni a été contrôlé indépendamment au niveau binaire (en-tête, taille et CRC) et ses valeurs ont été extraites pour vérifier les règles de mapping. Le décodage dans le navigateur doit encore être testé sur iPhone/iPad avec le SDK chargé, puis les valeurs de l'aperçu comparées à Decathlon Coach avant déploiement.
- Aucune application ne peut garantir l'absence absolue de bogue sur tous les FIT, appareils et profils de champs développeur. Si le SDK renvoie une erreur ou le stockage local échoue, l'import est arrêté et aucune séance existante n'est modifiée.

CORRECTION COMPATIBILITÉ GARMIN SDK
- Les messages sont lus sous les clés officielles du SDK : sessionMesgs, recordMesgs, lapMesgs, fileIdMesgs et activityMesgs (et non sous des noms abrégés).
- Le SDK Garmin documente le regroupement des messages par type et les clés profile correspondantes ; les champs positionLat/positionLong sont des semicircles et sont convertis en degrés uniquement pour la trace de l’application. Les messages FIT originaux et le fichier binaire préservé restent inchangés.
- Les fichiers contenant plus d’une session sont refusés, y compris lorsqu’un message activity annonce numSessions supérieur à 1.
