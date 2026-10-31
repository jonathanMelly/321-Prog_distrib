# Fil rouge : choisir son scénario

Les [thématiques](../../thematiques/README.md) du module sont **indépendantes du scénario**. Le scénario donne le décor dans lequel on applique, thématique après thématique, ce que les [drills](../drills/README.md) et le [chat](../chat/README.md) ont fait comprendre.

| Scénario | Décor | État | Choisissez-le si… |
|---|---|---|---|
| [UMDD (Dousville)](umdd/README.md) | une ville de boulangeries-pâtisseries, services partagés par la classe | complet | vous voulez un fil rouge **pas encore éprouvé**, collaboratif, langage libre |
| [Powercher](powercher/README.md) | maisons connectées, énergie, « Mère Nature » | repris des activités existantes | vous voulez réutiliser le matériel déjà testé ([powercher_v1](../powercher_v1/README.md), [powerdeal](../powerdeal/README.md), [aie_confiance](../aie_confiance/README.md)) |
| [Pedaloland](pedalo/README.md) | l'industrie du pédalo | esquisse | à réserver à un autre groupe : [Pedaloland.md](../../Pedaloland.md) |

## Ce qui ne change pas

Quel que soit le scénario :

- le [contrat](../contrats/README.md) de base (enveloppe, topics du chat, présence, log) ;
- le [labo Docker](../infra/README.md) ;
- les [drills](../drills/README.md) et le [chat](../chat/README.md) ;
- l'[évaluation](../../evaluation/umdd-v2.md).

## Ce qui change

Les **noms** des services et leurs règles métier (boulangerie, maison, usine à pédalos). La structure est la même : chaque scénario répond aux mêmes questions (qu'est-ce qui s'affiche ? quelle horloge commune ? qui est vivant ? qui paie ? …).

## Mécanisme de sélection (inspiré du module 323)

Le module [323](../../../323-Programmation_fonctionnelle/thematiques/01-paradigmes-fonctionnels.md) fonctionne ainsi : un sélecteur (composant `FilRougeSelector.vue`, état dans `useFilRouge.ts`, lien dynamique `FilRougeLink.vue`) mémorise le scénario choisi, et chaque thématique pointe vers `exos/fil-rouge/<scénario>/<exercice>/`.

Ici, tant que les thématiques sont lues sur GitHub, chaque thématique donne **un lien par scénario**. Si ce dossier est un jour publié avec VitePress comme en 323, il suffira de :

1. copier les trois fichiers du sélecteur ;
2. donner le même nom de fichier à la page de chaque scénario pour une thématique (ex. `log-annuaire.md`) ;
3. remplacer le tableau de liens par `<FilRougeLink ex="log-annuaire.md" label="…"/>`.

(Pour l'instant `powercher` et `pedalo` regroupent leurs thématiques dans un seul README avec ancres (`#serialisation`, `#temps-protocole`, …) ; ils seront éclatés en un fichier par thématique quand ils seront développés.)
