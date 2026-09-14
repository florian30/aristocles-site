---
layout: page
title: "Politique de confidentialité — Aristocles (version bêta)"
permalink: /confidentialite/
---

> **TL;DR** — Aristocles est une application de tutorat vocal pour les enfants du CE1 au
> CM2. **Le compte est celui du parent** ; l'enfant n'a pas de compte. Pour fonctionner,
> l'app envoie la **voix** de l'enfant (pour la transcrire), les **photos** de son cahier
> (pour lire l'énoncé) et le **texte des échanges** avec Ari à des services d'intelligence
> artificielle situés aux **États-Unis** (OpenAI, OpenRouter, Anthropic). Tout le reste est
> stocké chez Supabase, à **Paris**. **Aucune publicité, aucun pistage, aucune revente.** La
> voix n'est jamais conservée ; les photos sont effacées au bout de **90 jours** ; le texte
> des échanges est conservé tant que le compte existe. Vous pouvez demander la suppression
> du compte et des données à tout moment en nous écrivant.
>
> Version 0.2 (bêta), datée du 14 septembre 2026.

---

## 1. Qui est responsable de vos données

Aristocles est édité, en phase bêta, par son fondateur. Contact pour toute question ou
demande sur vos données : bonjour@aristocles.fr. Les coordonnées complètes de l'éditeur
seront ajoutées avant l'ouverture publique.

C'est à cette adresse que vous pouvez exercer vos droits (section 7) et poser vos questions.

## 2. À qui s'adresse Aristocles

Aristocles est conçu pour des **enfants scolarisés du CE1 au CM2**, qui l'utilisent **sous
le compte de leur parent**, sur l'appareil du parent. Il n'existe **pas de compte enfant** :
c'est le parent qui crée le compte, qui crée le profil de l'enfant, et qui consent au
traitement des données de l'enfant. L'espace parent est protégé par un **code PIN à
quatre chiffres**.

Pendant la phase bêta, l'application est diffusée à un cercle restreint de familles, par
TestFlight (iPhone) et par la piste de test interne de Google Play (Android).

## 3. Quelles données nous traitons, et pourquoi

### 3.1 Le compte parent

| Donnée | Pourquoi | Détail |
|---|---|---|
| Adresse e-mail | Vous identifier et vous permettre de vous connecter | Gérée par le service d'authentification de Supabase. |
| Mot de passe | Protéger votre compte | Jamais stocké en clair (haché par Supabase Auth). Longueur minimale : 6 caractères. |
| Code PIN parent | Protéger l'espace parent (bilans, réglages) contre l'enfant | Quatre chiffres. Jamais stocké en clair : seule une empreinte (Argon2id, avec sel) est conservée. Jamais écrit dans les journaux. Verrouillage après plusieurs essais ratés. |
| Date de consentement | Garder la preuve que vous avez accepté ce cadre | Horodatage posé par le serveur au moment où le PIN est créé. |
| Compteur d'usage journalier | Plafonner le nombre d'appels aux services d'IA par famille et par jour | Un compteur, sans contenu. |

Le formulaire d'inscription ne demande que l'e-mail et le mot de passe. Aucun nom, aucune
adresse postale, aucun numéro de téléphone du parent n'est demandé.

### 3.2 Le profil de l'enfant

| Donnée | Pourquoi | Obligatoire ? |
|---|---|---|
| Prénom | Pour qu'Ari s'adresse à l'enfant par son prénom | Oui |
| Genre (fille / garçon / autre / non précisé) | Pour accorder correctement les phrases d'Ari | Oui |
| Classe (CE1, CE2, CM1 ou CM2) | Pour adapter le niveau des exercices et du langage | Oui |
| École | Contexte, posé à l'enfant par Ari lors de la première rencontre | Non |
| Prénom du maître ou de la maîtresse | Contexte, posé à l'enfant lors de la première rencontre | Non |
| Matières actives, notions à travailler en priorité | Réglages choisis par le parent | Non |

Nous ne demandons **ni date de naissance, ni photo, ni adresse de l'enfant**. Ce que
l'enfant dit aimer faire en dehors de l'école (ses activités) lui est demandé lors de la
première rencontre, mais **n'est pas enregistré** à ce jour.

### 3.3 La voix de l'enfant

L'enfant parle à Ari en **appuyant sur un bouton** (push-to-talk) : le micro n'écoute que
pendant qu'il est enfoncé. L'enregistrement est envoyé à notre serveur, qui le transmet à
**OpenAI (service Whisper)** pour le transformer en texte, en français.

- **L'enregistrement audio n'est conservé nulle part** : ni sur nos serveurs, ni dans une
  base de données. Sur le téléphone, le fichier ne vit que dans un dossier temporaire.
- **Le texte obtenu est conservé** dans l'historique de la séance (voir 3.5).
- Nos journaux techniques ne gardent que la durée de l'enregistrement et sa taille, jamais
  son contenu ni sa transcription.

À l'inverse, la voix d'Ari est **fabriquée** à partir de son texte par **OpenAI (synthèse
vocale)**. Le fichier audio produit n'est pas stocké sur nos serveurs ; il est mis en cache
dans un dossier temporaire du téléphone.

### 3.4 Les photos du cahier

En mode Devoirs et en Dictée, l'enfant peut **photographier l'énoncé** ou sa dictée. La
photo est stockée dans un espace privé de Supabase, rangé par enfant, et lue par un modèle
d'IA (via OpenRouter, puis Anthropic Claude ; en mode Devoirs, également OpenAI) qui en
extrait le texte : consignes à faire, ou mots écrits par l'enfant.

- Le stockage est **privé** : seul le parent connecté peut relire les photos de son enfant.
  Limite : 5 Mo par photo, formats JPEG, PNG et HEIC.
- **Les photos sont effacées automatiquement au bout de 90 jours** (purge hebdomadaire,
  le dimanche à 4 h du matin). Le fait qu'une photo a été prise (date, écran) reste dans
  l'historique, sans l'image.
- Le **texte extrait** de la photo est conservé dans l'historique de la séance.
- L'application n'accède **pas** à la galerie de photos du téléphone : seulement à l'appareil
  photo, au moment de la prise de vue.

### 3.5 Les échanges avec Ari et le travail de l'enfant

Tout ce que l'enfant dit à Ari (transcrit en texte), et tout ce qu'Ari lui répond, est
conservé dans l'**historique de la séance**. Cet historique est rattaché à l'enfant, et donc
à votre compte. Il sert à :

- permettre à Ari de suivre le fil de la conversation pendant la séance ;
- produire, à la fin de chaque écran, une **synthèse rédigée** de ce que l'enfant a fait ;
- produire les **bilans** qui vous sont destinés (quotidiens et hebdomadaires) ;
- alimenter, sur demande, la conversation « Parler à Ari » de l'espace parent.

Sont aussi conservés : les exercices résolus et leur issue, les dictées (texte de référence,
mots cibles, écarts constatés, et l'enregistrement audio de la dictée lue par Ari), les
devoirs datés, le « pouce » que l'enfant donne à la fin d'un écran, et les conversations
entre **vous** et Ari dans l'espace parent.

Chaque appel à un modèle d'IA reçoit le **prénom** et la **classe** de l'enfant, ainsi que
les consignes du devoir en cours : c'est ce qui permet à Ari de parler à l'enfant et non à un
inconnu.

### 3.6 Les souvenirs pédagogiques

Pour qu'Ari s'améliore d'une séance à l'autre, nous conservons par enfant :

- un **état de maîtrise par notion** (jamais vue, fragile, en cours, acquise…), mis à jour à
  la fin des séances ;
- un **lexique de dictée** : les mots sur lesquels l'enfant bute, et combien de fois ;
- un **portrait** (intérêts, préférences pédagogiques, contexte personnel) destiné à être
  extrait automatiquement des synthèses de séance. **Cette extraction automatique est
  désactivée à ce jour** : le portrait reste vide tant qu'elle ne l'est pas.

Ces souvenirs ne sont **pas** injectés dans les conversations d'Ari avec l'enfant ; ils
servent aux bilans et à la conversation parent.

### 3.7 Les données techniques

| Donnée | Ce qu'elle contient | Ce qu'elle ne contient jamais |
|---|---|---|
| Journal des appels d'IA | Rôle (tuteur, lecture de photo…), modèle utilisé, durée, nombre de jetons, coût estimé, succès ou échec, identifiant de l'enfant, identifiants de séance et d'écran | Le texte envoyé, le texte reçu, le prénom |
| Événements d'usage | Type d'événement (début de tour, fin d'écran…), numéro de tour, écran concerné, horodatage | Le contenu des échanges |
| Journal de purge | Nombre de photos candidates, supprimées, en échec, à chaque passage | Les chemins des fichiers, l'identifiant de l'enfant |
| Version de l'app | Le numéro de build installé, pour vérifier qu'il est encore pris en charge | — |

Sur le téléphone lui-même, l'app garde seulement : un réglage local (bandeau de première
rencontre fermé ou non), la date de votre dernière visite des bilans, un cache audio
temporaire, et, si l'envoi a échoué, les photos en attente d'envoi. Le jeton de connexion
est conservé par la bibliothèque Supabase.

## 4. Qui reçoit vos données

Nous ne vendons ni ne louons aucune donnée. Les seuls destinataires sont nos prestataires
techniques, qui traitent les données **pour notre compte** et selon nos instructions.

| Prestataire | Pays | Ce qu'il reçoit | Ce qu'il ne reçoit pas |
|---|---|---|---|
| **Supabase** (base de données, authentification, stockage de fichiers, fonctions serveur) | **France (Paris)** | Tout ce qui est décrit à la section 3 | — |
| **OpenAI** | **États-Unis (hors UE)** | La voix de l'enfant (transcription) ; le texte d'Ari (synthèse vocale) ; en mode Devoirs et pour les indices d'exercice : les échanges texte, les photos et le prénom de l'enfant | L'e-mail du parent, le PIN |
| **OpenRouter** (intermédiaire) puis **Anthropic** (modèles Claude) | **États-Unis (hors UE)** | Les échanges texte en mode Apprentissage, les photos du cahier, le prénom et la classe, les synthèses de séance, les bilans, les conversations parent | L'e-mail du parent, le PIN, la voix |

Précisions :

- Pour les appels à OpenAI en mode Devoirs et pour les indices, nous demandons
  explicitement à OpenAI de **ne pas conserver l'échange** après la réponse (paramètre
  `store: false`), parce qu'il s'agit de données de mineurs.
- Aucun autre tiers ne reçoit de données : **aucun outil d'analyse d'audience, aucun outil
  de publicité, aucun outil de rapport de plantage** n'est intégré à l'application.
- Apple (TestFlight) et Google (Google Play) distribuent l'application et peuvent, de leur
  côté, vous demander un retour ; nous ne leur transmettons aucune donnée de l'enfant.

Ces prestataires étant établis hors de l'Union européenne, les données qui leur sont
envoyées font l'objet d'un **transfert international**. Le cadre juridique de ces
transferts sera précisé dans une prochaine version de cette politique.

## 5. Combien de temps nous conservons les données

| Donnée | Durée | Comment |
|---|---|---|
| Enregistrement de la voix de l'enfant | **Zéro** : transmis pour transcription, jamais stocké | Pas d'écriture en base ni en stockage de fichiers |
| Photos du cahier (énoncés, dictées) | **90 jours**, puis effacement | Purge automatique hebdomadaire (dimanche 4 h), active depuis le 9 septembre 2026 |
| Texte des échanges, synthèses, exercices, dictées, bilans, conversations parent | **Tant que le compte existe** | Aucune purge automatique à ce jour ; effacement sur demande (section 7) |
| Audio des dictées lues par Ari | **Tant que le compte existe** | Aucune purge automatique à ce jour |
| Souvenirs pédagogiques (maîtrise, lexique, portrait) | **Tant que le compte existe** | Aucune purge automatique à ce jour |
| Journal des appels d'IA | **Tant que le compte existe** ; conservé sans identifiant d'enfant après suppression de l'enfant | Le lien vers l'enfant est effacé (`set null`), la ligne technique reste |
| Événements d'usage | **30 jours** prévus | La purge est écrite mais **pas encore activée** |
| Compte parent, PIN, profil enfant | **Tant que le compte existe** | La suppression du compte entraîne, en cascade, celle du profil, des séances, des échanges, des souvenirs et des bilans |

## 6. Mineurs et consentement

- Le parent **crée le compte**, **crée le profil** de l'enfant et **consent** au traitement
  des données de l'enfant, par une case à cocher lors de l'inscription. Sans cette case,
  l'inscription est impossible.
- L'enfant n'a pas de compte, pas d'e-mail, pas de mot de passe.
- Le parent peut **retirer son consentement** à tout moment en demandant la suppression du
  compte (section 7). Le retrait met fin à l'usage de l'application.

## 7. Vos droits, et comment les exercer

Vous disposez, pour vous et pour votre enfant, des droits suivants :

- **Accès** : savoir quelles données nous détenons, et en obtenir une copie.
- **Rectification** : corriger une donnée. Le prénom, le genre, les matières et les notions
  prioritaires se modifient directement dans l'espace parent (« Mon compte »). La classe et
  l'e-mail se modifient sur demande.
- **Effacement** : faire supprimer le compte et toutes les données de l'enfant. Pendant la
  bêta, la suppression se fait **sur demande par e-mail**, dans un délai d'un mois au plus ;
  l'application ne propose pas encore de bouton de suppression automatique.
- **Retrait du consentement** : à tout moment, avec le même effet qu'une demande
  d'effacement.
- **Portabilité** : obtenir vos données dans un format lisible.
- **Réclamation** : vous pouvez saisir la CNIL (www.cnil.fr) si vous estimez que vos droits
  ne sont pas respectés.

Pour exercer un droit, écrivez à bonjour@aristocles.fr depuis l'adresse e-mail de votre
compte, en précisant le prénom de l'enfant concerné.

## 8. Pas de publicité, pas de pistage, pas de revente

- L'application ne contient **aucune publicité** et aucun kit publicitaire.
- Elle ne fait **aucun suivi** de votre activité à des fins publicitaires ou de mesure
  d'audience : aucun identifiant publicitaire n'est lu, aucun outil d'analyse tiers n'est
  installé. Le manifeste de confidentialité iOS déclare `NSPrivacyTracking = false`.
- Vos données ne sont **jamais vendues, louées ni cédées**.

## 9. Sécurité

- Toutes les communications entre l'application et nos serveurs sont **chiffrées (HTTPS)** ;
  l'app refuse les connexions non chiffrées.
- Les fichiers (photos, audio de dictée) sont dans des espaces **privés**, accessibles
  uniquement au parent de l'enfant concerné.
- La base de données applique une **isolation par famille** : un parent ne peut lire que
  les données de ses propres enfants.
- Le PIN parent est protégé par une empreinte **Argon2id** avec verrouillage après échecs.
- Les journaux techniques ne contiennent **jamais** le contenu des échanges ni la voix.
- Les mots de passe sont gérés par Supabase Auth. La longueur minimale est de 6 caractères.

## 10. Phase bêta : ce que l'équipe peut voir

Aristocles est en version bêta. Pour améliorer le tuteur, l'équipe dispose d'un **tableau
de bord de suivi des testeurs**, protégé par mot de passe, qui montre par enfant : le
prénom, les séances, les exercices résolus, les **synthèses rédigées** de chaque écran, le
résumé de séance, les coûts et durées des appels d'IA, et les événements d'usage. Ce tableau
de bord **ne montre jamais le verbatim** des échanges entre l'enfant et Ari.

Les échanges bruts restent en base et peuvent être consultés directement par l'équipe pour
diagnostiquer un problème signalé par une famille. Pendant la bêta, cet accès direct est
limité au fondateur d'Aristocles.

## 11. Modifications de cette politique

Cette politique sera mise à jour à chaque évolution du traitement (nouveau prestataire,
nouvelle durée de conservation, ouverture au public). La version et la date figurent en tête.
Les familles bêta seront prévenues par e-mail en cas de changement important.
