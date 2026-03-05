# Portfolio DevSecOps_JobFinderProject
DevSecOps project focused on secure CI/CD pipelines, infrastructure as code, and automated security testing.

# Architecture du Projet
Application déployée sous forme de microservices containerisés :
Utilisateur
     │
     ▼
Frontend (Node.js)
     │
     ▼
Backend (Node.js API)
     │
     ▼
Database

L’ensemble est :
-> Containerisé avec Docker
-> Déployé sur Kubernetes
-> Automatisé via Jenkins Pipeline
-> Sécurisé via des outils DevSecOps

# Stack Technique

| Domaine          | Outil      |
| ---------------- | ---------- |
| Backend          | Node.js    |
| Frontend         | Node.js    |
| Containerisation | Docker     |
| Orchestration    | Kubernetes |
| CI/CD            | Jenkins    |
| Analyse statique | SonarQube  |
| SAST             | Gitleaks   |
| SCA              | Trivy      |
| DAST             | OWASP ZAP  |
| Registry         | DockerHub  |
| Versionning      | GitLab     |


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
