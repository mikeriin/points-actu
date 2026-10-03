# points-actu

Appli « Points actu » (PWA statique servie par GitHub Pages) : points d'actualité de 6h, 12h et 18h.

## Format d'une info (data/points.json → points[].sections.<rubrique>[])

```json
{
  "titre": "Gros titre court et accrocheur (6 à 12 mots)",
  "resume": "Une phrase d'explication rapide.",
  "details": "2 à 4 phrases de contexte, affichées au toucher sur « En savoir plus ».",
  "src": "Nom court de la source",
  "url": "https://…",
  "une": true
}
```

- `une` (facultatif) : met l'info en grand « À la une » ; sinon la première info de la première rubrique.
- L'ancien format `{"t": "…"}` reste lu : l'appli en tire elle-même titre, résumé et détails.
