# Contract testing
 
## Le principe :

- Introduction Architecture
  - bcp de services, dont des services externes
  - display a schemas
  - bcp d'interations entre ces services
 
- Problematique (situation puis liste de problèmes) :
  - Situation : estimation de charge de refacto d'API (changement int -> devise)
    - Je ne sais quels services utilisent l'API
    - Je ne sais pas s'il utilise le champs à modifier
  - D'autres problèmes de gestions d'API ?
    - Tester la communication dans le consumer (sans utiliser un vrai env)
    - __/!\ Chercher les problèmatiques __
 
- Principe du contract testing
  - C'est quoi le contract testing ?
    - Definition d'un contrat
    - Vérification du consumer et du producer
  - rôle de mock
  - (CT vs E2E testing : pyramide des tests)
 
- Qui définit le contrat : Consumer vs Producer driven :
  - principes
  - avantages et inconvénient
  - examples d'usages
  - quelques exemples d'outils (Spring cloud contract, Pact, ...)
 
- Ca permet quoi le consumer driven ?
  - Voir les endpoints non/mal utilisés
  - Identifier les consumers
  - ex: micro-services
 
- Producer Driven
  - On ne connait pas les consumers (twitter)
 
## Pact :
 
- Présentation générale :
  - polyglotte (Ruby, JVM, JS, C#, Go, Python)
  -  consumer driven
  -  gestion du versionning
  -  why pact ? Opensource, active community, well documented, polyglotte
 
- Présentation du cas d'usage
  - Notre consumer / producer / format d'échange
  - Notre exemple demande de prix (en entier)
    - Présentation d'un contrat
    - Présentation d'un consumer
    - Présentation du producer
  - Présentation Pact Broker
  - Supprimer un champs inutilisé (stock) -> le test PASS
  - Changer le prix de entier à entier + devise -> Le test explose
  - Retour Pact broker historique + graphique
 
Ouverture :
- Can I deploy : avec le versionning ?
- Messaging ?
 
Some links :
- Pact https://docs.pact.io/
- Refs
https://reflectoring.io/7-reasons-for-consumer-driven-contracts/
https://martinfowler.com/bliki/ContractTest.html
 
## Conclusion
- quand faire du CT ?
  - Sécuriser ses échanges
- quoi tester
  - L'interaction
  - le format d'échange
- ne pas tester ?
  - le métier

# Démo

- 2 consumer un JS, Kotlin
- Un provider Kotlin
- Pact broker

## Initial State
- Présentation contract consumer
- Présentation Test consumer
- Présentation Test Provider
- Exécution des tests
- présentation Pact Broker
    - liste des contracts
    - le dernier contrat éxécuté
    - l'historique des run
    - le réseau des interactions
- Présentation de l'autre contrat

## New Feature
- On modifie le contract JS
- On lance le test du consumer, ça passe
- On lance le test du provider, ça explose
- On corrige, ça passe
- On montre tout ça dans Pact Broker

## A changer 
- 2rd parties
- On test ça
- quand se fait la génération du mock ? => au build
- quand faire du consumer driven => consumer connus et avec lesquels on peut communiquer
- quand faire du producer driven => Prendre l'exemple d'une API publique
- Nommer les autres produits
- Pact broker => carte des interations
- update /api/productS
- Au global en plus gros => EN PLUS GROS
- Dans la démo, remettre la situation par rapport au schéma
- Should find allAccounts renommé en meilleur truc pour le provider
- Mieux expliquer le fonctionnement du broker plutot que ses avantages :
               - Présenter la problématique (storage les contrats)
               - Présenter les solutions possibles
               - Présenter le broker et son fonctionnement avec les graphs
- Pyramide de tests
