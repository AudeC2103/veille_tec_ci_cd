
# Rapport de Recherche : CI/CD (Continuous Integration/Continuous Deployment)

SOMMAIRE
## Introduction
## 1. Historique et évolution
  ### 1. Origine de l'intégration continue
  ### 2. Evolution vers le déploiement continue
  ### 3. Perspectives futures
## 2. Concepts de CI/CD
  ### 1. Integration Continue (CI)
  ### 2. Déploiement Continue (CD)
## 3. Outils de CI/CD Populaires
  ### 1. Outils d'Intégration Continue (CI)**
  ### 2. Outils de Déploiement Continu (CD)**
  ### 3. Outils de Gestion de Configuration**
  ### 4. Outils de Monitoring et Feedback**
  ### 5. Outils de Gestion de Projet et Documentation**
## 4. Pipelines de build et de déploiement automatisé
  ### 1. Processus du pipeline de build dans le CI
  ### 2. Processus du pipeline de déploiement dans le CD
## 5. Tests Automatisés et Intégration Continue
  ### 1. Importance des Tests Automatisés
  ### 2. Mise en Place de l'Intégration Continue
## Conclusion

---

## Introduction

Dans le monde du développement logiciel moderne, la rapidité et la fiabilité des livraisons de code sont devenues cruciales. 
Les utilisateurs finaux s'attendent à des mises à jour fréquentes et sans interruption, tandis que les développeurs doivent jongler avec des cycles de développement rapides et des exigences de qualité élevées. 
C'est ici que les pratiques de CI/CD (Continuous Integration/Continuous Deployment) entrent en jeu. 
La CI/CD représente une série de principes et de pratiques permettant d'automatiser et d'optimiser les processus de développement, de test et de déploiement du code. 
Pour les développeurs front-end, comprendre et intégrer ces concepts est essentiel pour garantir une collaboration fluide avec les équipes back-end et assurer des livraisons de logiciels efficaces et de haute qualité. 
Ce rapport vise à expliquer les concepts de CI/CD, à présenter les outils les plus populaires, et à illustrer leur importance à travers des exemples concrets et des configurations pratiques. 

## 1. Historique et évolution

### 1. Origines de l'Intégration Continue (CI)

- **Années 1990 - Pratiques de Développement Traditionnelles et début de l'Extreme Programming (XP):**
  - Avant l'adoption généralisée des méthodes agiles et de l'intégration continue, le développement logiciel suivait souvent des modèles en cascade. Les développeurs travaillaient sur des branches distinctes pendant de longues périodes avant d'intégrer leurs modifications dans la branche principale. Le rythme de mise en production d’une application était d’environ une mise à jour majeure tous les 3 à 6 mois.
  - **1991 :** Grady Booch introduit le concept d'intégration continue dans son livre "Object-Oriented Analysis and Design with Applications". Bien que la pratique ne soit pas encore formalisée, l'idée d'intégrer régulièrement les changements de code est suggérée.
  - **1996 :** Kent Beck développe l'Extreme Programming (XP) pendant qu'il travaillait sur le projet Chrysler Comprehensive Compensation System (C3). XP est une méthodologie de développement logiciel agile, fondée sur des principes qui visent à améliorer la qualité du logiciel et la réactivité aux changements. Kent Beck a ensuite publié son livre "Extreme Programming Explained" en 1999, ce qui a popularisé la méthodologie et l'a introduite à un public plus large. Voici les principaux aspects de l'XP :
    - **Itérations Courtes :** XP encourage des cycles de développement très courts, appelés itérations, généralement d'une à deux semaines. À la fin de chaque itération, une verson fonctionnelle du logiciel est produite.
    - **Tests Unitaires :** Une pratique centrale de l'XP est l'écriture de tests unitaires automatisés avant même que le code ne soit écrit. Les tests sont exécutés régulièrement pour s'assurer que les modifications apportées n'introduisent pas de régressions.
    - **Programmation en Binôme :** Les développeurs travaillent en binômes, où l'un écrit le code tandis que l'autre observe, examine et offre des suggestions. Ce style favorise la collaboration, améliore la qualité du code et partage les connaissances au sein de l'équipe.
    - **Intégration Continue :** XP promeut l'intégration continue (CI), où les modifications de code sont intégrées fréquemment dans le système principal. Cela réduit les conflits d'intégration à long terme et permet une détection précoce des erreurs.
    - **Client Présent :** Un représentant du client est impliqué de manière active tout au long du processus de développement. Cela garantit que les besoins du client sont constamment pris en compte et que le logiciel développé répond efficacement aux exigences du marché.
    - **Refactoring Continu :** Le refactoring (la réorganisation du code sans en changer le comportement externe) est une pratique constante pour maintenir la flexibilité du code et améliorer sa lisibilité.
    - **Design Simplicity :** XP encourage la simplicité dans la conception du logiciel. Plutôt que de prévoir des fonctionnalités futures hypothétiques, l'accent est mis sur la création d'une solution qui répond immédiatement aux besoins présents.
    - **Collective Ownership :** Tous les membres de l'équipe sont responsables de l'ensemble du code base. Cela encourage la collaboration, la relecture de code et l'amélioration continue.

- **Années 2000 - Adoption intiale : Manifeste Agile et 1er outils CI :**
  -  **2000 :** Kent Beck et Martin Fowler popularisent l'intégration continue en tant que pratique clé de l'Extreme Programming (XP). Le livre "Continuous Integration" de Martin Fowler décrit les principes et les pratiques associées.
  -  **2001 :**
    - le Manifeste Agile est publié, promouvant des pratiques de développement logiciel plus collaboratives et itératives. L'intégration continue devient un élément central des méthodologies agiles. 
  En effet le Manifeste Agile, publié par un groupe de développeurs de logiciels, a formalisé un ensemble de valeurs et de principes pour guider le développement logiciel agile. Les valeurs fondamentales du Manifeste Agile sont :
      - Individus et interactions plutôt que processus et outils.
      - Logiciel opérationnel plutôt que documentation exhaustive.
      - Collaboration avec le client plutôt que négociation de contrat.
      - Répondre au changement plutôt que suivre un plan.
Ces valeurs ont favorisé une approche plus flexible, itérative et collaborative du développement de logiciels, par opposition aux méthodes traditionnelles en cascade.
    - CruiseControl, l'un des premiers outils d'intégration continue open-source, est lancé par ThoughtWorks. Cet outil aide les équipes à automatiser le processus de build et à intégrer régulièrement les changements de code.
  - **2005 :** Hudson, un autre outil d'intégration continue open-source, est créé. Il deviendra plus tard Jenkins après un fork en 2011 en raison de divergences de la communauté avec Oracle, qui avait acquis Sun Microsystems (propriétaire initial de Hudson). Il est devenu l'un des outils les plus populaires pour l'intégration continue grâce à sa facilité d'utilisation et à sa flexibilité.

- **Années 2010 - Innovations clés  :**
  -  **2010 :** Travis CI est lancé, offrant une solution d'intégration continue basée sur le cloud, ce qui facilite l'adoption de la CI pour les projets open-source hébergés sur GitHub
  -  **2011 :** GitLab CI est introduit, intégrant l'intégration continue directement dans la plateforme de gestion de code GitLab
  -  **2014 :** CircleCI est lancé, offrant une autre solution d'intégration et de déploiement continu (CI/CD) basée sur le cloud.
 
- **Années 2020 - Progression Technologique :**
  - **2020 :**
    - GitHub Actions est largement adopté, permettant aux développeurs d'automatiser leurs workflows directement à partir de GitHub, y compris les pipelines CI/CD.
    - L'intégration continue s'est étendue à Kubernetes, facilitant des déploiements plus rapides et une gestion améliorée des environnements de développement.
  - **2021 :** améliorations des outils existant : Jenkins, GitLab CI/CD, CircleCI et Travis CI ont tous continué à évoluer avec des fonctionnalités améliorées et une meilleure intégration cloud.
  - **2022 :** Focus sur la Sécurité : Une augmentation des efforts pour intégrer la sécurité dans les pipelines CI/CD, avec l'adoption de scanners de sécurité automatisés et de tests de vulnérabilité.

### 2. Évolution vers le Déploiement Continu (CD)

- **2009 :** **Adoption intiale** Jez Humble et David Farley introduise la notion de déploiement continu dans leur livre "Continuous Delivery".
- **Années 2010 - CI/CD et DevOps :**
  Avec l'adoption croissante des pratiques CI, l'industrie a commencé à se concentrer sur le déploiement continu (CD). Le CD vise à automatiser non seulement l'intégration, mais aussi le déploiement du code en production.
  - **2010 :** Développement de pratiques de déploiement continu avec l'émergence de plateformes cloud comme AWS Elastic Beanstalk.
  - **2011 :** GitLab intègre le déploiement continu dans sa plateforme GitLab CI/CD.
  - **2014 :** Introduction de Docker, facilitant l'utilisation de conteneurs pour le déploiement de logiciels.
    Le mouvement DevOps, qui a émergé au début des années 2010, a joué un rôle crucial dans la promotion de CI/CD. DevOps met l'accent sur la collaboration entre les équipes de développement et d'exploitation pour livrer des logiciels plus rapidement et de manière plus fiable.
  DevOps est une approche qui cherche à unifier le développement de logiciels et les opérations informatiques. Les principaux objectifs de DevOps sont :
    - Accélérer le cycle de développement
    - Améliorer la qualité du logiciel
    - Renforcer la collaboration
    - Augmenter la fiabilité
- **Années 2020 - Progrès dans les Stratégies de Déploiement :**
  - **2020 :** Adoption généralisée des pratiques de CD avec des outils comme Kubernetes, permettant une gestion plus automatisée et flexible des déploiements.
  - **2021 :** Accent accru sur la sécurité dans les pipelines de déploiement continu, avec l'intégration de scanners de sécurité automatisés.
  - **2022 :** Évolution vers des stratégies de déploiement plus sophistiquées comme le déploiement progressif et le rollback automatisé.

### 3. Perspectives futures

  - **Intelligence Artificielle et Machine Learning :** On prévoit que l'intégration de l'IA et du machine learning dans les pipelines CI/CD pourrait se développer pour optimiser les workflows et améliorer la qualité du code.
  - **Expansion de l'Automatisation :** L'automatisation des pipelines CI/CD devrait continuer à croître, avec des innovations dans l'automatisation des tests, des déploiements et de la gestion des infrastructures.
  - **Interopérabilité et Standardisation :** Une meilleure interopérabilité entre les outils CI/CD et une standardisation des pratiques pourraient simplifier l'adoption et l'utilisation de ces technologies pour les équipes de développement.

## 2. Concepts de CI/CD

### 1. Intégration Continue (Continuous Integration - CI)

**C'est quoi**
- Pratique de développement logiciel
- Intégration fréquente du code dans un dépôt partagé
- Vérification par construction et tests automatisés

**Aspects Clés**
- Intégration fréquente : commits multiples par jour
- Construction et tests automatisés : outils comme Jenkins, Travis CI, CircleCI
- Retour d'information immédiat : alertes en cas d'échec
- Contrôle de version : utilisation de VCS (ex. Git)

**But** : 
- Détecter les problèmes tôt
- Réduire les conflits de fusion
- Améliorer la collaboration entre les développeurs.

**Avantages**
- Détection précoce erreurs
- Amélioration de la collaboration
- Cycles de publication plus rapides
- Qualité du code améliorée

**Défis**
- Configuration initiale complexe
- Maintenance continue nécessaire
- Gestion de la complexité dans les grands projets

### 2. Déploiement Continu (Continuous Deployment - CD)

Le déploiement continu va au-delà de l'intégration continue en automatisant le déploiement du code validé en production. Chaque modification validée passe par un pipeline automatisé et, si elle réussit toutes les étapes, est déployée automatiquement.

**C'est quoi**
Automatisation du déploiement > 
des modifications de code
Livraison continue de nouvelles fonctionnalités 
aux utilisateurs

**Aspects Clés**
Pipeline de déploiement automatisé 
Tests automatisés / validation avant déploiement
Déploiements fréquents 
Surveillance et retour d'information > performances > erreurs post-déploiement

**But**
Livrer rapidement et en toute sécurité des fonctionnalités aux utilisateurs finaux

**Avantages**
Temps de mise sur le marché réduit
Retour rapide des utilisateurs
Réduction des risques de déploiement
Amélioration de la qualité logicielle

**Défis**
Infrastructure complexe à mettre en place
Exigence de haute qualité des tests
Nécessité d'une culture DevOps forte
Gestion des déploiements dans des environnements multiples

**Processus** : Comprend des tests automatisés approfondis, des vérifications de sécurité, et des étapes de déploiement.

## 3. Outils de CI/CD Populaires

### Types d'Outils de CI/CD

**1. Outils d'Intégration Continue (CI)**
- **Jenkins** : Serveur d'automatisation open-source pour pipelines CI.
- **Travis CI** : Intégration continue pour projets GitHub, automatise les tests.
- **CircleCI** : Plateforme CI rapide et flexible.
- **Buildkite** : CI/CD performant et scalable, fonctionne sur votre infrastructure.

**2. Outils de Déploiement Continu (CD)**
- **GitLab CI/CD** : Pipelines CI/CD complets intégrés dans GitLab.
- **Spinnaker** : Déploiement continu multi-cloud.
- **Octopus Deploy** : Déploiements sécurisés et répétables.

**3. Outils de Gestion de Configuration**
- **Ansible** : Gestion et automatisation de la configuration.
- **Chef** : Automatisation de l'infrastructure avec des recettes.
- **Puppet** : Gestion cohérente et conforme des systèmes.

**4. Outils de Monitoring et Feedback**
- **Prometheus** : Monitoring et alertes open-source.
- **Grafana** : Visualisation de données et tableaux de bord.
- **Datadog** : Monitoring des performances et analyse des infrastructures.
- **New Relic** : Monitoring des performances en temps réel.

**5. Outils de Gestion de Projet et Documentation**
- **Jira** : Gestion de projets agile et suivi des tâches.
- **Confluence** : Collaboration et documentation centralisées.

**6. Outils de Tests Automatisés**
- **Jest** : Framework de tests JavaScript pour React, développé par Facebook. Simple et rapide.
- **Selenium** : Outil open-source pour automatiser les tests des applications web sur différents navigateurs.
- **JUnit** : Framework de tests pour Java, idéal pour les tests unitaires.
- **Mocha** : Framework de tests JavaScript pour Node.js, flexible et asynchrone.
- **Chai** : Bibliothèque d'assertions pour JavaScript, souvent utilisée avec Mocha.
- **Cypress** : Framework de tests end-to-end pour les applications web, rapide et simple à utiliser.

## 4. Pipelines de build et de déploiement automatisé

Les pipelines d'intégration continue (CI) et de déploiement continu (CD) sont une série d'étapes qui doivent être réalisées pour fournir une nouvelle version du logiciel. Ils sont une pratique visant à dynamiser la livraison de logiciels tout au long du cycle de vie du développement grâce à l'automatisation. Toutes les étapes s'exécutent dans l'ordre les unes après les autres. Si une étape/étape échoue, elle ne passera pas à une autre étape/étape tant que l'étape précédente n'aura pas réussi. 

![image pipeline CI/CD](https://github.com/AudeC2103/veille_tec_ci_cd/assets/166111910/7b97b834-f39a-43c3-9906-f1bb2b148cf1)

### 1. Processus du pipeline de build dans le CI

Les développeurs effectuent des modifications de code, puis les soumettent (**Commit**) et les poussent (**Push**) vers un dépôt central (par exemple : Git)
Chaque commit déclenche le pipeline de build, qui comprend :

#### 1. Compilation :
  Le code source est compilé (Exemple : Transformation du code source C++ en fichiers .exe ou .out). 
  **Étapes de la Compilation** :
  1. **Analyse Lexicale :**
    Le compilateur lit le code source et le décompose en tokens, qui sont les plus petites unités de sens dans le code (mots-clés,   identifiants, opérateurs, etc.).
2. **Analyse Syntaxique :**
     Le compilateur vérifie la structure syntaxique du code en utilisant une grammaire définie pour le langage de programmation. Il s'assure que les instructions sont correctement formées.
   3. **Analyse Sémantique :**
    Le compilateur vérifie que le code a un sens logique (par exemple, que les variables sont correctement déclarées et utilisées).
4. **Optimisation :** 
    Le compilateur améliore le code pour le rendre plus efficace, sans changer son comportement.
   5. **Génération de Code :**
    Le compilateur traduit le code source en code machine ou en bytecode. Le code machine est spécifique au processeur de l'ordinateur, tandis que le bytecode est destiné à une machine virtuelle (comme la JVM pour Java).
#### 2. Exécution des tests unitaires :
  Les tests unitaires sont exécutés pour vérifier le bon fonctionnement des unités de code (fonctions, méthodes) et ainsi valider que les modifications n'introduisent pas de bug.
#### 3. Génération des fichiers de sortie :
   Les fichiers de sortie, comme les binaires ou les images de conteneurs Docker, sont créés. Voici les étapes détaillées :
  1. **Packaging :**
  Le code est empaqueté (par exemple, dans une archive ZIP ou une image Docker).
  2. **Publication des Artefacts :**
  Les binaires et autres fichiers générés sont stockés dans un registre d'artefacts (par exemple, JFrog Artifactory, Nexus).
  L'objectif est de rendre les artefacts disponibles pour le déploiement.
  3. **Notification :**
  Les développeurs sont informés des résultats du pipeline (succès ou échec).

  En cas d'échec, des actions correctives sont entreprises.
  
Le pipeline de build est donc une partie intégrante de la CI. Il se déclenche à chaque fois qu'il y a une modification de code soumise au dépôt central.
![image pipeline CI](https://lh5.googleusercontent.com/O3xnRvZnWtNutz1570FzDEQNPk08mbc7kEABgyv7gLrgZhGsioDdSN-VyUPUVJ2DekIHBboCMwKwrvF-3js4hw3Mteefo-rlFCRiv0JG0Y2xGatLXl5lCpklaDlaF9qN2dSY7ES5)

### 2. Processus du pipeline de déploiement (ou Release Pipeline) dans le CD

Le pipeline de déploiement continu (CD) est un processus automatisé visant à déployer les artefacts validés par le pipeline CI dans divers environnements (staging, production) de manière régulière et fiable.

#### 1. Récupération des artefactes et déploiement sur environnement de staging :
Cette étape consiste à récupérer les artefacts validés par le pipeline CI (comme les binaires ou les images Docker) à partir du registre d'artefacts (par exemple, JFrog Artifactory, Nexus) et à les déployer dans un environnement de test (staging = copie de l'environnement de production) pour s'assurer de leur bon fonctionnement avant de les déployer en production.
 
#### 2. Tests d'Intégration et Validation :
Cette étape inclut l'exécution de tests automatisés d'intégration pour vérifier que tous les composants du système interagissent correctement et éventuellement une validation manuelle pour garantir la qualité et la fiabilité de la nouvelle version.

#### 3. Déploiement en Production et Surveillance :
Les artefacts validés sont déployés dans l'environnement de production, rendant les nouvelles fonctionnalités disponibles pour les utilisateurs finaux. Une surveillance continue des applications est déployées pour détecter rapidement tout problème potentiel et à effectuer un retour en arrière (rollback) si nécessaire (utilisation d'outils de monitoring comme Prometheus et Grafana pour assurer une observabilité complète) avec pour objectif d'assurer la stabilité et la performance des applications en production et réagir rapidement en cas de problèmes.

![image pipeline CI/CD](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*TEIma78T4t4gcpkPo7GqzA.png)

Un pipeline CI/CD permet une mise sur le marché nettement plus rapide des nouvelles fonctionnalités d'un produit. Cela permet de satisfaire davantage les clients et de réduire la tension et le stress liés au développement de logiciels.

## 5. Tests Automatisés et Intégration Continue

### 1. Importance des Tests Automatisés

Les tests automatisés sont cruciaux pour assurer la qualité du code. Ils permettent de détecter rapidement les régressions et les bugs introduits par les nouvelles modifications.

- **Types de tests** : Tests unitaires, tests d'intégration, tests de bout en bout.

### 2. Mise en Place de l'Intégration Continue

Pour mettre en place l'intégration continue, il est nécessaire de configurer un serveur CI/CD (comme Jenkins, GitHub Actions ou GitLab CI) pour surveiller le dépôt de code source et exécuter automatiquement les tests à chaque commit.

- **Processus** : Surveillance des commits, exécution des builds, exécution des tests, génération de rapports.

## Conclusion

  L'implémentation des pipelines CI/CD représente une avancée significative dans le développement logiciel moderne. En automatisant les processus d'intégration et de déploiement, ces pipelines permettent de garantir une livraison continue de code de haute qualité. Comprendre CI/CD permet aux développeurs front-end de mieux collaborer avec les équipes back-end. Cela facilite l'intégration de nouvelles fonctionnalités et assure que les modifications sont déployées en douceur. En automatisant les builds et les tests, les développeurs front-end peuvent se concentrer sur le développement de fonctionnalités et l'amélioration de l'expérience utilisateur. CI/CD assure ainsi une amélioration continue du produit.
     Du côté des clients, l'adoption de CI/CD assure une livraison plus rapide des fonctionnalités tout en maintenant la stabilité et la fiabilité des applications, ce qui se traduit par une satisfaction accrue. En somme, les pipelines CI/CD jouent un rôle crucial en facilitant une collaboration efficace entre les équipes de développement et en assurant des livraisons fréquentes et de qualité aux utilisateurs finaux.

## sources 

- [CI/CD pour les débutants (Video)](https://www.youtube.com/watch?v=1h9_cB9mPT8)
- [Tutoriel Jenkins](https://www.jenkins.io/doc/tutorials/)
- [Tutoriel GitHub Actions](https://docs.github.com/en/actions/learn-github-actions)
- [Tutoriel GitLab CI](https://docs.gitlab.com/ee/ci/tutorials/)
- [Atlassian](https://www.atlassian.com/continuous-delivery/ci-vs-cd)
- [qiminfo](https://www.qiminfo.ch/ci-cd/)
- [Octo](https://blog.octo.com/devops-de-lintegration-continue-au-deploiement-continu)
- [Datascientest](https://datascientest.com/ci-cd-integration-continue-livraison-continue)
- [Geeksforgeeks](https://www.geeksforgeeks.org/difference-between-continuous-integration-and-continuous-delivery/)
- [openreplay](https://blog.openreplay.com/what-is-a-ci-cd-pipeline/)
- [simform](https://www.simform.com/blog/what-is-cicd/)
- [Utor](https://u-tor.com/topic/ci-cd-workflow-and-qa)
- [gartsolution](https://gartsolutions.medium.com/building-an-effective-ci-cd-pipeline-a-comprehensive-guide-bb07343973b7)
  
