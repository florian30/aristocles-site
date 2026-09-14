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
> pistage, pas de revente. Nous vous demandons un **accord explicite**, que vous pouvez
> **retirer à tout moment** par e-mail : le compte et les données sont alors supprimés.
>
> Ce texte accompagne la [politique de confidentialité](/aristocles-site/confidentialite/),
> qui détaille chaque point. Version 0.2, 14 septembre 2026.

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
| Des **mesures techniques** : durée et coût des appels d'IA, événements d'usage | Supabase, Paris | Tant que le compte existe (événements : 30 jours prévus) |

Ce que l'application **ne fait pas** : pas de publicité, pas d'outil de mesure d'audience,
pas de suivi publicitaire, pas de revente ni de cession de données, pas d'accès à votre
galerie de photos, pas d'écoute en dehors du bouton.

## Pendant la bêta : ce que nous regardons

Aristocles est en version bêta, testée par un cercle proche de familles. Pour améliorer le
tuteur, l'équipe consulte un tableau de bord de suivi qui montre, par enfant, le prénom,
les séances, les exercices, les **synthèses rédigées** de chaque écran et les coûts. Ce
tableau de bord **ne montre pas le mot à mot** des échanges. Le texte intégral reste en
base et peut être relu directement pour diagnostiquer un problème que vous nous signalez.

## Ce que nous vous demandons

1. **Votre accord explicite** pour que les données de votre enfant soient traitées comme
   décrit ci-dessus, y compris leur transmission aux prestataires d'intelligence
   artificielle situés aux États-Unis. Cet accord se donne en cochant la case lors de
   l'inscription ; sans lui, le compte ne peut pas être créé.
2. **De rester présent** : l'application est faite pour un enfant sous le regard d'un
   adulte, sur l'appareil de l'adulte.
3. **De nous signaler** tout comportement d'Ari qui vous semble inapproprié, faux ou
   inquiétant, pour que nous corrigions.

Vous pouvez **retirer votre accord à tout moment**, sans justification, en nous écrivant à
bonjour@aristocles.fr depuis l'e-mail de votre compte. Nous supprimons alors le compte et
toutes les données de votre enfant (profil, échanges, photos, souvenirs, bilans). Pendant la
bêta, cette suppression est faite **à la main, sur demande, dans un délai d'un mois au plus** :
l'application n'a pas encore de bouton « supprimer mon compte » qui agisse seul.

Vous pouvez aussi, à tout moment : consulter les données que nous détenons, corriger le
prénom, le genre, les matières et les priorités de votre enfant directement dans l'espace
parent, et nous demander la correction de la classe ou de l'e-mail.
