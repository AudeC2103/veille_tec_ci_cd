
# Rapport de Recherche : CI/CD (Continuous Integration/Continuous Deployment)

## SOMMAIRE
### Introduction
### 1. Historique et évolution
  #### 1. Origine de l'intégration continue
  #### 2. Evolution vers le déploiement continue
  #### 3. Perspectives futures
### 2. Concepts de CI/CD
  #### 1. Integration Continue (CI)
  #### 2. Déploiement Continue (CD)
### 3. Outils de CI/CD Populaires
  #### 1. Jenkins
  #### 2. GitHub Action
  #### 3. GitLab CI
### 4. Pipelines de build et de déploiement automatisé
  #### 1. Processus du pipeline de build dans le CI
  #### 2. Processus du pipeline de déploiement dans le CD
### 5. Tests Automatisés et Intégration Continue
  #### 1. Importance des Tests Automatisés
  #### 2. Mise en Place de l'Intégration Continue


## Introduction

L'objectif de ce rapport est de fournir une compréhension claire et accessible des concepts de CI/CD (Continuous Integration/Continuous Deployment) pour les développeurs front-end. CI/CD est une pratique essentielle qui automatise le processus de développement, de test et de déploiement, améliorant ainsi la qualité et la rapidité des livraisons de logiciels.

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
    - Le Manifeste Agile est publié, promouvant des pratiques de développement logiciel plus collaboratives et itératives. L'intégration continue devient un élément central des méthodologies agiles. 
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

L'intégration continue est une pratique de développement où les développeurs intègrent régulièrement leur code dans un dépôt centralisé. Chaque intégration est vérifiée par une compilation automatique, permettant de détecter rapidement les erreurs.

- **But** : Détecter les problèmes tôt, réduire les conflits de fusion, et améliorer la collaboration entre les développeurs.
- **Processus** : Inclut l'exécution de tests automatisés et la vérification du code.

\`\`\`yaml
#### Exemple de configuration de Jenkins pour l'intégration continue
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'make build'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'make test'
            }
        }
    }
}
\`\`\`

### 2. Déploiement Continu (Continuous Deployment - CD)

Le déploiement continu va au-delà de l'intégration continue en automatisant le déploiement du code validé en production. Chaque modification validée passe par un pipeline automatisé et, si elle réussit toutes les étapes, est déployée automatiquement.

- **But** : Livrer rapidement et en toute sécurité des fonctionnalités aux utilisateurs finaux.
- **Processus** : Comprend des tests automatisés approfondis, des vérifications de sécurité, et des étapes de déploiement.

\`\`\`yaml
##### Exemple de configuration GitHub Actions pour le déploiement continu
name: CI/CD Pipeline

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set up Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '14'

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test

      - name: Deploy to production
        run: npm run deploy
        if: success()
\`\`\`


## 3. Outils de CI/CD Populaires

### 1. Jenkins

Jenkins est un serveur open-source d'automatisation qui permet de mettre en place des pipelines de CI/CD. Il est très extensible grâce à ses nombreux plugins.

- **Caractéristiques** : Open-source, extensible, large communauté.
- **Cas d'utilisation** : Automatisation des builds, tests et déploiements.

### 2. GitHub Actions

GitHub Actions permet d'automatiser les workflows directement depuis le dépôt GitHub. Il est intégré à l'écosystème GitHub et permet de créer des pipelines CI/CD à l'aide de fichiers YAML.

- **Caractéristiques** : Intégré à GitHub, facile à configurer, large éventail d'actions.
- **Cas d'utilisation** : Automatisation des tests, des builds et des déploiements.

### 3. GitLab CI

GitLab CI est intégré à GitLab et permet de configurer des pipelines CI/CD directement depuis le dépôt. Il offre des fonctionnalités avancées telles que la gestion des runners et le monitoring des pipelines.

- **Caractéristiques** : Intégré à GitLab, complet, gestion des runners.
- **Cas d'utilisation** : Automatisation complète du cycle de vie des applications.

## 4. Pipelines de build et de déploiement automatisé

Les pipelines d'intégration continue (CI) et de déploiement continu (CD) sont une série d'étapes qui doivent être réalisées pour fournir une nouvelle version du logiciel. Ils sont une pratique visant à dynamiser la livraison de logiciels tout au long du cycle de vie du développement grâce à l'automatisation. Toutes les étapes s'exécutent dans l'ordre les unes après les autres. Si une étape/étape échoue, elle ne passera pas à une autre étape/étape tant que l'étape précédente n'aura pas réussi. 

![image pipeline CI/CD](https://github.com/AudeC2103/veille_tec_ci_cd/assets/166111910/7b97b834-f39a-43c3-9906-f1bb2b148cf1)

### 1. Processus du pipeline de build dans le CI

#### Commit et Push :
Les développeurs effectuent des modifications de code, puis les soumettent et les poussent vers un dépôt central (par exemple : Git)
#### Pipeline de build : 
Chaque commit déclenche le pipeline de build, qui comprend :
  ##### 1. Compilation :
  Le code source est compilé (Exemple : Transformation du code source C++ en fichiers .exe ou .out). 
  **Étapes de la Compilation** :
  ###### 1. Analyse Lexicale:
    Le compilateur lit le code source et le décompose en tokens, qui sont les plus petites unités de sens dans le code (mots-clés,   identifiants, opérateurs, etc.).
  ###### 2. Analyse Syntaxique :
     Le compilateur vérifie la structure syntaxique du code en utilisant une grammaire définie pour le langage de programmation. Il s'assure que les instructions sont correctement formées.
  ###### 3. Analyse Sémantique :
    Le compilateur vérifie que le code a un sens logique (par exemple, que les variables sont correctement déclarées et utilisées).
  ###### 4. Optimisation : 
    Le compilateur améliore le code pour le rendre plus efficace, sans changer son comportement.
  ###### 5. Génération de Code :
    Le compilateur traduit le code source en code machine ou en bytecode. Le code machine est spécifique au processeur de l'ordinateur, tandis que le bytecode est destiné à une machine virtuelle (comme la JVM pour Java).
  ##### 2. Exécution des tests unitaires :
  Les tests unitaires sont exécutés pour vérifier le bon fonctionnement des unités de code (fonctions, méthodes) et ainsi valider que les modifications n'introduisent pas de bug.
  ##### 3. Génération des fichiers de sortie :
   Les fichiers de sortie, comme les binaires ou les images de conteneurs Docker, sont créés. Voici les étapes détaillées :
  ##### 1. Packaging :
  Le code est empaqueté (par exemple, dans une archive ZIP ou une image Docker).
  ##### 2. Publication des Artefacts :
  Les binaires et autres fichiers générés sont stockés dans un registre d'artefacts (par exemple, JFrog Artifactory, Nexus).
  L'objectif est de rendre les artefacts disponibles pour le déploiement.
  ##### 3. Notification :
  Les développeurs sont informés des résultats du pipeline (succès ou échec).
  En cas d'échec, des actions correctives sont entreprises.
  
Le pipeline de build est donc une partie intégrante de la CI. Il se déclenche à chaque fois qu'il y a une modification de code soumise au dépôt central.

### 2. Processus du pipeline de déploiement (ou Release Pipeline) dans le CD

Le pipeline de déploiement continu (CD) est un processus automatisé visant à déployer les artefacts validés par le pipeline CI dans divers environnements (staging, production) de manière régulière et fiable.


- **Étapes typiques** : Déploiement sur un environnement de staging, exécution des tests d'intégration, déploiement en production.


Un pipeline CI/CD permet une mise sur le marché nettement plus rapide des nouvelles fonctionnalités d'un produit. Cela permet de satisfaire davantage les clients et de réduire la tension et le stress liés au développement de logiciels.

## 5. Tests Automatisés et Intégration Continue

### 1. Importance des Tests Automatisés

Les tests automatisés sont cruciaux pour assurer la qualité du code. Ils permettent de détecter rapidement les régressions et les bugs introduits par les nouvelles modifications.

- **Types de tests** : Tests unitaires, tests d'intégration, tests de bout en bout.

### 2. Mise en Place de l'Intégration Continue

Pour mettre en place l'intégration continue, il est nécessaire de configurer un serveur CI/CD (comme Jenkins, GitHub Actions ou GitLab CI) pour surveiller le dépôt de code source et exécuter automatiquement les tests à chaque commit.

- **Processus** : Surveillance des commits, exécution des builds, exécution des tests, génération de rapports.

## Conclusion

### Importance pour les Développeurs Front-end

**1. Collaboration avec les équipes Back-end**

Comprendre CI/CD permet aux développeurs front-end de mieux collaborer avec les équipes back-end. Cela facilite l'intégration de nouvelles fonctionnalités et assure que les modifications sont déployées en douceur.

**2. Automatisation des tâches répétitives**

En automatisant les builds et les tests, les développeurs front-end peuvent se concentrer sur le développement de fonctionnalités et l'amélioration de l'expérience utilisateur.

**3. Livraison continue de fonctionnalités**

CI/CD permet de livrer rapidement des nouvelles fonctionnalités aux utilisateurs, assurant ainsi une amélioration continue du produit.

La mise en place de CI/CD permet d'améliorer significativement la qualité et la rapidité des livraisons de logiciels. En automatisant les processus de build, de test et de déploiement, les équipes de développement peuvent se concentrer sur l'ajout de valeur plutôt que sur des tâches répétitives et sujettes à erreur. Pour les développeurs front-end, comprendre ces concepts et outils est essentiel pour collaborer efficacement avec les équipes back-end et assurer une livraison de logiciels fluide et de haute qualité.

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
  
