# MQTT

Un protocole de messagerie léger, ses garanties de livraison (QoS), ses présences (retain) et ses testaments (LWT).

**À l'issue de cette thématique, vous serez capable de :**
- prédire qui reçoit quoi selon le QoS, la session et le retain
- choisir un protocole (MQTT / REST / RPC) pour un besoin donné et le justifier
- utiliser les wildcards et séparer les flux par topics
- expliquer ce que le broker garantit et ce qu'il ne garantit pas

**Fallacies :** 1 (fiabilité), 2 (latence). Voir [les 8 fallacies](../supports/fallacies.md).

## Théorie
- [MQTT](../supports/mqtt.md)
- [Kahoot A](https://create.kahoot.it/share/mqtt/8545db98-717d-4ecb-9e2f-1349eb200161) · [Kahoot B](https://create.kahoot.it/details/c8177a44-0898-44e5-9c5b-4d72099a28be)

## Drill
- [D03 — MQTT : QoS, session, retain](../activites/drills/D03-qos-retain.md)

## Chat
- [C3 — Présence et messages privés](../activites/chat/C3-presence.md)

## Fil rouge

| Fil rouge  | Activité                                                                        |
|------------|---------------------------------------------------------------------------------|
| UMDD       | [TimeService (premier service sur le bus)](../activites/fil-rouge/umdd/time.md) |
| Powercher  | [Powercher](../activites/fil-rouge/powercher/README.md#temps-protocole)         |
| Pedaloland | [Mapping](../activites/fil-rouge/pedalo/README.md)                              |

Activité historique : [Footchat](../activites/footchat/README.md) (échauffement MQTT)
