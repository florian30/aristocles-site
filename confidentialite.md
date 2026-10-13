---
layout: page
title: "Politique de confidentialité — Aristocles (version bêta)"
permalink: /confidentialite/
---

Version 0.14 du 13-10-2026.

## L'essentiel

1. **Pourquoi nous avons besoin de données.** Ari aide votre enfant en le questionnant,
   sans jamais lui donner la réponse. Pour cela, il doit entendre ce qu'il dit, lire ses
   devoirs et se souvenir de ce qu'il a déjà fait. Nous ne demandons que le strict
   nécessaire : un prénom, un genre et une classe pour l'enfant, votre adresse e-mail pour
   vous. Pas de compte enfant, ni nom de famille, ni date de naissance, ni photo de
   l'enfant.
2. **Ce que nous gardons, et combien de temps.** La voix n'est jamais enregistrée : elle
   devient du texte, puis disparaît. Les photos de devoirs sont effacées au bout de
   90 jours. Les échanges avec Ari et les bilans sont gardés tant que le compte existe,
   chez notre hébergeur, à Paris.
3. **Qui d'autre les reçoit.** Pour comprendre la voix, lire une photo et répondre, Ari
   s'appuie sur des services d'intelligence artificielle situés aux États-Unis (OpenAI, et
   Anthropic par l'intermédiaire d'OpenRouter), liés à nous par contrat. Ils reçoivent le
   prénom et la classe de l'enfant, jamais votre adresse e-mail. Les e-mails passent par
   Resend ; les notifications, si vous les activez, par Google et Apple.
4. **Pendant la bêta.** Pour vérifier qu'Ari ne se trompe pas et ne donne jamais la
   réponse, le fondateur relit des échanges, aidé d'outils d'intelligence artificielle.
   Personne d'autre n'y a accès.
5. **Ce que nous ne faisons jamais.** Aucune publicité, aucune mesure d'audience, aucun
   pistage. Les données de votre enfant ne sont jamais vendues, louées ni cédées.
6. **Vous gardez la main.** Vous supprimez le profil d'un enfant, ou tout le compte,
   vous-même depuis l'application, immédiatement. Pour obtenir une copie de vos données,
   les corriger ou retirer votre accord : contact@aristocles.app. Vous pouvez aussi
   saisir la CNIL.

Le détail qui suit fait foi.

---

## 1. Qui est responsable de vos données

- **Responsable** : Florian Blanc, fondateur d'Aristocles.
- **E-mail de contact** : `contact@aristocles.app`

C'est à cette adresse que vous exercez vos droits (section 7) et posez vos questions.
Aucun délégué à la protection des données n'est désigné.

## 2. À qui s'adresse Aristocles

Aristocles accompagne des **enfants du CE1 au CM2**, qui l'utilisent **sous le compte de
leur parent**, sur l'appareil du parent. Il n'existe **pas de compte enfant** : le parent
crée le compte, crée jusqu'à **quatre profils** d'enfants et donne son accord pour eux.
Chaque enfant choisit son profil à l'ouverture de l'application ; ses séances et ses
progrès ne sont montrés qu'à lui et à vous, jamais à un frère ou une sœur. L'espace
parent est protégé par un code à quatre chiffres.

Pendant la bêta, l'application est diffusée à un cercle restreint de familles, par
TestFlight (iPhone) et par la piste de test de Google Play (Android).

## 3. Quelles données nous utilisons, et pourquoi

**Base légale : votre consentement.** Vous le donnez pour vous et pour vos enfants en
cochant la case de l'inscription (section 6). Les notifications demandent un accord à
part (3.6). Vous pouvez retirer votre accord à tout moment (section 7).

### 3.1 Votre compte

| Donnée | Pourquoi |
|---|---|
| Adresse e-mail | Vous identifier, vous envoyer les codes de connexion |
| Mot de passe | Protéger votre compte. Il n'est jamais conservé en clair |
| Code parent (4 chiffres) | Protéger l'espace parent. Il est chiffré de façon irréversible : personne, pas même nous, ne peut le lire |
| Date de votre accord | Garder la preuve de votre consentement |
| Compteur d'usage journalier | Limiter le nombre d'appels aux services d'IA par famille. Un nombre, sans contenu |

Nous ne demandons ni votre nom, ni votre adresse postale, ni votre numéro de téléphone.

### 3.2 Le profil de l'enfant

| Donnée | Pourquoi |
|---|---|
| Prénom | Qu'Ari s'adresse à l'enfant par son prénom |
| Genre (fille, garçon, autre, non précisé) | Que les phrases d'Ari soient correctement accordées |
| Classe (CE1 à CM2) | Adapter le niveau des exercices et du langage |
| Couleur du profil | Que chaque enfant reconnaisse le sien |
| Matières et notions à travailler | Vos réglages, facultatifs |
| Ce qu'il aime faire en dehors de l'école, ce qu'il préfère à l'école | Ses réponses à Ari lors de leur première rencontre, pour qu'Ari sache un peu à qui il parle |

Ces deux réponses sont gardées telles que l'enfant les a dites ; s'il y cite un nom, il y
reste. Les premières versions de l'application demandaient aussi le nom de l'école et le
prénom de l'enseignant : les réponses déjà données restent sur le profil, et vous pouvez
en demander l'effacement.

### 3.3 La voix

L'enfant parle à Ari **en appuyant sur un bouton** : le micro n'écoute que pendant
l'appui. L'enregistrement est envoyé à OpenAI (service Whisper), qui le transforme en
texte.

- **L'enregistrement n'est conservé nulle part**, ni sur nos serveurs, ni dans une base de
  données.
- **Le texte obtenu est conservé** avec la séance (3.5).

Votre voix, quand vous dictez un retour (3.7), suit le même chemin : elle est transcrite,
puis l'enregistrement est oublié. Vous relisez le texte avant de l'envoyer.

La voix d'Ari est fabriquée à partir de son texte par OpenAI (synthèse vocale). Elle n'est
pas conservée sur nos serveurs.

### 3.4 Les photos

En mode Devoirs et en Dictée, l'enfant peut **photographier l'énoncé** ou sa dictée. Un
modèle d'IA (Anthropic, et en mode Devoirs aussi OpenAI) lit la photo pour en tirer le
texte.

- Les photos sont rangées dans un **espace privé** : seul vous pouvez les revoir (et, pendant
  la bêta, le fondateur : section 10).
- **Elles sont effacées automatiquement au bout de 90 jours.** Les photos de dictée sont
  en plus **toutes effacées à la fin de la bêta**.
- Le **texte lu** sur la photo est gardé avec la séance.
- L'application n'ouvre la **galerie de photos** du téléphone qu'**à votre demande**, pour
  choisir une photo de devoir ou une capture d'écran à joindre à un retour (3.7). Elle ne
  reçoit que l'image choisie, jamais le reste de la galerie.

### 3.5 Les échanges avec Ari et le travail de l'enfant

Ce que l'enfant dit à Ari (en texte) et ce qu'Ari lui répond sont gardés avec la séance.
C'est ce qui permet à Ari de suivre la conversation, et de vous écrire les **bilans** du
jour et de la semaine.

Sont aussi gardés : les exercices faits et leur résultat, les dictées (texte, mots à
travailler, fautes relevées, et l'audio de la dictée lue par Ari), les listes de mots que
vous avez données, les devoirs, et vos propres conversations avec Ari dans l'espace
parent.

Pour que les séances et les bilans s'enchaînent, nous gardons aussi, par enfant, où il en
est dans chaque notion et les mots de dictée sur lesquels il bute.

**Ce que reçoivent les modèles d'IA.** À chaque échange, le modèle reçoit le prénom et la
classe de l'enfant, ce qu'il travaille et la conversation en cours. En mode Apprentissage,
il reçoit aussi les deux réponses de la première rencontre (3.2). Pendant la rencontre
elle-même, Ari réagit à chaque réponse : le modèle reçoit alors la réponse et le genre de
l'enfant, sans son prénom ni sa classe.

### 3.6 Les notifications

**Elles sont adressées au parent, jamais à l'enfant, et seulement si vous les activez.**
Vous les coupez, type par type ou toutes, dans Espace parent › Notifications ou dans les
réglages du téléphone.

Il y en a cinq types : le bilan de la semaine, le bilan du jour, les nouveautés de l'app,
les actualités d'Aristocles et de petits rappels. Une notification de bilan cite le
**prénom** de l'enfant et dit en une phrase ce qu'il a fait ; elle peut s'afficher sur
l'écran verrouillé, sauf si vous en masquez l'aperçu dans les réglages du téléphone.
Cette phrase est écrite par un modèle d'IA (Anthropic, via OpenRouter) à partir des faits
de la semaine, jamais à partir des mots de l'enfant.

Pour les envoyer, nous gardons le jeton de notification de votre téléphone et vos choix,
ainsi qu'un journal des envois (section 5).

L'application peut aussi afficher un court message d'Aristocles (une nouveauté, une
enquête). Ces messages sont les mêmes pour toutes les familles concernées. Un message
destiné à l'enfant n'ouvre jamais de page web et ne s'affiche jamais pendant une séance.

### 3.7 Vos retours sur l'application

Dans l'espace parent, l'écran « Votre avis sur l'application » vous permet de nous
signaler un problème ou une idée, par écrit ou à la voix (3.3), avec une capture d'écran
si vous le souhaitez. **Rien ne part sans que vous touchiez « Envoyer ».**

Avec votre message partent : sa catégorie, l'enfant concerné si vous en choisissez un, un
lien vers sa dernière séance, et des informations techniques (version de l'app, modèle et
système du téléphone, taille d'écran et de police, langue, notifications activées ou
non). Ces informations servent à reproduire le problème.

Le fondateur lit chaque retour. Il en reçoit aussi le texte par e-mail chaque matin, avec
le prénom et la classe de l'enfant choisi, mais sans votre adresse e-mail ni la capture.
Pour suivre la correction, il peut en reprendre le texte dans un outil de développement
assisté par l'IA (Claude, d'Anthropic). Les retours sont gardés 12 mois.

### 3.8 Les données techniques

Pour que l'application fonctionne et pour corriger ses défauts, nous gardons :

- un relevé de chaque appel aux services d'IA : quel modèle, combien de temps, quel coût.
  **Sans le texte des échanges** ;
- le déroulé des séances (début d'un tour, fin d'un écran), sans leur contenu ;
- pendant la bêta, ce qui se passe autour des séances : ouverture de l'app, connexion,
  écrans consultés, erreurs techniques. **Jamais votre mot de passe ni votre code parent,
  jamais le contenu des échanges, jamais le prénom ni votre adresse e-mail** ;
- pendant la bêta, une copie complète de ce que le modèle d'IA reçoit et répond à chaque
  réplique d'Ari, pour comprendre et corriger Ari (section 10). Aucune photo n'y figure.

Sur le téléphone, l'application ne garde que le nécessaire : votre connexion, la date de
votre dernière visite des bilans, un cache audio temporaire et, si un envoi a échoué, les
photos en attente.

## 4. Qui reçoit vos données

Nous ne vendons ni ne louons aucune donnée. Les seuls destinataires sont nos prestataires
techniques. Ils traitent les données **pour notre compte**, selon nos instructions.

| Prestataire | Pays | Ce qu'il reçoit, et pourquoi |
|---|---|---|
| **Supabase** (hébergement) | **France (Paris)** | Tout ce que décrit la section 3 : c'est là que vos données sont gardées |
| **OpenAI** | États-Unis | La voix, pour la transcrire ; le texte d'Ari, pour lui donner une voix ; en mode Devoirs et pour les indices, les échanges, les photos et le prénom de l'enfant |
| **OpenRouter**, qui transmet à **Anthropic** (modèles Claude) | États-Unis | Les échanges, les photos, le prénom, le genre et la classe de l'enfant, pour qu'Ari réponde, lise les devoirs et écrive les bilans et les notifications ; les retours que le fondateur reprend dans son outil de développement (3.7) |
| **Resend** (envoi des e-mails) | États-Unis | Votre adresse e-mail et les e-mails de connexion ; l'e-mail du matin du fondateur, qui reprend le texte de vos retours (3.7) |
| **Firebase** (service de Google), puis Apple ou Google | États-Unis | Si vous activez les notifications : le jeton de votre téléphone et le texte de chaque notification (3.6) |

Aucun de ces prestataires ne reçoit votre code parent. Les services d'IA ne reçoivent
jamais votre adresse e-mail.

Aucun autre tiers ne reçoit de données : **aucun outil de publicité, de mesure d'audience
ou de rapport de plantage** n'est intégré à l'application. Apple et Google, qui
distribuent l'application, ne reçoivent de nous que le texte des notifications.

**Transferts hors de l'Union européenne.** OpenAI, OpenRouter, Anthropic, Resend et
Google sont situés aux États-Unis. Ces transferts sont encadrés par les **clauses
contractuelles types** de la Commission européenne, prévues par le contrat de traitement
des données de chaque prestataire. Resend et Google adhèrent en plus au **cadre de
protection des données UE–États-Unis** (*Data Privacy Framework*). Vous pouvez obtenir une
copie de ces garanties à contact@aristocles.app.

**Ce que font les services d'IA des données reçues.** Ils **ne s'en servent pas pour
entraîner leurs modèles**. OpenRouter ne garde pas les échanges qu'il transmet. OpenAI ne
garde pas l'enregistrement de la voix après l'avoir transcrit. Pour le reste, OpenAI et
Anthropic peuvent garder les échanges **30 jours au plus**, pour détecter les abus, puis
les effacent ; seul un échange signalé comme contraire à leurs règles d'usage peut être
gardé plus longtemps. Resend garde une copie des e-mails envoyés.

## 5. Combien de temps nous gardons les données

| Donnée | Durée |
|---|---|
| Enregistrement de la voix | **Jamais conservé** |
| Photos du cahier (devoirs, dictées) | **90 jours**, puis effacement automatique. Les photos de dictée sont toutes effacées à la fin de la bêta |
| Compte, profils, échanges avec Ari, exercices, dictées et leur audio, listes de mots, bilans, suivi des notions | **Tant que le compte existe** |
| Listes de mots non confirmées (Dictée) | **7 jours**, puis effacement |
| Journal des appels d'IA (sans le texte des échanges) | **12 mois** (365 jours), puis effacement |
| Événements de séance (sans le contenu des échanges) | **90 jours**, puis effacement |
| Événements d'usage (bêta) | **90 jours**, puis effacement |
| Journal complet des échanges avec l'IA (bêta) | **90 jours**, puis effacement ; retiré à la fin de la bêta |
| Notifications : jeton du téléphone, vos choix | Tant que le téléphone est connecté au compte |
| Notifications : journal d'envoi | **90 jours**, puis effacement |
| Vos retours sur l'application, capture comprise | **12 mois**, puis effacement |

Supprimer le compte efface **immédiatement** tout ce qui précède, fichiers compris. Seul
le journal des appels d'IA, qui ne contient aucun texte, est détaché du compte et suit sa
durée de 12 mois.

## 6. Mineurs et consentement

- Le parent **crée le compte** et **les profils**, et **donne son accord** pour ses
  enfants en cochant une case à l'inscription. Sans elle, l'inscription est impossible.
  Cet accord vaut pour tous les profils du compte, y compris ceux ajoutés plus tard.
- L'enfant n'a ni compte, ni e-mail, ni mot de passe.
- Les **notifications** demandent un accord à part, que vous retirez à tout moment
  (3.6).
- Vous pouvez **retirer votre accord** à tout moment, en supprimant le compte ou en nous
  écrivant (section 7). Le retrait met fin à l'usage de l'application.

## 7. Vos droits, et comment les exercer

Vous disposez, pour vous et pour vos enfants, des droits suivants :

- **Accès** et **portabilité** : obtenir une copie de vos données, dans un format
  lisible.
- **Rectification** : le prénom, le genre, les matières et les notions se modifient dans
  l'espace parent ; la classe et l'adresse e-mail, sur demande.
- **Effacement** :
    - le **profil d'un enfant** : Espace parent › Mes enfants › la fiche de l'enfant ›
      Supprimer le profil. Tout ce qui le concerne est effacé immédiatement ; le compte et
      les autres profils sont conservés. Vos retours (3.7) restent, sans le lien vers cet
      enfant ;
    - **tout le compte** : Espace parent › Mon compte › Supprimer mon compte.
      L'effacement est immédiat et définitif, fichiers compris.
  Votre mot de passe vous est demandé dans les deux cas.
- **Retrait du consentement**, à tout moment.
- **Réclamation** auprès de la CNIL (www.cnil.fr), si vous estimez que vos droits ne sont
  pas respectés.

Pour tout le reste, ou si vous ne pouvez plus vous connecter, écrivez à
contact@aristocles.app depuis l'adresse de votre compte, en précisant le prénom de
l'enfant concerné. Nous répondons au plus tard sous un mois.

## 8. Ce que nous ne faisons jamais

- Aucune **publicité**, aucun kit publicitaire.
- Aucune **mesure d'audience** ni **pistage** : aucun identifiant publicitaire n'est lu,
  aucun outil d'analyse tiers n'est installé.
- Vos données ne sont **jamais vendues, louées ni cédées**.

## 9. Sécurité

- Les échanges entre l'application et nos serveurs sont **chiffrés**.
- Les photos et les fichiers audio sont dans des espaces **privés**.
- Chaque famille est **isolée** : un parent ne peut lire que les données de ses enfants.
- Le code parent est chiffré de façon irréversible et se bloque après plusieurs essais
  ratés.
- Nos journaux techniques ne contiennent jamais la voix, et seul le journal de la bêta
  (3.8) contient le texte des échanges.

## 10. Pendant la bêta : la relecture

Aristocles est en bêta, testé par un cercle fermé de familles. Pendant la bêta, pour
vérifier qu'Ari ne se trompe pas et ne donne jamais la réponse, le fondateur relit des
échanges, aidé d'outils d'intelligence artificielle. Personne d'autre n'y a accès.

Pour cela, il dispose d'un tableau de bord qui ne s'ouvre qu'avec son compte personnel.
Il y voit ce que la bêta recueille, famille par famille : le profil de l'enfant et votre
adresse e-mail, les séances et leurs échanges mot à mot, les bilans, les photos encore
conservées, les retours et les événements techniques. Il n'y voit jamais votre code
parent. Il s'en sert aussi pour comprendre un problème que vous nous signalez.

La copie complète des échanges avec l'IA (3.8) est gardée 90 jours au plus et sera
retirée à la fin de la bêta.

## 11. Modifications de cette politique

Cette politique change à chaque évolution de ce que fait l'application (nouveau
prestataire, nouvelle durée, ouverture au public). La version en vigueur est celle
publiée sur le site d'Aristocles ; son numéro et sa date figurent en tête.
