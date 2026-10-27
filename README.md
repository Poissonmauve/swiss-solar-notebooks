# Solaire et choc des prix de l'électricité 2023 : les notebooks du midterm

**Question.** Est-ce que la hausse des tarifs d'électricité de 2023 a accéléré le solaire sur les toits en Suisse ?
Y = nouvelles installations solaires par commune et par an · X = hausse du tarif des ménages en 2023 (ct/kWh) · Z = part de logements habités par leur propriétaire.

> **Dépôt privé, à garder privé.** Le dossier `data/` contient les tarifs de reprise VESE, sous licence et réservés au groupe (voir plus bas).

## Les trois notebooks

| Fichier | C'est quoi |
|---|---|
| `1_midterm_eda_original.ipynb` | Le notebook partagé au groupe pour le midterm, en anglais. C'est la référence : les numéros de cases qu'on s'est répartis ([1], [3], [5]…) viennent de lui. |
| `2_midterm_eda_FR_commente.ipynb` | Le même notebook, case pour case et avec le même code, mais avec les explications et les commentaires en français. Les numéros de cases sont les mêmes que dans le 1. |
| `3_midterm_eda_FR_redecoupe.ipynb` | Une version française redécoupée en plus petites cases, avec plus d'explications, et une section 6 « Prochaines étapes » pour le final (brouillons, dont une étude d'événement qui tourne déjà). |

Les trois partent des mêmes fichiers bruts et donnent exactement les mêmes chiffres que les slides (297 633 installations, 2 098 communes, pente de 0,24 avec un IC de 0,20 à 0,28, placebo à 0,02…).

## Lancer un notebook

```bash
pip install pandas numpy matplotlib shapely statsmodels jupyter
```

```bash
jupyter notebook
```

Ouvrir le notebook voulu, puis *Kernel → Restart & Run All* (environ une minute). Il faut le lancer depuis la racine du dépôt : les notebooks lisent `data/` avec des chemins relatifs.

## Le reste du dossier

| Dossier | Contenu |
|---|---|
| `presentation/` | Les slides du midterm : `midterm_E4S_version_equipe.pptx` (notre dernière version) et `midterm_E4S_version_corrigee.pptx` (la même avec les petites corrections de texte : Feger, « Left chart », placebo, endogénéité, biais d'échantillon). |
| `docs/` | `QA.md` (questions probables et réponses), `PRESENTER_GUIDE.md` (script et explications), `STUDY_GUIDE.html` (tout le midterm expliqué depuis zéro, avec un quiz). |

## D'où viennent les données (`data/`, fichiers tels que téléchargés)

| Fichier | Source | Où le trouver |
|---|---|---|
| `bfe_plants.csv.zip` | OFEN, registre des installations de production d'électricité, extrait du 14 sept. 2026. Donne **Y**. | [opendata.swiss](https://opendata.swiss/de/dataset/elektrizitatsproduktionsanlagen) · [téléchargement direct](https://data.geo.admin.ch/ch.bfe.elektrizitaetsproduktionsanlagen/elektrizitaetsproduktionsanlagen/elektrizitaetsproduktionsanlagen_2056.csv.zip) |
| `elcom_tariffs_H2_H4_H7.csv` | ElCom, prix de l'électricité par gestionnaire de réseau (commune × gestionnaire × année, profils H2/H4/H7). Donne **X**. | [opendata.swiss](https://opendata.swiss/de/dataset/strompreis-per-stromnetzbetreiber) · [site des prix ElCom](https://www.strompreis.elcom.admin.ch/) |
| `bfs_dwellings_by_occupant_2000_all.csv` | OFS, recensement 2000, logements occupés par commune, nombre de pièces et type d'occupant (px-x-0903020000_103). Donne **Z**. | [tableau](https://www.bfs.admin.ch/asset/de/px-x-0903020000_103) |
| `bfs_commune_mutations.csv` | OFS, registre officiel des communes, fusions depuis 2010. | [registre](https://www.bfs.admin.ch/bfs/de/home/grundlagen/agvch.html) |
| `bfs_population.csv` | OFS STATPOP, population par commune, 2010–2025 (px-x-0102010000_101). | [tableau](https://www.bfs.admin.ch/asset/de/px-x-0102010000_101) |
| `bfs_gws_buildings_2015_2024.csv` | OFS, statistique des bâtiments (GWS), bâtiments par commune et catégorie. Donne la part de maisons individuelles. | [stats.swiss](https://stats.swiss/vis?df[ds]=disseminate&df[id]=DF_GWS_REG1&df[ag]=CH1.GWS&df[vs]=1.0.0&lc=de) |
| `swiss_boundaries_2020.geojson` | swisstopo swissBOUNDARIES3D, version 2020-01, converti en GeoJSON. Pour placer les installations et faire les cartes. | [produit](https://www.swisstopo.admin.ch/de/landschaftsmodell-swissboundaries3d) |
| `ortschaftenverzeichnis_plz.csv.zip` | swisstopo, annuaire officiel des localités avec codes postaux. Pour les installations sans coordonnées. | [produit](https://www.swisstopo.admin.ch/de/amtliches-ortschaftenverzeichnis) |
| `vese_pvtarif_2021.json`, `vese_pvtarif_2023.json` | VESE, base pvtarif, tarif de reprise par gestionnaire. **Sous licence.** Section 5 seulement. | [pvtarif](https://www.pvtarif.ch) |

**Licence VESE** : utilisation réservée au groupe, jamais publique (accord de VESE par téléphone le 7 octobre 2026, à condition que rien ne soit rendu public). Chaque résultat qui les utilise porte la mention « Données des tarifs de rétribution : VESE / pvtarif.ch » (http://www.vese.ch, http://www.pvtarif.ch). Tout le reste est de la donnée publique officielle.

## Pour le final

Le rapport final est un article de 3 000 mots maximum dans un notebook, à rendre sur Moodle le 18 décembre à 16 h. Il doit charger ses données par des liens URL, mais ce dépôt est privé et les données VESE ne peuvent pas être publiées : il faudra un dépôt public séparé avec seulement les données ouvertes. Le pipeline complet (régressions, études de robustesse) est dans le dépôt principal `swiss-solar-tariff-shock`.
