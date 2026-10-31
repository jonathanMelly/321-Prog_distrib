# Résilience (design for failure)

Comment faire en sorte que les pannes soient une donnée contextuelle plutôt qu'une source de désastre ?

**À l'issue de cette thématique, vous serez capable de :**
- choisir entre échec rapide, mode dégradé et nouvelle tentative
- implémenter un backoff exponentiel avec jitter et justifier son plafond
- expliquer le disjoncteur (circuit breaker)
- décrire un arrêt propre (graceful shutdown)

**Fallacies :** 1 (fiabilité), 2 (latence). Voir [les 8 fallacies](../supports/fallacies.md).

## Théorie
- [Design for failure](../supports/design4failure.md)
- [Kahoot P2P / design for failure](https://create.kahoot.it/share/p2p-et-resilience-des-reseaux/20a4a666-6729-4382-8a91-aa8eb8ec1984)

## Drill
- [D07 — Retry : backoff et jitter aux dés](../activites/drills/D07-retry.md)

## Chat
- [C6 — Survivre à la coupure du broker](../activites/chat/C6-reconnexion.md)

## Fil rouge

| Fil rouge  | Activité                                                           |
|------------|--------------------------------------------------------------------|
| UMDD       | [Annuaire en cluster](../activites/fil-rouge/umdd/cluster.md)      |
| Powercher  | [Powercher](../activites/fil-rouge/powercher/README.md#resilience) |
| Pedaloland | [Mapping](../activites/fil-rouge/pedalo/README.md)                 |
