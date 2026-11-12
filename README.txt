ATHLETICA 3.4.0 — Fiabilité des données

Contenu : index.html, manifest.webmanifest, sw.js, icon-192.png, icon-512.png, README.txt.

La clé de stockage athletica-v1, les huit sections et toutes les fonctions existantes sont conservées. Aucune donnée n'est migrée ou supprimée : les anciennes sorties restent lues telles quelles.

Corrections :
- enregistrement protégé : si le stockage du navigateur est plein, un message l'indique au lieu d'une perte silencieuse ;
- tracés GPS importés allégés (un point toutes les 3 s, distance au dixième de mètre) ; kilomètres et FC par km calculés avant allègement ; les anciens tracés ne sont pas modifiés ;
- records : le dernier kilomètre incomplet n'est plus compté comme un kilomètre entier ;
- import Decathlon : aperçu avec champs indisponibles, détection de doublons, date à saisir si absente (plus de date du jour par défaut), choix de la paire de chaussures ; FC par km lue dans la feuille Laps ;
- sauvegarde : fusion sans écrasement ou remplacement précédé d'une copie de sécurité téléchargée ; objectif et thème inclus dans le fichier ;
- chaussures : renommer une paire conserve son kilométrage ;
- Réglages : import de sauvegarde, bloc À propos (version, stockage, dernière sauvegarde), rappel de sauvegarde sur l'accueil après 14 jours ;
- service worker : seule une réponse valide est mise en cache ; le module Excel est conservé pour l'usage hors ligne après un premier chargement en ligne ;
- zones tactiles agrandies, marge haute pour l'application installée.

Limite : essais d'interface et d'import avec des fichiers Decathlon réels sur iPhone/iPad à faire. Ne pas effacer les données du navigateur. Faire une sauvegarde JSON avant toute mise à jour.

Installation : remplacer les six fichiers du dépôt GitHub Pages par ceux de ce dossier, après avoir conservé une sauvegarde JSON récente. Ne pas téléverser le ZIP lui-même.
