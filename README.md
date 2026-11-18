# Toppop Run — appli Android

Ce dépôt fabrique automatiquement l'appli Android de **Toppop Run** (https://toppop-run.netlify.app) pour Google Play, avec Bubblewrap (l'outil officiel de Google).

## Fabriquer l'appli
1. Onglet **Actions** → « Fabriquer l'appli Android » → **Run workflow**.
2. Attendre 5 à 10 minutes (coche verte).
3. Ouvrir l'exécution → section **Artifacts** → télécharger **toppop-run-android**.
   - `app-release-bundle.aab` : le fichier à envoyer sur Google Play Console.
   - `app-release-signed.apk` : pour tester sur un téléphone Android.
   - `assetlinks.json` : à mettre dans `.well-known/` du site.

## Nouvelle version
Augmenter `appVersionCode` (+1) et `appVersion` dans `twa-manifest.json`, puis relancer.

## Secrets nécessaires (Settings → Secrets and variables → Actions)
- `KEYSTORE_BASE64` : la clé de signature encodée en base64
- `KEYSTORE_PASSWORD` et `KEY_PASSWORD` : les mots de passe (voir signing-key-info.txt, gardé hors du dépôt)
