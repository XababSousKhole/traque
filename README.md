# TRAQUE : l'appli de chasse à l'homme

Appli Android + iPhone. La position continue d'être envoyée quand le téléphone est **verrouillé** (pas éteint).
Le même fichier `www/index.html` marche aussi en version web (Netlify), mais sans l'envoi écran verrouillé.

## 1. Mettre le projet sur GitHub (une seule fois)

1. Crée un compte sur github.com.
2. Installe **GitHub Desktop** (desktop.github.com) et connecte-toi.
3. Décompresse ce dossier, puis dans GitHub Desktop : *File > Add local repository* > choisis le dossier > *create a repository* > *Publish repository*.
   Décoche **Keep this code private** (dépôt public = compilation gratuite et tes amis peuvent télécharger l'appli).
4. Sur github.com, ouvre ton dépôt > onglet **Actions** : la compilation démarre toute seule (10 à 20 min).
5. Quand c'est vert, va dans **Releases** (colonne de droite) : tu y trouves `TRAQUE-android.apk` et `TRAQUE-iphone.ipa`.

À chaque modification envoyée (bouton *Push origin*), une nouvelle version est compilée.

## 2. Installer sur Android

1. Sur le téléphone, ouvre la page **Releases** du dépôt et télécharge `TRAQUE-android.apk`.
2. Ouvre le fichier et autorise « Installer des applis inconnues » pour ton navigateur.
3. Au premier lancement : autorise la **position** et les **notifications**.
4. Important (Samsung, Xiaomi, Huawei, Oppo...) : *Paramètres > Applications > TRAQUE > Batterie* > **Non restreinte**. Sinon le téléphone peut couper l'appli en poche.

Une notification « TRAQUE : partie en cours » reste affichée pendant le jeu : c'est elle qui permet d'envoyer la position écran éteint.

## 3. Installer sur iPhone (gratuit, avec un PC Windows)

Apple ne permet pas d'installer une appli hors App Store sans passer par un ordinateur.

1. Sur le PC, installe **iTunes** (version du site d'Apple, pas celle du Microsoft Store) et **Sideloadly** (sideloadly.io).
2. Branche l'iPhone en USB, glisse `TRAQUE-iphone.ipa` dans Sideloadly, entre un identifiant Apple (gratuit), clique **Start**.
3. Sur l'iPhone : *Réglages > Général > VPN et gestion de l'appareil* > fais confiance à ton identifiant Apple.
4. iOS 16 et plus : *Réglages > Confidentialité et sécurité > Mode développeur* > activer, puis redémarrer.
5. Au lancement : position **« Toujours »** de préférence, et autorise les notifications.

Limites du gratuit : l'appli expire au bout de **7 jours** (il faut refaire l'étape 2) et chaque iPhone doit passer par un PC.
Pour éviter ça : compte **Apple Developer (99 $/an)**, puis distribution par lien TestFlight (l'appli se met à jour toute seule).

## Pendant la partie

- Tu peux **verrouiller** le téléphone : la position part toujours.
- Ne **ferme pas** l'appli (ne la balaie pas dans les applis récentes), sinon plus rien n'est envoyé.
- Les alertes (sonar, ping précis, chasseur proche, capture) arrivent en **notifications** quand l'écran est éteint.

## Modifier le jeu

Tout le jeu est dans `www/index.html`. Après modification, pousse sur GitHub : l'appli est recompilée.
La clé de signature Android (`android/app/traque.keystore`) est dans le projet pour que les mises à jour s'installent par-dessus l'ancienne version. Ne la change pas.
