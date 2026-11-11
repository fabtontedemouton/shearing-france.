SHEARING FRANCE — VERSION 4.1

CORRECTIONS
- Mise en page mobile recalculée pour tenir dans la largeur disponible, sans débordement horizontal.
- Cartes, podium, tableaux et statistiques adaptés aux petits écrans.
- Réactivation du registre des compétiteurs (la V4.0 le vidait au démarrage).
- Import des 51 compétiteurs recensés dans l'article public du Dorat 2022.
- Résultats du Dorat 2022 corrigés selon le classement publié.
- Ajout de résultats 2019 et 2026, dont les finales Golden Shears / Championnats du monde, avec temps et points lorsqu'ils sont publiés.
- Les profils sont générés à partir des inscriptions et des résultats archivés; les nationalités non établies restent « à confirmer ».

DONNÉES ET LIMITES
Cette base regroupe les compétiteurs nommément publiés dans les sources consultées et les résultats retrouvés. Elle ne prétend pas être exhaustive pour toutes les compétitions locales, toutes les années ou tous les pays. Les résultats incomplets ne sont pas complétés artificiellement. Les dates à confirmer restent signalées.

FONCTIONNEMENT
Le prototype enregistre les modifications sur l'appareil (localStorage). Les données ne sont pas synchronisées entre plusieurs téléphones. La mise à jour automatique du service worker nécessite une publication sur un hébergement HTTPS stable.

V4.4 : fiches individuelles cliquables, palmarès sourcés pour les compétiteurs dont des informations publiques fiables ont été retrouvées. Les profils sans biographie sourcée affichent les résultats disponibles et signalent les informations manquantes.


V4.5 : import des classements individuels visibles sur le registre officiel ATM pour les circuits 2022, 2023, 2024 et 2025 (16 concours, 255 lignes de résultats). Chaque ligne est rattachée à une compétition, une catégorie, un rang et à la source officielle ATM. La page ATM propose également des PDF détaillés liés par concours; seuls les rangs visibles dans les tableaux HTML ont été importés dans cette version, les temps/points non publiés dans ces tableaux restent vides.


V4.6 : ajout des six places officielles de sélection de l'équipe de France 2026 (machine, forces, tri de laine), reliées aux fiches individuelles et à l'événement dédié. Source : registre des résultats ATM. Les résultats déjà importés des circuits 2022-2025 sont conservés.


V4.7 : ajout des résultats publiés de Martel 2021 (Senior : Gaspard Kicki 1er, Baptiste Arcoutel 2e) et du répertoire complet des 51 participants du Dorat 2022 avec département. Les personnes présentes au concours sans rang publié sont inscrites comme participants, sans résultat inventé. Source Le Dorat : Alliance Élevage; Martel 2021 : La Dépêche.


V4.8 — consolidation : fusion idempotente des archives publiques avec les données locales, reconstruction automatique de l'index des compétiteurs depuis les résultats, suppression des doublons d'archives, sauvegarde automatique des données importées au premier chargement. L'application reste une PWA locale : la publication collective des résultats en ligne nécessite une base de données et un service serveur, non configurés dans ce ZIP. Le service worker et les mises à jour automatiques nécessitent un hébergement HTTPS.


V6.0 : ajout d'un formulaire de création/mise à jour du profil personnel (nom, pays, département/région, club/équipe). Le profil est enregistré localement, ajouté à l'annuaire des compétiteurs et relié aux résultats portant exactement le même nom. Pas encore de comptes sécurisés ni de synchronisation multi-appareils : cela nécessitera le backend central prévu pour la publication collective.


## Mise à jour facile
- Publier le contenu du dossier `shearing-france` sur le même hébergement HTTPS et dans le même dossier que la version précédente.
- Ne pas changer l'adresse de l'application : le service worker détecte les nouveaux fichiers et propose le bouton « Actualiser ».
- La mise à jour de l'application ne supprime pas les données locales du navigateur (`sf_v1`).
- Faire régulièrement une sauvegarde depuis la rubrique Organisation avant une mise à jour importante.
- Les profils et résultats restent enregistrés localement sur l'appareil. La synchronisation entre plusieurs personnes/appareils nécessite encore un serveur et une base de données partagée.


## V6.0 — interface plus intuitive
- Accueil guidé avec raccourcis vers calendrier, résultats, classements et profil.
- Navigation regroupée par usage : découvrir, communauté, participer.
- Menu latéral sur ordinateur et barre de navigation horizontale sur mobile.
- Les rubriques, données, formulaires et fonctions de la V5.0 sont conservés.
- Pour mettre à jour : republier le contenu du dossier `shearing-france` sur le même hébergement HTTPS et à la même adresse. Le service worker V6.0 renouvelle son cache.


## V6.1 — correction du menu
- Libellés de navigation raccourcis pour être lisibles au premier coup d'œil.
- Icônes et textes centrés sur mobile dans une grille de trois colonnes.
- Les libellés peuvent revenir à la ligne : aucune troncature volontaire.
- Pour mettre à jour, remplacer les fichiers de la version hébergée en conservant la même adresse.


## V6.2 — import photo de résultats
- Sélection ou prise de photo depuis le téléphone.
- Reconnaissance OCR français/anglais dans le navigateur via Tesseract.js (connexion Internet requise pour charger le moteur).
- Texte OCR modifiable et lignes de résultats proposées avec champs éditables.
- Création locale du concours si absent, création de fiches compétiteurs manquants et ajout des résultats en provisoire.
- Contrôle humain requis avant validation. La publication partagée exige encore une API et une base de données en ligne avec authentification organisateur.


## V6.3 — fusion intelligente des imports
- Si le concours existe déjà (nom/date et ville compatibles), l'import le retrouve au lieu d'en créer un second.
- Les informations manquantes du concours sont complétées sans remplacer les champs déjà renseignés.
- Les résultats déjà présents sont complétés uniquement dans leurs champs vides (temps, pénalité, rang, points).
- Les compétiteurs et participants manquants sont ajoutés ; les doublons déjà complets sont ignorés.
- En cas de différence entre une donnée importée et une donnée déjà enregistrée, l'existante est conservée et le conflit est signalé.
- Les lignes importées restent provisoires et doivent être vérifiées avant validation.
- Important : cette fusion fonctionne dans les données locales de l'appareil. La synchronisation entre tous les utilisateurs nécessitera la prochaine étape serveur (base de données et comptes).
