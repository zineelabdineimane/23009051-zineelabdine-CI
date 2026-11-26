# CI22 — Partenaires commerciaux du Maroc (clustering)

**ENCG Settat — S7 Commerce international — Module BD & DS — Enseignant : A. Larhlimi — 2026–2027**
**Étudiant(e) :** ZINE EL ABDINE Imane — **Code Apogée :** 23009051 — **Groupe :** CI

## Problématique
Peut-on regrouper les partenaires commerciaux du Maroc en groupes homogènes et stables selon la structure de leurs échanges (taille des flux, solde, croissance 2015→2023) ?

## Données
- Source : UN Comtrade Plus — https://comtradeplus.un.org/
- Extraction du 19/11/2026 : https://comtradeplus.un.org/fr/trade-statistics?type=C&freq=A&cl=HS&cmd=TOTAL&period=2015%2C2023&reporter=504&partner=all&partner2=all&flow=X%2CM&mot=all&customs=all&breakdown=plus&aggregate=NONE#result
- Licence : UN Comtrade license agreement (https://comtradeplus.un.org/en/license-agreement) et conditions d'utilisation de l'ONU.
- Déclarant : Maroc ; flux X et M ; partenaires : tous ; produit : TOTAL (tous produits) ; années : 2015 et 2023 ; USD courants (`primaryValue`).
- Fichier attendu : `data/raw/comtrade_maroc.csv` [présent / non redistribué : voir `data/raw/LISEZMOI_donnees.md`].

## Méthode
K-means (pipeline : imputation médiane → standardisation → K-means), K choisi par la silhouette (3 à 8), comparé à : partition aléatoire, règle par taille d'échanges, K-means K=2, et GMM. Stabilité mesurée par l'ARI sur sous-échantillons de 80 % et plusieurs graines (graine = 42).

## Résultats (à compléter depuis le notebook)
| Méthode | Silhouette | Davies-Bouldin | ARI |
|---|---|---|---|
| K-means (K=6) | 0,301 | 0,902 | 0,843 |
| Références : aléatoire / règle par taille / K=2 / GMM | −0,142 / −0,049 / 0,363 / 0,245 | – / 4,057 / 1,070 / 1,075 | – |

## Reproduire
```bash
pip install -r requirements.txt
jupyter notebook notebooks/projet_CI22.ipynb   # ou Google Colab, puis tout exécuter
```
Les chemins sont relatifs depuis la racine du dépôt.

## Contenu du dépôt
`notebooks/projet_CI22.ipynb` notebook exécuté · `rapport/rapport.pdf` export · `presentation/` 6 diapositives (PDF + source) · `video/` ou lien ci-dessous · `figures/` · `docs/` fiche du sujet · `DECLARATION_IA.md`.

**Vidéo (si non déposée) :** [À COMPLÉTER — vidéo à ajouter plus tard]
