SHEARING FRANCE — PROJET ANDROID (V6.1)

PRÉREQUIS
- Un ordinateur Windows, macOS ou Linux.
- Node.js LTS installé.
- Android Studio installé avec Android SDK.
- Une connexion Internet pour télécharger les dépendances Android.

ÉTAPES
1. Décompresser ce dossier sur l'ordinateur.
2. Ouvrir un terminal / Invite de commandes dans le dossier Shearing-France-Android.
3. Exécuter :
   npm install
   npx cap add android
   npx cap sync android
   npx cap open android
4. Android Studio s'ouvre. Attendre la fin de la synchronisation Gradle.
5. Pour tester sur un téléphone : activer les Options développeur et le Débogage USB, brancher le téléphone, puis cliquer Run ▶.
6. Pour générer un APK de test : Android Studio > Build > Build Bundle(s) / APK(s) > Build APK(s).
7. Pour une version distribuable : Build > Generate Signed Bundle / APK. Choisir APK pour installation directe ou Android App Bundle (AAB) pour Google Play. Créer et sauvegarder la clé de signature en lieu sûr.

MISE À JOUR DE L'APPLICATION
Cette version embarque les fichiers web dans l'application. Pour publier une nouvelle version :
- remplacer les fichiers du dossier www par ceux de la nouvelle version du site;
- incrémenter la version Android dans Android Studio (versionCode et versionName);
- exécuter npx cap sync android;
- reconstruire et signer un nouvel APK/AAB.
Les données enregistrées dans le stockage local de l'application sont normalement conservées lors d'une mise à jour signée avec la même clé et le même applicationId. Ne pas désinstaller l'ancienne version pour mettre à jour.

IMPORTANT
- Ce projet est un conteneur Android Capacitor prêt à générer le dossier Android.
- Le dossier Android n'est pas inclus : il est créé par « npx cap add android ».
- Le code et les données de Shearing France restent ceux de la V6.1. Les données locales ne sont pas synchronisées entre utilisateurs/appareils.
- Les liens externes et les notifications doivent être testés sur appareil réel avant diffusion.
