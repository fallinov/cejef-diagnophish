# DiagnoPhish — Rapport de synthese CEJEF

## Stack

- HTML statique + Tailwind CSS (via CDN dev, `libs/tailwind.js`)
- Pas de framework JS, pas de build, pas de backend
- Heberge sur GitHub Pages

## Structure

```
index.html          # Page unique du rapport
img/
  logo-cejef.webp   # Logo officiel CEJEF (utilise dans le header)
  logo-cejef.svg    # Logo SVG simplifie (non utilise)
  favicon.svg
  favicon-32x32.png
.gitignore           # Exclut playwright/
```

## Donnees

Toutes les donnees sont **en dur dans `index.html`**. Pas de base de donnees, pas d'API.
Sources : rapports officiels Navixia SA (PDF).

### Sections du rapport

| Section | Lignes ~ | Contenu |
|---------|----------|---------|
| Overview | 200-286 | 4 stat cards + tendance globale |
| Participation | 288-350 | Tableau inactifs par trail (4 trails) + barres visuelles |
| Phishing | 352-431 | Scenarios + comparaison 4 campagnes |
| Divisions | 434-533 | Scores par division (P1-P4) + liens/donnees |
| Detail trails | 535-672 | 4 blocs `<details>` avec scores par division |
| Constats | 674-750 | Analyse + recommandations Navixia |

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
- Pas de CDN externe en production (souverainete)
- Logo header : `img/logo-cejef.webp` (logo officiel, pas le SVG)
- Captures Playwright dans `playwright/` (gitignore)

## Mise a jour des donnees

Pour ajouter un nouveau trail ou mettre a jour les scores :
1. Lire les rapports PDF Navixia
2. Mettre a jour les sections concernees dans `index.html`
3. Verifier la coherence des totaux (participants, pourcentages)
4. Les "inactifs" sont les utilisateurs avec "Current Security level" = 4 dans l'export CSV
