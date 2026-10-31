# Transactions

Quand une opération touche deux services qui ne se font pas confiance, comment rester cohérent ?

**À l'issue de cette thématique, vous serez capable de :**
- décrire les états intermédiaires d'une opération qui touche deux services
- distinguer transaction distribuée et saga
- concevoir une compensation
- expliquer le rôle de l'idempotence dans une transaction

**Fallacies :** 1 (fiabilité), 6 (plusieurs administrateurs). Voir [les 8 fallacies](../supports/fallacies.md).

## Théorie
- [Transaction](../supports/transaction.md)

## Drill
- [D06 — Transaction : Fair Trade quand la banque plante](../activites/drills/D06-transaction.md)

## Chat
- (pas d'étape de chat dédiée : la déduplication de [C5](../activites/chat/C5-doublons.md) est le prérequis)

## Fil rouge

| Fil rouge  | Activité                                                                         |
|------------|----------------------------------------------------------------------------------|
| UMDD       | [Banque, coopérative, Fair Trade](../activites/fil-rouge/umdd/banque-coop.md)    |
| Powercher  | [Powercher](../activites/fil-rouge/powercher/README.md#idempotence-transactions) |
| Pedaloland | [Mapping](../activites/fil-rouge/pedalo/README.md)                               |

Activité historique : [Transat : transaction distribuée](../activites/transat/README.md)
