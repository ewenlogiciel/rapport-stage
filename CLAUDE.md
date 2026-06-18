# Rapport de Stage — Site Web

## Contexte

Rapport de stage de fin de BUT MMI (Multimédia et Internet), spécialité Développement Web.
Format libre choisi : site web statique.

L'objectif est un rendu **visuellement impressionnant** qui reflète les compétences acquises en développement web. Le site est lui-même une démonstration du niveau atteint : typographie soignée, animations, mise en page travaillée. Pas un PDF mis en ligne — un vrai produit web.

## Stack technique

- **Astro** (v5) — framework SSG orienté contenu, zéro JS par défaut
- **Tailwind CSS** (v4) — utilitaires CSS, pas de classes custom sauf nécessité
- **TypeScript** — mode `strictest`
- Pas de framework JS (pas de React, Vue, etc.) — composants `.astro` uniquement

## Structure du projet

```
src/
├── layouts/
│   └── Layout.astro        # Layout principal (head, nav, footer)
├── components/
│   ├── Nav.astro            # Navigation latérale ou en-tête
│   └── SectionTitle.astro  # Titre de section réutilisable
├── pages/
│   ├── index.astro          # Page d'accueil / présentation
│   ├── entreprise.astro     # Présentation de l'entreprise d'accueil
│   ├── missions.astro       # Missions effectuées pendant le stage
│   ├── competences.astro    # Compétences développées
│   └── bilan.astro          # Bilan personnel et professionnel
└── styles/
    └── global.css           # Import Tailwind + variables CSS éventuelles
```

## Direction visuelle

- Dark theme avec accents colorés (à définir)
- Typographie forte : grands titres, hiérarchie marquée
- Animations au scroll via Intersection Observer (vanilla JS, pas de lib)
- Transitions de page fluides (View Transitions API d'Astro)
- Page d'accueil avec hero impactant
- Mise en page variée selon les sections — pas que du texte centré

## Système de couleurs

Toutes les couleurs de marque sont définies **une seule fois** dans `src/styles/global.css` via `@theme` :

```css
@theme {
  --color-accent: #3b82f6;       /* couleur principale (boutons, bordures actives) */
  --color-accent-light: #60a5fa; /* variante claire (textes, tags) */
  --color-canvas: #080810;       /* fond de page */
  --color-surface: #0f0f1a;      /* fond des cards */
  --color-surface-hover: #13132a;/* fond des cards au survol */
}
```

Dans les templates, utiliser **uniquement** les classes dérivées de ces variables :
- `bg-canvas`, `bg-surface`, `bg-surface-hover`
- `text-accent`, `text-accent-light`
- `bg-accent`, `bg-accent/10`, `border-accent/20`, etc.
- **Ne jamais** écrire `blue-400`, `blue-600`, `bg-[#080810]` en dur

Pour changer la couleur d'accent du site : modifier `--color-accent` et `--color-accent-light` dans `global.css` uniquement.

## Conventions

- JS vanilla uniquement côté client (animations, interactions), pas de framework
- Toutes les pages utilisent `Layout.astro`
- Tailwind v4 : pas de `tailwind.config.js`, configuration via CSS (`@theme` dans `global.css`)
- Préférer les classes utilitaires Tailwind directement dans le HTML
- Pas de commentaires sauf si la logique est non évidente

## Contenu

Le contenu du rapport (textes, dates, nom entreprise, missions) sera renseigné progressivement.
Ne pas inventer de contenu — utiliser des placeholders explicites du type `[À REMPLIR]`.

Quand un texte est fourni pour un projet ou une section : le reproduire **exactement**, mot pour mot. Il est permis de le **découper** en plusieurs blocs visuels (intro, contexte, fonctionnalités, etc.) selon ce qui rend le mieux, mais **jamais le reformuler, le résumer ou le réécrire**.
