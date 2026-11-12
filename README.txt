ATHLETICA 3.3.1 — Apple Fitness Edition

Contenu : index.html, manifest.webmanifest, sw.js, icones 192/512.

Cette version conserve la clé de stockage locale athletica-v1, les huit sections et les fonctions existantes. Le thème clair est présenté par défaut ; le thème sombre reste disponible dans Réglages.

Corrections de fiabilité :
- dates GPX conservées selon le fuseau local de l'activité ;
- dates Excel/CSV interprétées sans décalage UTC pour les dates sans heure ;
- calcul des semaines avec des clés calendaires locales ;
- moyennes de fréquence cardiaque par kilomètre calculées à partir des échantillons réellement présents dans chaque segment ;
- service worker limité aux caches ATHLETICA, sans supprimer les caches d'autres applications ;
- navigation réseau prioritaire avec repli hors ligne sur la page mise en cache.

Contrôles effectués : syntaxe JavaScript, analyse HTML, unicité des identifiants, validité JSON du manifeste, tests de dates dans le fuseau Asia/Jerusalem et intégrité de l'archive ZIP.

Limite : des essais d'interface et d'import avec des fichiers Decathlon réels sur iPhone/iPad restent nécessaires. Ne pas effacer les données du navigateur. Faire une sauvegarde JSON avant toute mise à jour.

Installation : remplacer les six fichiers du dépôt GitHub Pages par ceux de ce dossier, après avoir conservé une sauvegarde JSON récente. Ne pas téléverser le ZIP lui-même.
