# DiagnoPhish — Rapport de synthese CEJEF

## Stack

- HTML statique + Tailwind CSS (Play CDN local, `libs/tailwind.js`)
- Polices self-hosted : Montserrat (titres) + Inter (corps) dans `fonts/`
- Pas de framework JS, pas de build, pas de backend
- Heberge sur GitHub Pages

## Structure

```
index.html              # Rapport de synthese DiagnoPhish
charte-graphique.html   # Page de reference charte graphique CEJEF
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
  logo-cejef.webp         # Ancien logo (non utilise)
  favicon.svg
  favicon-32x32.png
.gitignore               # Exclut playwright/
```

## Charte graphique CEJEF

### Couleurs
- Divisions : DIVART #003865, DIVCOM #0053A1, DIVLYC #F28C00, DIVSSA #CAD400, DIVTEC #DF006E
- Neutres : Noir #1A171B (texte), Gris #878787 (secondaire), Gris clair #B0B1B3 (bordures)
- Fond : #FFFFFF ou #F5F5F5

### Typographie
- Titres : Montserrat, Bold/Semibold
- Corps : Inter, Regular
- H1 2rem Bold #1A171B, H2 1.5rem Semibold #003865, H3 1.25rem Semibold #1A171B

### Principes
- Sobriete : pas de degrades, pas d'ombres, pas d'effets 3D
- Border-radius 8px max, bordures 1px #B0B1B3
- Tables : en-tetes fond #003865, texte blanc
- WCAG AAA vise (contrastes >= 7:1)
- Zero CDN externe — tout est self-hosted

## Donnees

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
