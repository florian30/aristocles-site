---
layout: page
title: "Consentement des parents — bêta Aristocles"
permalink: /consentement/
---

> **TL;DR** — Une page à lire avant de laisser votre enfant utiliser Aristocles. Votre
> enfant va **parler à Ari**, un tuteur robot qui ne donne jamais la réponse. Pour cela,
> l'app envoie sa **voix** (transcrite puis effacée), les **photos** de son cahier (gardées
> 90 jours) et le **texte des échanges** (gardé tant que le compte existe) à des services
> d'intelligence artificielle aux États-Unis. Le reste est stocké à Paris. Pas de pub, pas de
> pistage, pas de revente. **Pendant la bêta**, l'app enregistre aussi les **écrans consultés
> et les erreurs techniques** (sans le contenu des échanges) et garde une **copie complète des
> échanges avec le tuteur envoyés à l'IA** pour comprendre et corriger Ari : 90 jours au plus,
> lue par le fondateur seul. Nous vous demandons un **accord explicite**, que vous pouvez **retirer à
> tout moment depuis l'application** (Espace parent › Mon compte › Supprimer mon compte) :
> le compte et toutes les données sont alors supprimés, **immédiatement et
> irréversiblement**, fichiers compris.
>
> Ce texte accompagne la [politique de confidentialité](/aristocles-site/confidentialite/),
> qui détaille chaque point. Version 0.7, 22 septembre 2026. **Dès maintenant**, le tableau
> de bord de suivi de la bêta ne s'ouvre qu'avec le compte personnel du fondateur, et il lui
> montre tout ce que la bêta recueille, y compris le mot à mot des échanges de votre enfant
> avec Ari et l'e-mail du parent (« Pendant la bêta : ce que nous regardons »). **À partir de
> la prochaine version de l'application**, une fois qu'elle est installée : Ari ne demande
> plus l'école ni le prénom de l'enseignant ; les deux réponses de votre enfant à la première
> rencontre sont enregistrées et transmises au tuteur, avec son prénom et sa classe, en mode
> Apprentissage ; Ari réagit à chaque réponse de la rencontre ; en mode Devoirs, quelques mots
> de l'énoncé accompagnent la voix envoyée à la transcription, sans nouveau prestataire. Une
> application qui n'est pas mise à jour continue de fonctionner comme avant. La version 0.6
> actait que la suppression du compte se fait depuis l'application, immédiate, irréversible,
> fichiers compris (photos, audio des dictées).

---

## Ce que votre enfant va faire

Aristocles est une application de **tutorat vocal** pour les enfants du CE1 au CM2. Votre
enfant y rencontre **Ari**, une mascotte robot qui l'aide à réviser (mode Apprentissage), à
faire ses devoirs (mode Devoirs) et à s'entraîner en dictée.

- Ari **ne donne jamais la réponse** : il pose des questions, donne des indices, reformule,
  encourage. C'est le principe fondateur de l'application.
- Votre enfant **parle** à Ari en appuyant sur un bouton, et Ari lui **répond à voix haute**
  ; le texte s'affiche en parallèle.
- En mode Devoirs, votre enfant peut **photographier l'énoncé** dans son cahier pour qu'Ari
  le lise.
- Ari sait qu'il est une intelligence artificielle, le dit, et reconnaît ses erreurs. Il
  refuse les sujets sans rapport avec l'école.

Votre enfant utilise l'application **sur votre appareil, sous votre compte**. Il n'a pas de
compte à lui. L'espace parent (bilans, réglages) est protégé par un **code PIN** que vous
choisissez.

## Ce que l'application enregistre

| Quoi | Où ça va | Combien de temps |
|---|---|---|
| Votre **e-mail** et votre mot de passe | Supabase, Paris | Tant que le compte existe |
| Le **prénom**, le genre et la classe de votre enfant (et, s'il le dit à Ari, son école et le prénom de son enseignant). **À partir de la prochaine version de l'application**, Ari ne demande plus l'école ni le prénom de l'enseignant ; les réponses déjà données sont conservées, et vous pouvez en demander l'effacement | Supabase, Paris ; le prénom et la classe sont aussi transmis aux services d'IA en mode Devoirs, pour les synthèses et les bilans ; **à partir de la prochaine version de l'application**, aussi en Apprentissage. L'école et l'enseignant ne sont transmis à aucun service d'IA | Tant que le compte existe |
| **À partir de la prochaine version de l'application**, les **deux réponses** de votre enfant à la première rencontre : ce qu'il aime faire en dehors de l'école, ce qu'il préfère à l'école, enregistrées telles qu'il les a dites (elles peuvent contenir un nom s'il en a dit un) | Supabase, Paris ; transmises au tuteur (OpenRouter puis Anthropic, États-Unis) à chaque échange du mode Apprentissage, coupées à 120 caractères. **Pendant la rencontre**, chaque réponse est aussi envoyée **une fois** à ce service, avec la question posée et le **genre** de votre enfant (pour accorder les mots d'Ari, et pour cela seulement), pour qu'Ari y réagisse d'une phrase — **sans le prénom ni la classe** | Tant que le compte existe |
| La **voix** de votre enfant, pendant qu'il appuie sur le bouton | Transmise à OpenAI (États-Unis) pour être transcrite en texte, avec une courte amorce de texte pour aider la transcription ; **à partir de la prochaine version de l'application**, en mode Devoirs, cette amorce porte aussi une vingtaine de mots au plus de l'énoncé affiché (OpenAI reçoit déjà les photos du cahier en Devoirs : aucun nouveau prestataire) | **Jamais conservée** : ni chez nous, ni en base |
| Les **photos** du cahier | Stockées chez Supabase (Paris), dans un espace privé ; lues par un service d'IA (OpenRouter puis Anthropic, États-Unis ; en mode Devoirs, également OpenAI) | **90 jours**, puis effacées automatiquement |
| Le **texte des échanges** avec Ari (ce que votre enfant a dit, transcrit ; ce qu'Ari a répondu), les exercices faits, les dictées, les synthèses de séance et vos bilans | Supabase, Paris ; le texte est transmis aux services d'IA (OpenAI pour le mode Devoirs et les indices ; OpenRouter/Anthropic pour le reste) pour qu'Ari réponde et pour rédiger les bilans | Tant que le compte existe |
| Des **souvenirs pédagogiques** : les notions acquises ou fragiles, les mots de dictée qui posent problème | Supabase, Paris | Tant que le compte existe |
| Des **mesures techniques** : durée et coût des appels d'IA (sans le texte), événements de séance (tours, écrans) | Supabase, Paris | Tant que le compte existe (événements de séance : 30 jours prévus) |
| **Pendant la bêta**, des **événements d'usage** : ouverture de l'app, connexion (la méthode, jamais le mot de passe), saisie du PIN (réussie ou ratée, jamais le code), écrans consultés et temps passé, modes ouverts, erreurs techniques (type, écran, code, chemins du code — jamais le message brut ni le contenu des échanges) | Supabase, Paris ; lus par le fondateur seul | **Effacés avec le compte** ; sinon 90 jours (purge hebdomadaire) |
| **Pendant la bêta**, une **copie complète de ce qui est envoyé à l'IA** à chaque réplique d'Ari : le contexte (prénom, classe, notion ou énoncé ; en mode Apprentissage, à partir de la prochaine version de l'application, les deux réponses de la première rencontre), tout l'échange du tour (ce que votre enfant a dit, ce qu'Ari a répondu), les noms des photos (jamais l'image) et la réponse brute du modèle — pour comprendre et corriger Ari. À partir de la prochaine version de l'application, aussi pour chaque **réaction d'Ari pendant la première rencontre** : la question, la ou les réponses de votre enfant, son genre, la phrase du modèle (sans prénom ni classe) | Supabase, Paris ; lue par le fondateur seul ; aucun envoi supplémentaire aux prestataires | **Effacés avec le compte** ; sinon 90 jours (purge hebdomadaire) ; journal retiré en fin de bêta |

Ce que l'application **ne fait pas** : pas de publicité, pas d'outil de mesure d'audience,
pas de suivi publicitaire, pas de revente ni de cession de données, pas d'accès à votre
galerie de photos, pas d'écoute en dehors du bouton.

## Pendant la bêta : ce que nous regardons

Aristocles est en version bêta, testée par un cercle proche de familles. Pour suivre la
bêta et améliorer le tuteur, le **fondateur** consulte un tableau de bord de suivi, qui ne
s'ouvre qu'avec **son compte personnel** : il en est le **seul lecteur**. Ce tableau de bord
montre **tout ce que la bêta recueille** : le prénom, la classe et le genre de votre enfant,
votre adresse e-mail, les séances, les exercices, les dictées, les devoirs, les synthèses
et les bilans, vos conversations avec Ari, le **mot à mot des échanges** de votre enfant
avec Ari, la **copie complète de ce qui est envoyé à l'IA**, les **événements d'usage**, et
les **photos du cahier** tant qu'elles ne sont pas effacées. Il ne montre jamais votre code
PIN, et il ne modifie rien.

Le fondateur s'en sert pour comprendre pourquoi Ari a dit ce qu'il a dit et le corriger,
pour voir où l'app est utilisée et où elle casse, et pour diagnostiquer un problème que vous
nous signalez. Il peut aussi consulter ces données directement dans la base. Personne
d'autre n'y a accès. Les deux journaux de la bêta (événements d'usage, copie de ce qui est
envoyé à l'IA) sont gardés 90 jours au plus, et le second sera retiré à la fin de la bêta.

## Ce que nous vous demandons

1. **Votre accord explicite** pour que les données de votre enfant soient traitées comme
   décrit ci-dessus, y compris leur transmission aux prestataires d'intelligence
   artificielle situés aux États-Unis. Cet accord se donne en cochant la case lors de
   l'inscription ; sans lui, le compte ne peut pas être créé.
2. **De rester présent** : l'application est faite pour un enfant sous le regard d'un
   adulte, sur l'appareil de l'adulte.
3. **De nous signaler** tout comportement d'Ari qui vous semble inapproprié, faux ou
   inquiétant, pour que nous corrigions.

Vous pouvez **retirer votre accord à tout moment**, sans justification. Le compte et toutes
les données de votre enfant sont alors supprimés : profil, séances et échanges avec Ari,
exercices et dictées, bilans, souvenirs pédagogiques, photos de cahier et audios de dictée
(**les fichiers compris**), et, pendant la bêta, les journaux de la bêta (événements
d'usage, copie des échanges avec l'IA). Deux voies :

- **Depuis l'application** : Espace parent › Mon compte › **Supprimer mon compte**. Votre
  mot de passe vous est demandé ; la suppression est **immédiate et irréversible**, fichiers
  compris (photos, audio).
- **Par e-mail** : si votre application ne montre pas encore ce bouton, mettez-la à jour ;
  si vous ne pouvez plus vous connecter, écrivez à contact@aristocles.app depuis l'e-mail
  de votre compte : la suppression est alors faite à la main, dans un délai d'**un mois au
  plus**.

Vous pouvez aussi, à tout moment : consulter les données que nous détenons, corriger le
prénom, le genre, les matières et les priorités de votre enfant directement dans l'espace
parent, et nous demander la correction de la classe ou de l'e-mail.
