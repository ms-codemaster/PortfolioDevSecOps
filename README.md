# PortfolioDevSecOps
DevSecOps project focused on secure CI/CD pipelines, infrastructure as code, and automated security testing.
DevSecOps Portfolio – JobFinder Dashboard

Ce projet démontre la mise en place d'une chaîne DevSecOps complète autour d’une application Node.js composée d’un frontend et d’un backend.

L’objectif est de montrer comment automatiser le cycle de vie complet d’une application moderne, depuis l’analyse du code jusqu’au déploiement sécurisé sur Kubernetes, en intégrant des outils de sécurité, qualité et automatisation CI/CD.

Le pipeline met en œuvre les pratiques DevSecOps en intégrant la sécurité à chaque étape du cycle de développement.

# Structure du projet
jobfinderproject
│
├── backend
│   ├── Dockerfile
│   └── code backend Node.js
│
├── frontend
│   ├── Dockerfile
│   └── code frontend Node.js
│
├── k8s
│   ├── namespace.yaml
│   ├── backend-deployment.yaml
│   ├── backend-service.yaml
│   ├── frontend-deployment.yaml
│   ├── frontend-service.yaml
│   ├── mongo-deployment.yaml
│   ├── mongo-pvc.yaml
│   └── mongo-service.yaml
│
├── Jenkinsfile
│
└── README.md

# Pipeline CI/CD – Jenkins
Le pipeline automatise tout le processus :
1/ Git Clone
2/ SAST Scan (Gitleaks)
3/ SCA Scan (Trivy)
4/ Build Docker Images
5/ Scan des images Docker
6/ Analyse SonarQube
7/ Quality Gate
8/ Push DockerHub
9/ Déploiement Kubernetes
10/Rollback automatique si erreur
11/Scan DAST avec OWASP ZAP
12/Notification Email
