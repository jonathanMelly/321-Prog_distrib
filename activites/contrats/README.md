# Contrat Dousville

Seule source de vérité entre les participants. **Aucun code n'est fourni**, quel que soit le langage : vous lisez le contrat, vous implémentez.  
Le contrat grandit au fil des [thématiques](../../thematiques/README.md). Les contrats de l'annuaire, de la banque et de la coopérative sont **écrits par la classe** (voir plus bas).

## Transport

| Élément | Valeur |
|---|---|
| Broker (labo local) | `localhost:1883` direct, `localhost:1884` via proxy, voir [infra](../infra/README.md) |
| Broker (classe) | `mqtt.blue.section-inf.ch:1883` |
| Encodage | UTF-8, JSON ; un message MQTT = une enveloppe |
| Racine des topics | `dousville/` |

## Topics

| Topic | `type` | Thématique | QoS | Retain | Rôle |
|---|---|---|---|---|---|
| `dousville/vitrine/<bp>` | `business` | [Sérialisation](../../thematiques/01-serialisation.md) | 1 | oui | la vitrine d'une BP |
| `dousville/chat/all` | `chat` | [Sérialisation](../../thematiques/01-serialisation.md) | 0 | non | message à tous |
| `dousville/chat/dm/<destinataire>` | `chat` | [MQTT](../../thematiques/03-mqtt.md) | 1 | non | message privé |
| `dousville/presence/<bp>` | `presence` | [MQTT](../../thematiques/03-mqtt.md) | 1 | oui | ouverte, fermée ou morte (LWT) |
| `dousville/time` | `time` | [Temps](../../thematiques/02-temps.md) | 0 | non | heure de Dousville |
| `dousville/log/<bp>` | `log` | [Microservices](../../thematiques/04-microservices.md) | 0 | non | journal d'une BP |

## Enveloppe

Tout message est une enveloppe ([schéma](envelope.schema.json)) :

| Champ | Rôle | Exploité en |
|---|---|---|
| `v` | version du contrat (`1`) | Sérialisation (évolution) |
| `id` | UUID unique du message | Idempotence |
| `from` | nom de la BP émettrice | Sécurité (confiance) |
| `to` | destinataire, ou `*` | adressage |
| `ts` | UTC, ISO 8601 | Temps |
| `type` | nom du schéma du `payload` | Sérialisation (validation) |
| `payload` | contenu, selon `type` | |

Exemple :

```json
{"v":1,"id":"0b5f5c0e-3a52-4c58-9b0e-5a3f2b1a9c11","from":"alice","to":"*",
 "ts":"2026-11-02T08:15:30Z","type":"chat","payload":{"text":"salut"}}
```

## Règles

1. Un message qui ne valide pas contre son schéma est **ignoré et loggé**. Il ne fait jamais planter un service.
2. On est **strict en émission, tolérant en réception** : un champ inconnu dans un payload est ignoré, un champ obligatoire absent rend le message invalide.
3. Une BP ne publie que sous son propre nom (`from`), jusqu'à ce que la thématique Sécurité nous donne le moyen de le prouver.

## Schémas

[envelope](envelope.schema.json) · [chat](chat.schema.json) · [business](business.schema.json) · [presence](presence.schema.json) · [time](time.schema.json) · [log](log.schema.json)

Valider sans écrire de code : n'importe quel validateur JSON Schema (draft 2020-12), en ligne ou en bibliothèque de votre langage.

## Contrats écrits par la classe (Microservices, Idempotence et Transactions)

L'annuaire, la coopérative et la banque n'ont **pas** de schéma fourni. Chaque groupe de service :

1. propose ses topics, ses `type` et ses schémas dans une pull request sur ce dossier ;
2. les autres groupes la relisent (un contrat ambigu = un service inutilisable) ;
3. le contrat est fusionné **avant** que les groupes clients ne codent.

Le prof peut jouer le client d'un service pour vérifier qu'un contrat est suffisant.
