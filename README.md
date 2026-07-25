# Kizomba Urban Quiz

**141 questions sur la culture kizomba. Et on cite nos sources.**

Un quiz sur la Kizomba, le Semba, l'Urban Kiz, le Tarraxo, la Tarraxinha et le Ghetto Zouk.
Gratuit, sans compte, sans publicité, jouable directement dans le navigateur.

👉 **[kizomba-urban-quiz.vercel.app](https://kizomba-urban-quiz.vercel.app/)**

*by KizFlow Studio*

---

## La règle de la maison

Cette application **ne tranche pas les débats de la scène.**

Sur les origines de l'Urban Kiz, sur les rôles des uns et des autres, sur la frontière entre
Tarraxinha et Tarraxo — les récits se contredisent, et aucune source neutre ne départage.
Alors l'app dit « souvent présenté comme », nomme qui affirme quoi, et laisse la discussion ouverte.

Exemple : Curtis Seldon et Enah Lebon se présentent tous deux publiquement comme créateur
ou fondateur de l'Urban Kiz. L'app pose la question sur **le désaccord lui-même**, pas sur
une version choisie.

### Quatre natures de question

Chaque question affiche ce qu'elle est. C'est visible à l'écran, après chaque réponse.

| Étiquette | Ce que ça veut dire | Nombre |
|---|---|---|
| **Source · …** | Affirmation vérifiable, avec sa provenance | 77 |
| **Repère pédagogique** | Conseil technique ou d'enseignement, pas de l'histoire | 35 |
| **Choix éditorial de l'app** | Une règle de formulation qu'on assume | 18 |
| **Règle de respect** | Consentement, écoute, humilité | 11 |

Un fait sans source s'affiche **en rouge**. Il en reste un dans l'app, et il est signalé
comme tel plutôt que caché.

---

## Une erreur ? Dites-le nous

Les récits de scène se contredisent et cette app n'est pas au-dessus.

Après chaque réponse, un lien **« Cette question te semble fausse ? Signale-la »** ouvre
un message pré-rempli avec l'identifiant de la question, la réponse donnée comme juste et
la source affichée. Il ne reste qu'à écrire ce qui cloche — et votre source.

On corrige, source à l'appui.

---

## Sujets encore ouverts

Ces points sont documentés de façon insuffisante et l'app les traite avec prudence.
Toute personne concernée qui souhaite préciser son propre parcours est la bienvenue.

- Les rôles respectifs de **Curtis Seldon**, **Enah Lebon** et **Moun** dans l'histoire de l'Urban Kiz
- Les profils de **DJ Anaïs**, **DJ Madiss**, **DJ Ash**, **DJ Radikal**, **DJ Snakes**, **DJ Neyser**
- **Félicien & Isabelle**, **Jonathan Mahoto**, **Albir Rojas & Sara López**
- La frontière exacte entre **Tarraxinha** et **Tarraxo** selon les scènes

---

## Ce que l'app fait

- **9 packs** qui se débloquent à l'XP : Découverte, Sensation, Culture, DJ Kizomba, Expert,
  Mindset, Evokeez, Pionniers, Galactic
- **Quiz du jour** — 5 questions, les mêmes pour tout le monde, nouvelles chaque jour
- **Cartes culturelles** à collectionner, partageables en story
- **Badges de maîtrise** par pack, série quotidienne
- **Français et anglais** — détection automatique, bascule manuelle
- **Installable** : sur Android un bandeau apparaît, sur iPhone c'est Partager → Sur l'écran d'accueil
- Progression enregistrée **sur l'appareil**, aucun compte, aucune donnée envoyée nulle part

---

## Technique

Un seul fichier. Aucune compilation, aucune dépendance, aucun gestionnaire de paquets.

```
index.html              toute l'application : HTML, CSS, JS, banque de questions
manifest.webmanifest    déclaration PWA
kizomba-loop.mp3        ambiance sonore
icon-*.png              icônes PWA
mark.png                médaillon (en-tête, favicon)
hero.jpg  quiz-bg.jpg  bg-resultat.jpg  bg-cartes.jpg  pack-bg.jpg  card-bg.jpg  share-bg.jpg
og.jpg                  aperçu de lien
```

Tout à la racine, aucun sous-dossier.

### Déploiement

Vercel, avec **Framework Preset : `Other`**, Build Command et Output Directory **vides**.
Chaque commit sur `main` déclenche un déploiement.

### Ajouter une question

Dans `index.html`, la constante `QUESTIONS`. Une entrée ressemble à ceci :

```js
{
  "i": "s058",                    // identifiant unique
  "p": "culture",                 // pack
  "m": "Racines",                 // thème affiché
  "n": "fait",                    // fait | pedago | ethique | editorial
  "t": "single",                  // single | multi
  "q": "L'énoncé de la question ?",
  "o": ["Option A", "Option B", "Option C", "Option D"],
  "c": [0],                       // index des bonnes réponses
  "k": "Nom de la carte",         // carte culturelle débloquée
  "e": "L'explication après réponse.",
  "s": "Source · à citer",        // obligatoire si n vaut "fait"
  "en": {                         // traduction anglaise, mêmes champs
    "m": "Roots", "q": "…", "o": ["…","…","…","…"],
    "k": "…", "e": "…", "s": "…"
  }
}
```

⚠️ **L'ordre des options dans `en.o` doit être identique à celui de `o`.** Les index de `c`
pointent sur les deux. Une option déplacée d'un rang fait valider la mauvaise réponse
sans aucun avertissement.

Les réponses sont mélangées à chaque partie, donc l'ordre écrit ici n'est pas celui vu par le joueur.

### Adresse de contact

En haut du script :

```js
const CONTACT = "…";
```

C'est la seule ligne à changer pour rediriger les signalements d'erreur.

---

## Principales sources

Travaux et sources institutionnelles, puis sources d'écoles et récits de scène — jamais
comme vérité unique.

- **Ambassade d'Angola** — récit officiel angolais
- **ANGOP / allAfrica** — classement de la Kizomba au patrimoine culturel immatériel
  national angolais, avril 2024, et candidature UNESCO en cours
- **Livia Jiménez Sedano**, *Kizomba Dance: From Market Success to Controversial National Brand*
- **Kizombalove Academy** — syllabus et histoire enseignée
- **Discovering Kizomba**, **Meu Semba**, **The Kiz Lab** — sources communautaires documentées
- **Music In Africa**, **Wikipédia** — profils et repères généraux
- Pages officielles des personnes citées, pour ce qu'elles revendiquent elles-mêmes

---

## In English

A quiz on Kizomba, Semba, Urban Kiz, Tarraxo, Tarraxinha and Ghetto Zouk culture.
141 questions, sources shown after every factual answer.

**This app does not settle the scene's arguments.** On the origins of Urban Kiz, on who did
what, on where Tarraxinha ends and Tarraxo begins, it says *"often described as"*, names who
is claiming what, and leaves the discussion open.

The app detects your language automatically. You can switch with the **FR / EN** toggle in
the header. Spotted a mistake? Every question has a **"Think this one is wrong? Flag it"**
link — write to us with your source and we will fix it.

---

*Kizomba Urban Quiz — by KizFlow Studio*
