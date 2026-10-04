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

## Langues (learn.html)

15 min d'anglais le matin, 15 min d'ukrainien le soir : révisions espacées, leçon du jour, exercices, oral, et une lecture tirée de l'actu.

- Leçons : `data/learn/en.json` et `data/learn/uk.json` (`{"lang","nom","niveau","lessons":[…]}`), 90 leçons chacune, une par jour.
- Progression : sur le téléphone (localStorage) et, si un jeton GitHub est saisi dans les réglages, dans `progress.json` sur la branche `progression` (fusion sans perte entre appareils).
- S'entraîner (accueil des langues, quand on veut) : cartes de tout ce qui a été vu (tout, mots difficiles, dernière leçon) et prononciation au micro (reconnaissance vocale du navigateur, sinon auto-évaluation). Une carte ratée revient 3 à 5 cartes plus loin jusqu'à ce qu'elle passe ; un mot oublié repart aussi à 1 jour dans les révisions espacées.
- Lecture du jour (facultatif, écrite par la routine des news) : champ `lecture` d'un point de `data/points.json`, par langue. Affichée pendant 48 h.

```json
"lecture": {
  "en": {
    "titre": "Titre en anglais",
    "texte": "120 à 180 mots, niveau B1-B2, paragraphes séparés par \n",
    "vocab": [{"cible": "to deploy", "fr": "déployer", "ex": "phrase du texte"}],
    "questions": [{"q": "Question de compréhension ?", "r": "Réponse courte."}],
    "src": "Source", "url": "https://…"
  }
}
```

Pour l'ukrainien, même format avec `"tr"` (transcription) dans `vocab`.
