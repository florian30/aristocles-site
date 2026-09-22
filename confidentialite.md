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
> des échanges est conservé tant que le compte existe. **Pendant la bêta**, l'app enregistre
> aussi les **écrans consultés et les erreurs techniques** (sans le contenu des échanges) et
> garde une **copie complète des échanges avec le tuteur envoyés à l'IA**, pour comprendre et corriger Ari :
> **90 jours au plus**, lue par le fondateur seul. Vous pouvez supprimer le compte et toutes
> les données à tout moment **depuis l'application** (Espace parent › Mon compte ›
> Supprimer mon compte) : la suppression est **immédiate et irréversible**, fichiers compris.
>
> Version 0.7 (bêta), datée du 22 septembre 2026 — cette version acte deux choses, qui ne
> s'appliquent pas au même moment. **Dès maintenant**, quelle que soit la version de
> l'application installée : depuis le 16 septembre 2026, le **tableau de bord de suivi** de
> la bêta s'ouvre avec le compte personnel du fondateur, et il lui montre **tout** ce que la
> bêta recueille, y compris le mot à mot des échanges de l'enfant avec Ari, la copie complète
> des échanges avec l'IA, les événements d'usage, l'e-mail du parent et les photos du cahier
> (section 10) ; le fondateur en est le seul lecteur. **À partir de la prochaine version de
> l'application**, et seulement une fois qu'elle est installée : Ari ne demande plus à
> l'enfant son école ni le prénom de son enseignant ; ses deux réponses de la première
> rencontre (ce qu'il aime faire en dehors de l'école, ce qu'il préfère à l'école) sont
> enregistrées et transmises au tuteur, avec son prénom et sa classe, en mode Apprentissage ;
> Ari réagit à chaque réponse de la rencontre par un appel à l'IA qui reçoit le genre de
> l'enfant, sans son prénom ni sa classe (sections 3.2 et 3.5) ; en mode Devoirs, quelques
> mots de l'énoncé accompagnent la voix envoyée à la transcription (section 3.3), **sans
> nouveau prestataire**. Une application qui n'est pas mise à jour continue de fonctionner
> comme avant. La version 0.6 actait que **la suppression du compte se fait depuis
> l'application** (section 5, section 7) : Espace parent › Mon
> compte › Supprimer mon compte, le mot de passe du compte est demandé, l'effacement est
> **immédiat et irréversible** et emporte aussi les **fichiers** (photos du cahier, audio
> des dictées). L'e-mail reste une voie de secours. La version 0.5 changeait l'adresse de
> contact d'Aristocles pour contact@aristocles.app. La version 0.4 corrigeait l'effacement
> des journaux de la bêta : ils sont effacés **immédiatement** avec le compte, en cascade,
> et non plus survivants jusqu'à la purge à 90 jours.

---

## 1. Qui est responsable de vos données

Aristocles est édité, en phase bêta, par son fondateur. Contact pour toute question ou
demande sur vos données : contact@aristocles.app. Les coordonnées complètes de l'éditeur
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
| Genre (fille / garçon / autre / non précisé) | Pour accorder correctement les phrases d'Ari. À partir de la prochaine version de l'application : pour accorder la phrase qu'Ari improvise en réaction à chaque réponse de la première rencontre (ci-dessous) | Oui |
| Classe (CE1, CE2, CM1 ou CM2) | Pour adapter le niveau des exercices et du langage | Oui |
| École | Posée à l'enfant par Ari lors de la première rencontre. **Question retirée à partir de la prochaine version de l'application** ; les réponses déjà données sont conservées (voir ci-dessous) | Non |
| Prénom du maître ou de la maîtresse | Posée à l'enfant lors de la première rencontre. **Question retirée à partir de la prochaine version de l'application** ; les réponses déjà données sont conservées (voir ci-dessous) | Non |
| Matières actives, notions à travailler en priorité | Réglages choisis par le parent | Non |
| Ce que l'enfant aime faire en dehors de l'école, ce qu'il préfère à l'école | À partir de la prochaine version de l'application : ses réponses à Ari lors de la première rencontre, pour qu'Ari sache un peu à qui il parle | Non |

Nous ne demandons **ni date de naissance, ni photo, ni adresse de l'enfant**.

**La première rencontre change avec la prochaine version de l'application.** Les deux
paragraphes qui suivent ne s'appliquent qu'une fois cette version installée. Tant qu'elle
ne l'est pas, rien ne change : Ari pose les questions d'avant (dont l'école et le prénom de
l'enseignant), ce que l'enfant dit aimer faire en dehors de l'école **n'est pas enregistré**,
et aucun appel à l'IA n'est fait pendant la rencontre.

Lors de la première rencontre, Ari demande à l'enfant ce qu'il aime faire en dehors de
l'école et ce qu'il préfère à l'école. **Ses deux réponses sont enregistrées telles
quelles**, sans correction : ce sont des réponses libres, qui peuvent contenir un nom s'il
en dit un (le sien, celui d'un camarade, d'un lieu). Une seule exception : quand l'IA qui
réagit pendant la rencontre (ci-dessous) a vu dans ce que l'enfant a dit non pas une
réponse mais une question à Ari, un jeu ou un propos qui n'a pas sa place, **rien n'est
enregistré pour cette question** ; l'enfant peut répondre à nouveau avec le bouton « Ce
n'est pas ça ». Si l'IA n'a pas répondu à temps, la réponse est enregistrée telle quelle.
Les réponses enregistrées sont ensuite **transmises au tuteur à chaque échange du mode
Apprentissage** (3.5), chacune coupée à 120 caractères.

**Pendant la rencontre, Ari réagit à chaque réponse.** Chaque réponse de l'enfant (le
« bonjour » d'échauffement compris, qui n'est pas enregistré) est **envoyée une fois à un
modèle d'IA** (via OpenRouter, puis Anthropic Claude, aux États-Unis), avec la question
qu'Ari venait de poser, pour qu'Ari y réponde d'**une phrase**. Le modèle dit aussi ce qu'il
a vu dans la réponse (une réponse, une question à Ari, un jeu, un propos qui n'a pas sa
place) ; c'est l'application, pas le modèle, qui décide de reposer la question (une fois au
plus) ou de passer. Si l'enfant a corrigé sa réponse avec le bouton « Ce n'est pas ça »,
l'ancienne et la nouvelle partent ensemble. **Cet envoi contient le genre de l'enfant**, pour que les mots d'Ari
soient accordés — et pour cela seulement : le modèle a pour consigne de ne pas choisir ce
qu'il dit selon le genre. **Il ne contient ni le prénom ni la classe.** Si le modèle ne
répond pas à temps, Ari dit une phrase toute faite. Cet appel est compté dans le journal des
appels d'IA (3.7, sans le texte) et, pendant la bêta, copié dans le journal complet (3.8).

Jusqu'à cette version, Ari demande aussi à l'enfant **le nom de son école** et **le prénom
de son maître ou de sa maîtresse**. **Avec la prochaine version, ces deux questions ne sont
plus posées** : l'école permet de situer un mineur, et le prénom de l'enseignant concerne un
adulte qui n'a rien accepté. Les réponses déjà données **ne sont pas effacées** : elles
restent sur le profil de l'enfant, et une application mise à jour n'en ajoute plus aucune.
Vous pouvez en demander l'effacement (section 7), et elles disparaissent avec le compte.

### 3.3 La voix de l'enfant

L'enfant parle à Ari en **appuyant sur un bouton** (push-to-talk) : le micro n'écoute que
pendant qu'il est enfoncé. L'enregistrement est envoyé à notre serveur, qui le transmet à
**OpenAI (service Whisper)** pour le transformer en texte, en français.

- **L'enregistrement audio n'est conservé nulle part** : ni sur nos serveurs, ni dans une
  base de données. Sur le téléphone, le fichier ne vit que dans un dossier temporaire.
- **Le texte obtenu est conservé** dans l'historique de la séance (voir 3.5).
- Nos journaux techniques ne gardent que la durée de l'enregistrement et sa taille, jamais
  son contenu ni sa transcription.
- Pour aider la transcription, l'enregistrement part avec une **courte amorce de texte** :
  quelques phrases fixes qui présentent Ari et, dans un exercice oral, une vingtaine de mots
  au plus tirés de l'exercice (des mots du programme, pas des données de l'enfant). **À
  partir de la prochaine version de l'application**, en mode Devoirs, cette amorce porte aussi une vingtaine de mots au plus de l'**énoncé**
  affiché — en général le texte lu sur la photo du cahier (3.4), où se trouvent par exemple
  des noms propres. **Aucun nouveau prestataire** : OpenAI reçoit déjà ces photos en mode
  Devoirs (section 4). Nos journaux ne gardent que le nombre de ces mots, jamais les mots.

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

En mode Devoirs, pour les synthèses et pour les bilans, chaque appel à un modèle d'IA reçoit
le **prénom** et la **classe** de l'enfant, ainsi que les consignes du devoir en cours : c'est
ce qui permet à Ari de parler à l'enfant et non à un inconnu. La transcription de la voix et
la synthèse vocale (3.3) ne les reçoivent pas. **En mode Apprentissage**, le tuteur ne reçoit
aujourd'hui ni le prénom ni la classe ; **à partir de la prochaine version de
l'application**, il les reçoit à chaque échange, avec, quand l'enfant les a données, **ses
deux réponses de la première rencontre** (3.2), chacune coupée à 120 caractères. Le mode
Devoirs ne reçoit pas ces deux réponses.

### 3.6 Les souvenirs pédagogiques

Pour qu'Ari s'améliore d'une séance à l'autre, nous conservons par enfant :

- un **état de maîtrise par notion** (jamais vue, fragile, en cours, acquise…), mis à jour à
  la fin des séances ;
- un **lexique de dictée** : les mots sur lesquels l'enfant bute, et combien de fois ;
- un **portrait** (intérêts, préférences pédagogiques, contexte personnel) destiné à être
  extrait automatiquement des synthèses de séance. **Cette extraction automatique est
  désactivée à ce jour** : le portrait reste vide tant qu'elle ne l'est pas.

Ces souvenirs ne sont **pas** injectés dans les conversations d'Ari avec l'enfant ; ils
servent aux bilans et à la conversation parent. Les deux réponses de la première rencontre
(3.2) n'en font pas partie : elles **sont** transmises au tuteur en mode Apprentissage, à
partir de la prochaine version de l'application.

### 3.7 Les données techniques

| Donnée | Ce qu'elle contient | Ce qu'elle ne contient jamais |
|---|---|---|
| Journal des appels d'IA | Rôle (tuteur, lecture de photo, réaction de la rencontre…), modèle utilisé, durée, nombre de jetons, coût estimé, succès ou échec, identifiant de l'enfant, identifiants de séance et d'écran ; pour la réaction de la rencontre (à partir de la prochaine version de l'application) : le genre de l'enfant et ce que le modèle a vu dans la réponse, sans le texte | Le texte envoyé, le texte reçu, le prénom (pendant la bêta, une copie complète des échanges vit dans un journal **à part**, décrit en 3.8) |
| Événements de séance | Type d'événement (début de tour, fin d'écran…), numéro de tour, écran concerné, horodatage | Le contenu des échanges |
| Événements d'usage (bêta) | Ce qui se passe **autour** des séances : liste ci-dessous | Le mot de passe, le code PIN, le contenu des échanges, le prénom, l'e-mail |
| Journal de purge | Nombre de photos candidates, supprimées, en échec, à chaque passage | Les chemins des fichiers, l'identifiant de l'enfant |
| Version de l'app | Le numéro de build installé, pour vérifier qu'il est encore pris en charge | — |

**Les événements d'usage, ajoutés pendant la bêta.** Pour comprendre comment l'application
est utilisée et où elle casse, l'app envoie à notre serveur, par petits lots, ce qui se passe
autour des séances :

- l'**ouverture** de l'app, son passage à l'arrière-plan et son retour au premier plan ;
- la **connexion** et la déconnexion du parent, avec la *méthode* utilisée (code reçu par
  e-mail, mot de passe, inscription, récupération de mot de passe) — jamais le secret ;
- la saisie du **code PIN** parent : uniquement son *issue* (réussie, ratée, verrouillée) ;
- les **écrans consultés** (nom de l'écran, temps passé dessus, parfois un détail comme la
  page affichée ou l'étape en cours), et l'entrée ou la sortie d'un **mode** (Apprentissage,
  Devoirs, Dictée) ;
- les **erreurs techniques** non rattrapées : la classe de l'erreur, l'écran où elle s'est
  produite, un code court s'il y en a un, et les chemins du code concerné (40 lignes au plus).

Chaque événement porte l'identifiant de votre compte, celui de l'enfant actif s'il y en a un,
la séance en cours s'il y en a une, la version de l'app et sa plateforme (iPhone ou Android),
et un identifiant tiré au hasard à chaque lancement de l'app.

Ce que ces événements **ne contiennent jamais** :

- **votre mot de passe et votre code PIN** : ni la valeur, ni un fragment, ni même leur
  longueur. Le serveur refuse tout événement qui en porterait un ;
- **le contenu des échanges** de votre enfant avec Ari, et son prénom. Le message brut d'une
  erreur technique, qui pourrait en recopier une phrase, est retiré par l'app avant l'envoi,
  et une seconde fois par le serveur ;
- votre adresse e-mail.

Ces événements ne sont lus que par le fondateur (section 10) et ne servent à aucune mesure
d'audience ni publicité (section 8).

Sur le téléphone lui-même, l'app garde seulement : un réglage local (bandeau de première
rencontre fermé ou non), la date de votre dernière visite des bilans, un cache audio
temporaire, et, si l'envoi a échoué, les photos en attente d'envoi. Le jeton de connexion
est conservé par la bibliothèque Supabase.

### 3.8 Pendant la bêta : le journal complet des échanges avec l'IA

Pendant la bêta, et seulement pendant la bêta, nous gardons pour **chaque réplique d'Ari** une
copie exacte de ce que le modèle d'IA a reçu et de ce qu'il a rendu. C'est un journal **à
part**, distinct de l'historique de séance (3.5) et du journal des appels d'IA (3.7). À
partir de la prochaine version de l'application, il couvre aussi les **réactions d'Ari
pendant la première rencontre** (3.2) : la question posée, la ou les réponses de l'enfant,
son genre, et ce que le modèle a rendu — sans prénom ni classe, que le modèle ne reçoit pas.

**Ce qu'il contient.** Côté requête : le contexte de séance envoyé au modèle (dont le
**prénom** et la **classe** de l'enfant — en mode Apprentissage, à partir de la prochaine
version de l'application, avec ses deux réponses de la première rencontre —, la notion
travaillée ou l'énoncé du devoir),
l'**historique complet du tour** (ce que l'enfant a dit, transcrit mot à mot ; ce qu'Ari a
répondu), la description du visuel affiché à l'écran, les **chemins** des photos du cahier
(le nom du fichier, jamais l'image), les noms des outils mis à disposition du modèle et les
réglages de l'appel. Côté réponse : la **sortie brute** du modèle (texte, appels d'outils,
raison d'arrêt, jetons consommés) et ce qui a réellement été dit à l'enfant après nos filtres.
Le texte des consignes d'Ari (le « prompt système ») est gardé une seule fois par version,
à part.

**Pourquoi.** Pour comprendre pourquoi Ari a dit ce qu'il a dit, et le corriger. Un tuteur qui
ne doit jamais donner la réponse se règle en relisant ses tours : là où il en a trop dit, où
il s'est trompé, où il a mal compris l'enfant. Le journal des appels d'IA (3.7), qui n'a pas
le texte, ne permet pas ce travail.

**Ce que ce journal n'ajoute pas.** Aucun envoi supplémentaire : c'est une copie, chez
Supabase à Paris, de ce qui est déjà transmis à nos prestataires pour faire fonctionner Ari
(section 4). Aucune photo n'y est stockée.

**Qui le lit.** Le **fondateur, seul** : directement dans la base de données, ou par le
tableau de bord de suivi (section 10), qui ne s'ouvre qu'avec son compte personnel.
L'application n'y a pas accès : la base refuse toute lecture autre que celle du serveur.

**Combien de temps.** 90 jours au plus (section 5).

**Ce journal est propre à la bêta.** Il sera retiré à la fin de la bêta, données comprises.
Cette politique changera de version ce jour-là.

## 4. Qui reçoit vos données

Nous ne vendons ni ne louons aucune donnée. Les seuls destinataires sont nos prestataires
techniques, qui traitent les données **pour notre compte** et selon nos instructions.

| Prestataire | Pays | Ce qu'il reçoit | Ce qu'il ne reçoit pas |
|---|---|---|---|
| **Supabase** (base de données, authentification, stockage de fichiers, fonctions serveur) | **France (Paris)** | Tout ce qui est décrit à la section 3 | — |
| **OpenAI** | **États-Unis (hors UE)** | La voix de l'enfant (transcription, avec une courte amorce de texte : 3.3) ; le texte d'Ari (synthèse vocale) ; en mode Devoirs et pour les indices d'exercice : les échanges texte, les photos et le prénom de l'enfant | L'e-mail du parent, le PIN |
| **OpenRouter** (intermédiaire) puis **Anthropic** (modèles Claude) | **États-Unis (hors UE)** | Les échanges texte en mode Apprentissage, les photos du cahier, le prénom et la classe, les synthèses de séance, les bilans, les conversations parent ; à partir de la prochaine version de l'application : en mode Apprentissage, les deux réponses de l'enfant à la première rencontre, et, pendant la rencontre elle-même, chaque réponse avec la question posée et le genre de l'enfant (sans prénom ni classe) | L'e-mail du parent, le PIN, la voix |

Précisions :

- Pour les appels à OpenAI en mode Devoirs et pour les indices, nous demandons
  explicitement à OpenAI de **ne pas conserver l'échange** après la réponse (paramètre
  `store: false`), parce qu'il s'agit de données de mineurs.
- Aucun autre tiers ne reçoit de données : **aucun outil d'analyse d'audience, aucun outil
  de publicité, aucun outil tiers de rapport de plantage** n'est intégré à l'application.
  Les erreurs techniques sont enregistrées par nous-mêmes, sur nos serveurs (3.7).
- Apple (TestFlight) et Google (Google Play) distribuent l'application et peuvent, de leur
  côté, vous demander un retour ; nous ne leur transmettons aucune donnée de l'enfant.

Ces prestataires étant établis hors de l'Union européenne, les données qui leur sont
envoyées font l'objet d'un **transfert international**. Le cadre juridique de ces transferts
sera précisé dans une prochaine version de cette politique.

## 5. Combien de temps nous conservons les données

| Donnée | Durée | Comment |
|---|---|---|
| Enregistrement de la voix de l'enfant | **Zéro** : transmis pour transcription, jamais stocké | Pas d'écriture en base ni en stockage de fichiers |
| Photos du cahier (énoncés, dictées) | **90 jours**, puis effacement | Purge automatique hebdomadaire (dimanche 4 h), active depuis le 9 septembre 2026. Les fichiers sont aussi effacés **immédiatement** avec le compte, par la suppression depuis l'app (section 7) |
| Texte des échanges, synthèses, exercices, dictées, bilans, conversations parent | **Tant que le compte existe** | Aucune purge automatique à ce jour ; effacés **immédiatement** avec le compte, en cascade, par la suppression depuis l'app (section 7) |
| Audio des dictées lues par Ari | **Tant que le compte existe** | Aucune purge automatique à ce jour ; ces **fichiers** sont effacés **immédiatement** avec le compte, par la suppression depuis l'app (section 7) |
| Souvenirs pédagogiques (maîtrise, lexique, portrait) | **Tant que le compte existe** | Aucune purge automatique à ce jour ; effacés **immédiatement** avec le compte, en cascade (section 7) |
| Journal des appels d'IA | **Tant que le compte existe** ; conservé sans identifiant d'enfant après suppression de l'enfant | Le lien vers l'enfant est effacé (`set null`), la ligne technique reste |
| Événements de séance (tours, écrans) | **30 jours** prévus | La purge est écrite mais **pas encore activée** |
| Événements d'usage (3.7, bêta) | **90 jours**, effacés automatiquement (purge hebdomadaire) | Effacés **immédiatement** avec le compte (suppression en cascade, depuis le 15 septembre 2026) ; sinon purge hebdomadaire le dimanche à 4 h, active depuis le 14 septembre 2026, jamais en dessous de 30 jours. |
| Journal complet des échanges avec l'IA (3.8, bêta) | **90 jours**, effacés automatiquement (purge hebdomadaire) | Effacés **immédiatement** avec le compte (suppression en cascade, depuis le 15 septembre 2026) ; sinon purge hebdomadaire le dimanche à 4 h, active depuis le 14 septembre 2026, jamais en dessous de 30 jours. |
| Compte parent, PIN, profil enfant | **Tant que le compte existe** | La suppression du compte entraîne, en cascade, celle du profil, des séances, des échanges, des souvenirs et des bilans. Les **fichiers** (photos du cahier, audio des dictées) sont effacés **avant** le compte par la fonction de suppression : rien ne survit au stockage (section 7) |

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
- **Effacement** : faire supprimer le compte et toutes les données de l'enfant, **y compris
  les journaux de la bêta (3.7 et 3.8) et les fichiers (photos du cahier, audio des
  dictées), effacés en même temps que le compte**. Deux voies :
    - **Depuis l'application** : Espace parent › Mon compte › **Supprimer mon compte**.
      Votre mot de passe vous est demandé ; la suppression est **immédiate et
      irréversible**, fichiers compris (photos, audio).
    - **Par e-mail** : si votre application ne montre pas encore ce bouton, mettez-la à
      jour ; si vous ne pouvez plus vous connecter, écrivez à contact@aristocles.app
      depuis l'adresse e-mail de votre compte : la suppression est alors faite à la main,
      dans un délai d'**un mois au plus**.
- **Retrait du consentement** : à tout moment, avec le même effet qu'une demande
  d'effacement.
- **Portabilité** : obtenir vos données dans un format lisible.
- **Réclamation** : vous pouvez saisir la CNIL (www.cnil.fr) si vous estimez que vos droits
  ne sont pas respectés.

Pour exercer un droit, écrivez à contact@aristocles.app depuis l'adresse
e-mail de votre compte, en précisant le prénom de l'enfant concerné.

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
- Les journaux techniques (3.7) ne contiennent **jamais** le contenu des échanges ni la voix.
  La seule copie complète des échanges hors historique de séance est le journal de la bêta
  (3.8) : lisible par le fondateur seul, jamais la voix, jamais les photos.
- Le tableau de bord de suivi (section 10) ne s'ouvre qu'avec le **compte personnel du
  fondateur** : le serveur vérifie la connexion et refuse tout autre compte. Il ne fait que
  lire, et ne montre jamais le code PIN parent.
- Les mots de passe sont gérés par Supabase Auth. La longueur minimale est de 6 caractères.

## 10. Phase bêta : ce que l'équipe peut voir

Aristocles est en version bêta, testée par un cercle fermé de familles. Pour suivre cette
bêta et améliorer le tuteur, le fondateur dispose d'un **tableau de bord de suivi des
testeurs**. Depuis le 16 septembre 2026, on n'y entre plus par un mot de passe partagé :
il ne s'ouvre qu'avec le **compte personnel du fondateur**, qui en est le **seul lecteur**.

Ce tableau de bord montre **tout ce que la bêta recueille**, famille par famille et enfant
par enfant :

- le prénom, la classe et le genre de l'enfant, et l'**adresse e-mail du parent** ;
- les séances, les exercices et leur issue, les dictées, les devoirs, les synthèses rédigées
  de chaque écran, les résumés de séance et les souvenirs pédagogiques (3.6) ;
- vos **conversations avec Ari** dans l'espace parent ;
- le **mot à mot des échanges** entre l'enfant et Ari (3.5) : ce que l'enfant a dit,
  transcrit, et ce qu'Ari a répondu ;
- la **copie complète des échanges avec l'IA** (3.8) ;
- les **événements d'usage** (3.7) et les événements de séance, les coûts et durées des
  appels d'IA ;
- les **photos du cahier**, qu'il peut ouvrir par un lien valable cinq minutes, tant
  qu'elles n'ont pas été effacées (90 jours au plus, section 5).

Il ne montre jamais le code PIN parent, et il ne fait que lire : il ne modifie aucune donnée.

Le fondateur s'en sert pour **diagnostiquer un problème** signalé par une famille, et pour
**relire les tours d'Ari** afin d'améliorer ses consignes. Il peut aussi consulter ces
données directement dans la base. Personne d'autre n'a cet accès pendant la bêta. Les journaux propres à la bêta (3.7 événements d'usage, 3.8) sont
gardés 90 jours au plus ; le journal 3.8 sera retiré à la fin de la bêta.

## 11. Modifications de cette politique

Cette politique sera mise à jour à chaque évolution du traitement (nouveau prestataire,
nouvelle durée de conservation, ouverture au public). La version et la date figurent en tête.
Les familles bêta seront prévenues par e-mail en cas de changement important.
