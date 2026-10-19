# CCAG-T 2016 — application Android

Application hors ligne de consultation du CCAG-T marocain de 2016 (décret n° 2-14-394).

## Contenu de l'application
- **Accueil** : présentation du décret, les 9 chapitres, parcours d'un marché en délais.
- **Chapitres** : synthèse, points clés et liste des articles.
- **Articles** : recherche plein texte dans les 84 articles ; chaque article affiche ses renvois cliquables, les articles qui le citent, et des boutons précédent / suivant.
- **Délais & taux** : tableaux des taux, des délais et points de vigilance.
- **Favoris** : touchez l'étoile d'un article pour le retrouver ici.
- Mode sombre automatique, bouton Retour du téléphone géré, aucun accès internet requis.

## Obtenir l'APK sans rien installer (GitHub, gratuit)
1. Créez un compte sur github.com puis un nouveau dépôt (**New repository**).
2. Sur la page du dépôt : **Add file → Upload files**, glissez **le contenu** du dossier `CCAGT-Android` (y compris le dossier `.github`), puis **Commit changes**.
   Astuce : le dossier `.github` est masqué sur certains ordinateurs ; activez l'affichage des fichiers cachés avant de glisser.
3. Ouvrez l'onglet **Actions** : la compilation démarre seule (environ 5 minutes).
4. Une fois la coche verte affichée, ouvrez l'exécution et téléchargez **CCAGT-2016-apk** (fichier zip contenant l'APK).
5. Copiez l'APK sur le téléphone, ouvrez-le et autorisez l'installation depuis cette source.

## Compiler avec Android Studio
1. **File → Open** et choisissez le dossier `CCAGT-Android`.
2. Laissez Android Studio synchroniser (il télécharge le SDK et Gradle au premier lancement).
3. **Build → Build App Bundle(s) / APK(s) → Build APK(s)**.
   L'APK se trouve dans `app/build/outputs/apk/`.

En ligne de commande, avec le SDK Android installé : `./gradlew assembleRelease`.

## Modifier le contenu
Tout le contenu et l'interface sont dans `app/src/main/assets/index.html`
(données en tête du script : `CH` chapitres, `A` articles, `TAUX`, `DEL`, `VIG`).
Dans les textes, `[[55]]` crée un lien vers l'article 55.

## Publication sur Google Play
L'APK release est signé avec la clé de développement, suffisante pour l'installer directement.
Pour Google Play, créez votre propre clé de signature (Build → Generate Signed Bundle) et augmentez `versionCode` à chaque mise à jour.

## Avertissement
Résumé d'analyse du texte publié au Bulletin officiel n° 6470 du 2 juin 2016, seule référence juridique.
Le décret 2-12-349 cité par le CCAG-T a été remplacé par le décret 2-22-431 (2023) : vérifiez les correspondances.
