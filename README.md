# CI-CD4CE
CI / CD pour Compliance Eye

L'objectif de ce projet est de mettre en place une approche CI/CD pour un projet Laravel à déployer sur un VPS.


Ce projet nécessite deux parties distinctes, notamment la partie lié à la configuration qui servira à déployer le projet sur le serveur de chaque client. Il me reviendra à mettre en place un script de déploiement automatique qui sera lancé sur le serveur du client afin de déployer le projet. Cette partie sera appelé SETUP, et le projet lui meme sera appelé PROJET.

Je dois donc mettre en place un processus CI/CD pour le PROJET lui même.
Je dois simplement versionné la partie setup, qui servira lors de chaque déploiement chez le client. La version sur nos serveurs permettra de valider les test, et passer en production, la version stable qui peut servir pour les demo.

Ceci me permettra de garder un suivi de version, et d'assurer l'intégration continue, et le déploiement continu.
Nous aurons un environnement de test et un environnement de prod.

Je vais utiliser github action pour l'intégration continue et les test, 
et j'utiliserai Jenkins pour le déploiement continue.

Mes pipelines pour le projet seront les suivants :
- Laravel_ci.yaml (Github Actions) => Pipiline d'intégration continue
- Jenkinsfile (Jenkins) => Pipiline de déploiement continu

Mon pipeline CI se termine un job qui déclenche mon pipeline CD

Je vais faire usage des secrets pour mes différents mot de passe du serveur.

Je vais ajouter des notifications sur slack à chaque déploiement.