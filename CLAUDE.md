# DiagnoPhish — Rapport de synthese CEJEF

## Stack

- HTML statique + Tailwind CSS (Play CDN local, `libs/tailwind.js`)
- Polices self-hosted : Montserrat (titres) + Inter (corps) dans `fonts/`
- Pas de framework JS, pas de build, pas de backend
- Heberge sur GitHub Pages

## Structure

```
index.html              # Rapport de synthese DiagnoPhish
charte-graphique.html   # Charte graphique CEJEF v2
libs/
  tailwind.js           # Tailwind Play CDN (copie locale)
fonts/
  montserrat-latin.woff2  # Titres (H1, H2, H3)
  inter-latin.woff2       # Corps de texte
img/
  logo-cejef-officiel.svg # Logo complet SVG officiel (header)
  icon-cejef.svg          # Icone seule (favicon)
  icon-div{art,com,lyc,ssa,tec}.svg  # Icones divisions
  logos-cejef.zip         # Archive complete tous formats
  png-large/              # PNG haute resolution (print)
  png-medium/             # PNG moyenne resolution (reseaux sociaux)
  png-small/              # PNG basse resolution (favicons)
.gitignore               # Exclut playwright/
```

## Charte graphique CEJEF v2

URL publique : https://fallinov.github.io/cejef-diagnophish/charte-graphique.html

### Principes

1. **Minimaliste** — aplats, pas de degrades bicolores
2. **Accessible** — WCAG AA minimum, AAA vise
3. **Souverain** — zero CDN externe, tout self-hosted
4. **Mobile-first** — concevoir pour mobile, enrichir pour desktop

### Couleurs divisions

| Division | Couleur | Texte |
|----------|---------|-------|
| DIVART | #003865 (navy) | Blanc (11.98:1 AAA) |
| DIVCOM | #0053A1 (bleu) | Blanc (7.63:1 AAA) |
| DIVLYC | #F28C00 (orange) | Noir (8.53:1 AAA) |
| DIVSSA | #CAD400 (lime) | Noir (12.93:1 AAA) |
| DIVTEC | #DF006E (rose) | Blanc (4.81:1 AA) |

### Couleurs neutres

- Noir #1A171B (texte), Gris #878787 (secondaire), Gris clair #B0B1B3 (bordures), Fond #F5F5F5

### Regles cles

- CTA global : aplat navy #003865 + texte blanc
- CTA division sombre (DIVART/COM/TEC) : fond division + texte blanc
- CTA division claire (DIVLYC/SSA) : fond division + texte noir
- Degrade 5 couleurs : barres decoratives 4px uniquement (header/footer)
- Ombres subtiles multicouches (3 niveaux)
- Radius : 16px (cartes), 12px (boutons), 8px (champs)
- Conteneur max 1280px, centre
- Polices : Montserrat (titres), Inter (corps), JetBrains Mono (code) — self-hosted
- Icones : Lucide uniquement
- Dark mode obligatoire
- `prefers-reduced-motion` obligatoire
- Touch targets minimum 44x44px
- Interdit : texte blanc sur orange/lime, Liquid Glass, CDN externes, polices fantaisie

### Sections de la charte (8 + annexe)

1. Couleurs (palette + neutres + etats + degrade + contrastes WCAG)
2. Logos (complet + icone + 5 divisions, SVG + PNG)
3. Typographie (polices + echelle + regles)
4. Composants (boutons + cartes + ombres + CTA + header/footer + formulaire)
5. Images & icones (formats + Lucide + ressources)
6. Ton editorial (labels + conventions suisses + accroches)
7. Regles (a faire / a eviter + principes + animations)
8. Annexes (stack technique + variables CSS completes + configs Tailwind/Nuxt)

## Donnees DiagnoPhish

Toutes les donnees sont **en dur dans `index.html`**. Pas de base de donnees, pas d'API.
Sources : rapports officiels Navixia SA (PDF).

### Trails

| Trail | Theme | Periode | Participants |
|-------|-------|---------|-------------|
| 1 | Detecter le phishing | Sept-Nov 2024 | 341 |
| 2 | Lire les liens internet | Dec 2024-Mars 2025 | 322 |
| 3 | SharePoint / Fichiers | Mars-Juin 2025 | 322 |
| 4 | Intelligence artificielle | Nov 2025-Fev 2026 | 302 |

### Divisions

DIVART (53), DIVCOM (53), DIVLYC (64), DIVSSA (60), DIVTEC (72) = 302 total (Trail 4)

## Conventions

- Code en anglais, commits en francais
- Zero CDN externe (souverainete des donnees)
- Logo header : `img/logo-cejef-officiel.svg`
- Favicon : `img/icon-cejef.svg`
- Captures Playwright dans `playwright/` (gitignore)

## Mise a jour des donnees

Pour ajouter un nouveau trail ou mettre a jour les scores :
1. Lire les rapports PDF Navixia
2. Mettre a jour les sections concernees dans `index.html`
3. Verifier la coherence des totaux (participants, pourcentages)
4. Les "inactifs" sont les utilisateurs avec "Current Security level" = 4 dans l'export CSV
