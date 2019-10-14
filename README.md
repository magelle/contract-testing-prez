# Contract testing
nv
## Le principe :

- Introduction Architecture
               * bcp de services, dont des services externes
               * bcp d'interations entre ces services

- Problematique :
               * Qui utilise ? Quelle API / version ?
               * difficulté a mesurer les impacts d'un refacto de producer ou consumer

- Principe du contract testing :
               * quand faire du CT ?
               * quoi tester / ne pas tester ?
               * rôle de mock
               * CT vs E2E testing : pyramide des tests

- Consumer vs producer driven :
               * principes
               * comment choisir entre les deux
               * quelques exemples d'outils

- Ca permet quoi le consumer driven ?
               * Voir les endpoints non/mal utilisés
               * Identifier les consumers
               * ex: micro-services

- Producer Driven
    * On ne connait pas les consumers (twitter)
    *

- Avantages/inconvénients
 

## Pact :

- Présentation générale :
               * polyglotte
               * state
               * consumer driven
               * gestion du versionning
               * why pact ? Opensource, active community, well documented, polyglotte

- Ecriture d'un consumer
- Ecriture du producer
- broker
- Second Producer (avec visu sur le broker)
- Passage des tests
- Modif du producer et explosion !

Ouverture :
- Can I deploy : avec le versionning
- Messaging

Some links :
- Pact https://docs.pact.io/
- Refs
https://reflectoring.io/7-reasons-for-consumer-driven-contracts/
https://martinfowler.com/bliki/ContractTest.html

