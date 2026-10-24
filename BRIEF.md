# Surprise : brief du projet

## En une phrase

Une mini-appli web pour organiser une surprise pour quelqu'un d'autre (week-end, déclaration, dîner, chasse au trésor) et la lui faire découvrir étape par étape, au bon moment, via un simple lien.

## Idée de départ et recadrage

L'idée initiale était une appli de voyages surprise avec budget prédéfini : itinéraire, billets et hôtels donnés au compte-gouttes à la personne qui se laisse emmener.

Ce marché est déjà bien occupé (voir plus bas) et exige de réserver et vendre des voyages. Le projet a donc été recadré :

- **Ce que l'appli ne fait pas :** organiser le voyage, réserver, encaisser. L'utilisateur s'en charge lui-même.
- **Ce qu'elle fait :** la **mise en scène** de la surprise, c'est-à-dire la manière dont l'information est livrée à la personne surprise.

## Utilisateurs

- **L'organisateur :** il écrit le scénario, choisit comment chaque étape se débloque, puis envoie un lien.
- **La personne surprise :** elle ouvre le lien sur son téléphone et découvre les étapes au fil du temps. Rien à installer ni à créer comme compte.

## Cas d'usage

- Emmener quelqu'un quelque part sans rien dire (week-end, voyage, sortie).
- Faire une déclaration ou une demande en mariage en plusieurs temps.
- Dîner ou soirée surprise, avec tenue et horaires.
- Chasse au trésor ou cadeau d'anniversaire à retrouver grâce à des indices.

## Fonctionnement (version 1)

1. L'organisateur renseigne le prénom et un message d'accueil.
2. Il part d'un modèle (week-end surprise, déclaration, dîner, chasse au trésor) ou écrit ses propres étapes.
3. Chaque étape a un titre, un message, un lieu ou lien facultatif et un teaser affiché avant le déblocage.
4. Chaque étape se débloque de l'une de ces trois façons :
   - **au toucher** : la personne appuie sur « Dévoiler » ;
   - **à une date et heure précises** : compte à rebours, selon l'heure de son appareil ;
   - **avec un mot de code** : donné par l'organisateur au bon moment (accents et majuscules ignorés).
5. L'appli génère un lien qui contient tout le scénario. Un bouton « Aperçu » montre exactement ce que verra la personne.
6. La personne ouvre le lien : page d'accueil, puis cartes qui se dévoilent une à une, confettis à la dernière étape. Sa progression est conservée sur son téléphone.

## Choix techniques

- Un seul fichier `index.html`, sans serveur, sans compte, sans base de données.
- Le scénario est compressé dans l'adresse du lien (partie après `#`).
- Hébergement gratuit sur GitHub Pages.
- Fonctionne sur téléphone et peut être ajouté à l'écran d'accueil.
- Le contenu saisi est toujours affiché comme du texte (pas de HTML exécuté), et les liens `javascript:` sont neutralisés.

## Confidentialité

- Le dépôt est public, mais le contenu des surprises n'y figure pas : il vit uniquement dans les liens générés.
- Quiconque possède le lien peut en lire le contenu. À envoyer uniquement à la personne concernée.
- Ne jamais écrire d'informations sensibles dans le code du dépôt.
- La page demande aux moteurs de recherche de ne pas l'indexer.

## Limites connues

- Pas de photos ni de vidéos.
- Pas de déclenchement à distance en direct : l'organisateur ne peut pas ouvrir une étape depuis son propre téléphone.
- Les étapes à heure précise reposent sur l'horloge de l'appareil de la personne : elle pourrait la modifier pour tricher.
- La progression est liée à un seul appareil et à un seul navigateur.
- Les liens très longs peuvent poser problème par SMS : préférer une messagerie.

## Idées pour la suite

- **Photos et musique** dans les étapes.
- **Déclenchement en direct** par l'organisateur, via un petit service en ligne gratuit.
- **Notification** à l'heure d'une étape.
- **Code QR** à imprimer et à cacher (chasse au trésor).
- **Carte** avec le parcours, dévoilé étape par étape.
- **Thèmes visuels** selon l'occasion (anniversaire, romantique, voyage).
- **Gabarit de budget** et suivi des réservations pour l'organisateur (sans paiement dans l'appli).

## Marché (repéré en octobre 2026)

Le voyage surprise commercial existe déjà ; ce projet ne le concurrence pas directement car il ne vend aucun voyage.

| Acteur | Ce qu'il propose |
|---|---|
| MyLittleTrip | Abonnement : 3 voyages surprise par an (3 jours / 2 nuits), transport et hébergement inclus, destination révélée le jour J, appli avec indices progressifs, dès 59 €/mois |
| Waynabox | Séjours mystère à prix fixe, vol et hôtel inclus, à partir d'environ 150 € par personne |
| FlyKube, Cap Mystère, Surprisit | Même principe : destination secrète jusqu'au dernier moment |
| Journee | Voyages mystère sur mesure, a levé 1,75 M£ en 2022 |
| Coup de Tête | Appli qui tire au sort une destination en train selon durée et budget, avec réservation SNCF |

Ce que ces services ne couvrent pas, et que ce projet vise : la **livraison de la surprise** pour des scénarios que l'organisateur a lui-même préparés et réservés, quelle que soit l'occasion (pas seulement un voyage).

## Statut

- Version 1 fonctionnelle, testée sur un écran de téléphone simulé : création du scénario, lien, aperçu, compte à rebours, mot de code, persistance de la progression, lien invalide et protection contre l'injection de contenu.
- À valider sur de vrais téléphones (iPhone et Android) avant un premier usage réel.
