# Territoires restitués depuis plus d'un an — Faches-Ronchin

Ce dépôt sert **uniquement d'hébergement** pour deux fichiers cartographiques
régénérés automatiquement chaque semaine.

| Fichier | Usage |
| --- | --- |
| `territoires.geojson` | Lu automatiquement par la carte [uMap](https://umap.openstreetmap.fr/fr/map/territoire-1-an_1451432) |
| `territoires.kml` | Pour un import manuel dans Google My Maps |

Les zones dont le nom contient `APPT` (immeubles) sont **vertes**, les autres
territoires sont **bleus**. Chaque zone indique sa date de restitution.

## Pourquoi deux formats

Les deux outils ne lisent pas les styles de la même façon : Google My Maps
applique les styles portés par chaque `Placemark` d'un KML, tandis qu'uMap ne
colorie qu'à partir du champ `_umap_options` d'un GeoJSON et ignore les styles
d'un KML. Un fichier unique ne peut donc pas convenir aux deux.

## Confidentialité

Ces fichiers ne contiennent **aucune donnée personnelle** : ni nom, ni adresse,
ni note de refus de visite. Uniquement des contours de territoires, leur
libellé et une date de restitution. Les notes présentes dans l'export d'origine
sont supprimées à la génération, précisément parce que ce dépôt est public.

## Génération

Les fichiers sont produits par `generate_kml.py` à partir des exports CSV et KML
de Territory Helper. Ils ne doivent pas être modifiés à la main : toute
modification serait écrasée à la prochaine exécution.
