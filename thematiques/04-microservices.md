# Microservices

![Architecture.png](assets/Architecture.png)

Découper en services qui se parlent par messages, chacun avec son équipe et son contrat. Et accepter que les services meurent.

**À l'issue de cette thématique, vous serez capable de :**
- décrire le rôle d'un microservice et ce que lui coûte un voisin défaillant
- annoncer sa mort avec un LWT et expliquer le délai de détection d'une mort silencieuse
- co-écrire un contrat de service avec d'autres équipes
- implémenter un service d'annuaire et un service de journal

**Fallacies :** 1 (fiabilité), 5 (topologie), 6 (un seul administrateur). Voir [les 8 fallacies](../supports/fallacies.md).

## Théorie
- [Microservices](../supports/microservice.md)
- [Récap Kahoot NTP, sérialisation, microservices](https://create.kahoot.it/share/ntp-serialisation-et-microservice/1fdb114c-757c-4d9f-9fa5-b1310f47c90e)
- Rappel MQTT : [LWT](../supports/mqtt.md#last-will-and-testament-lwt) et [Keep-Alive](../supports/mqtt.md#keep-alive)

## Drill
- [D04 — Mort d'un nœud : LWT et keep-alive](../activites/drills/D04-mort-noeud.md)

## Chat
- [C4 — Annoncer sa propre mort](../activites/chat/C4-mort.md)

## Fil rouge

| Fil rouge  | Activité                                                              |
|------------|-----------------------------------------------------------------------|
| UMDD       | [Log et annuaire](../activites/fil-rouge/umdd/log-annuaire.md)        |
| Powercher  | [Powercher](../activites/fil-rouge/powercher/README.md#microservices) |
| Pedaloland | [Mapping](../activites/fil-rouge/pedalo/README.md)                    |
