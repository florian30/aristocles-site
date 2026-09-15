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
> tout moment** par e-mail : le compte et les données sont alors supprimés.
>
> Ce texte accompagne la [politique de confidentialité](/aristocles-site/confidentialite/),
> qui détaille chaque point. Version 0.5, 15 septembre 2026 (les journaux de la bêta sont
> désormais effacés immédiatement avec le compte).

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
| Le **prénom**, le genre et la classe de votre enfant (et, s'il le dit à Ari, son école et le prénom de son enseignant) | Supabase, Paris ; le prénom et la classe sont aussi transmis aux services d'IA à chaque échange | Tant que le compte existe |
| La **voix** de votre enfant, pendant qu'il appuie sur le bouton | Transmise à OpenAI (États-Unis) pour être transcrite en texte | **Jamais conservée** : ni chez nous, ni en base |
| Les **photos** du cahier | Stockées chez Supabase (Paris), dans un espace privé ; lues par un service d'IA (OpenRouter puis Anthropic, États-Unis ; en mode Devoirs, également OpenAI) | **90 jours**, puis effacées automatiquement |
| Le **texte des échanges** avec Ari (ce que votre enfant a dit, transcrit ; ce qu'Ari a répondu), les exercices faits, les dictées, les synthèses de séance et vos bilans | Supabase, Paris ; le texte est transmis aux services d'IA (OpenAI pour le mode Devoirs et les indices ; OpenRouter/Anthropic pour le reste) pour qu'Ari réponde et pour rédiger les bilans | Tant que le compte existe |
| Des **souvenirs pédagogiques** : les notions acquises ou fragiles, les mots de dictée qui posent problème | Supabase, Paris | Tant que le compte existe |
| Des **mesures techniques** : durée et coût des appels d'IA (sans le texte), événements de séance (tours, écrans) | Supabase, Paris | Tant que le compte existe (événements de séance : 30 jours prévus) |
| **Pendant la bêta**, des **événements d'usage** : ouverture de l'app, connexion (la méthode, jamais le mot de passe), saisie du PIN (réussie ou ratée, jamais le code), écrans consultés et temps passé, modes ouverts, erreurs techniques (type, écran, code, chemins du code — jamais le message brut ni le contenu des échanges) | Supabase, Paris ; lus par le fondateur seul | **Effacés avec le compte** ; sinon 90 jours (purge hebdomadaire) |
| **Pendant la bêta**, une **copie complète de ce qui est envoyé à l'IA** à chaque réplique d'Ari : le contexte (prénom, classe, notion ou énoncé), tout l'échange du tour (ce que votre enfant a dit, ce qu'Ari a répondu), les noms des photos (jamais l'image) et la réponse brute du modèle — pour comprendre et corriger Ari | Supabase, Paris ; lue par le fondateur seul ; aucun envoi supplémentaire aux prestataires | **Effacés avec le compte** ; sinon 90 jours (purge hebdomadaire) ; journal retiré en fin de bêta |

Ce que l'application **ne fait pas** : pas de publicité, pas d'outil de mesure d'audience,
pas de suivi publicitaire, pas de revente ni de cession de données, pas d'accès à votre
galerie de photos, pas d'écoute en dehors du bouton.

## Pendant la bêta : ce que nous regardons

Aristocles est en version bêta, testée par un cercle proche de familles. Pour améliorer le
tuteur, l'équipe consulte un tableau de bord de suivi qui montre, par enfant, le prénom,
les séances, les exercices, les **synthèses rédigées** de chaque écran et les coûts. Ce
tableau de bord **ne montre pas le mot à mot** des échanges. Le texte intégral reste en
base et peut être relu directement pour diagnostiquer un problème que vous nous signalez.

Pendant la bêta, le **fondateur seul** relit aussi, directement dans la base : la copie
complète de ce qui est envoyé à l'IA à chaque réplique d'Ari (pour comprendre pourquoi Ari a
dit ce qu'il a dit, et le corriger), et les événements d'usage (pour voir où l'app est utilisée
et où elle casse). Ces deux journaux sont gardés 90 jours au plus, personne d'autre n'y a
accès, et le premier sera retiré à la fin de la bêta.

## Ce que nous vous demandons

1. **Votre accord explicite** pour que les données de votre enfant soient traitées comme
   décrit ci-dessus, y compris leur transmission aux prestataires d'intelligence
   artificielle situés aux États-Unis. Cet accord se donne en cochant la case lors de
   l'inscription ; sans lui, le compte ne peut pas être créé.
2. **De rester présent** : l'application est faite pour un enfant sous le regard d'un
   adulte, sur l'appareil de l'adulte.
3. **De nous signaler** tout comportement d'Ari qui vous semble inapproprié, faux ou
   inquiétant, pour que nous corrigions.

Vous pouvez **retirer votre accord à tout moment**, sans justification, en nous écrivant
à contact@aristocles.app depuis l'e-mail de votre compte. Nous supprimons
alors le compte et toutes les données de votre enfant (profil, échanges, photos, souvenirs,
bilans). Pendant la bêta, cette suppression est faite **à la main, sur demande, dans un
délai d'un mois au plus** : l'application n'a pas encore de bouton « supprimer mon compte »
qui agisse seul.

Vous pouvez aussi, à tout moment : consulter les données que nous détenons, corriger le
prénom, le genre, les matières et les priorités de votre enfant directement dans l'espace
parent, et nous demander la correction de la classe ou de l'e-mail.
