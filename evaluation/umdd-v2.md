# Évaluation — parcours UMDD v2

L'IA est permise **si on comprend**. L'évaluation mesure la compréhension, pas la production.

## Deux pistes

À chaque checkpoint ou épreuve, la piste est attribuée (ou tirée) par l'enseignant.

### Piste Code
On donne un code qui contient un défaut lié à une [fallacy](../supports/fallacies.md) (doublon traité deux fois, retry sans backoff, `ts` utilisé pour l'ordre, signature qui ne couvre pas tout…).  
L'élève **explique** (nomme le défaut, la fallacy, le scénario de panne) puis **corrige**.

### Piste Feature
On donne une user story. L'élève rédige le **prompt** qu'il donnerait à une IA. Le prompt est noté :

| Critère               | Attendu                                                                                                                                       |
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| Concepts              | nomme les notions de théorie utiles (QoS, idempotence, LWT, signature…)                                                                       |
| Fallacy               | nomme la fallacy menaçante et ce qui l'illustre                                                                                               |
| Panne                 | précise le comportement en cas d'échec (timeout, doublon, nœud mort)                                                                          |
| Critère d'acceptation | décrit un test vérifiable, conforme au [contrat](../activites/contrats/README.md), reproductible avec le [labo](../activites/infra/README.md) |

Puis l'élève exécute le résultat et **explique 3 minutes un passage tiré au hasard** du code généré.

## Barème indicatif
Chaque tâche sur 4 : compréhension (2) · justesse (1) · communication (1). Un code non expliqué vaut 0 sur la compréhension, même s'il fonctionne.

## Rattachement aux compétences
Chaque tâche est étiquetée avec une ou deux bandes de la [matrice](matrice%20des%20compétences.md) (A2, C1, D1/D2, E1, F1) et un niveau B/I/A.

## Format
- **Checkpoints** : Forms de 10 min en fin de bloc de thématiques, voir [modalités](modalites.md). Théorie + une mini-tâche de piste Code.
- **Évaluation finale** : l'épreuve prévue au [planning](../planning/README.md), individuelle, en classe, IA permise. Pas de rendu sans défense orale.
- **NOTES.md** du [chat](../activites/chat/README.md) : sert de support à l'oral (« ce que j'ai compris / ce qui a cassé »).
- Conséquence : l'ancien « ne rien pousser, acheter de l'aide » ne s'applique pas à ce parcours.

## Banque d'énoncés

À préparer par l'enseignant. Une ligne par fallacy ; chaque idée existe en piste *feature* (user story) et en piste *code* (défaut à trouver).

| Fallacy | Piste Feature : user story | Piste Code : défaut planté |
|---|---|---|
| 1 fiabilité | « Un transfert doit être exécuté exactement une fois, même si la banque plante » | doublon traité deux fois (pas de déduplication), retry avec un nouvel `id` |
| 2 latence | « Le client doit afficher l'état même si le service est lent » | appel sans timeout qui bloque l'interface |
| 3 bande passante | « La vitrine ne doit pas saturer le réseau » | image non réduite, republiée toutes les secondes |
| 4 réseau sûr | « Seul le titulaire peut consulter son solde » | `from` pris pour argent comptant, signature qui ne couvre pas tous les champs |
| 5 topologie | « Un nouveau service doit être découvert sans reconfigurer les autres » | adresse du service écrite en dur |
| 6 plusieurs administrateurs | « Une équipe change son format de message sans casser les autres » | récepteur strict qui rejette un champ inconnu |
| 7 coût | « Le capteur doit tenir 3 mois sur batterie » | publication toutes les secondes sans nécessité |
| 8 homogène | « Un client Python doit lire les messages d'un service Java » | sérialisation dépendante du langage ou de la machine |
| heure | « Les messages doivent s'afficher dans l'ordre de la conversation » | tri par `ts` local sans correction |
