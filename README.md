#  Full DevOps E2E Pipeline : Architecture Microservices sur AWS EKS (Socks Shop)

**Projet de Fin d'Études / Solution Démo** illustrant une chaîne de valeur DevOps complète pour une application microservices (Socks Shop), du code source au déploiement de l'infrastructure à l'application.

Ce projet démontre une expertise avancée dans l'**automatisation de l'infrastructure (IaC)**, l'**orchestration des conteneurs (Kubernetes)**, et la mise en œuvre de la **CI/CD (Jenkins)** dans un environnement Cloud **AWS**.

---

##  Stack Technique

Ce projet valide la maîtrise des outils suivants dans un environnement de production simulé :

| Composant | Rôle |
| :--- | :--- |
| **AWS (EKS, VPC, IAM, S3)** | Fournisseur Cloud pour l'infrastructure haute disponibilité. |
| **Terraform** | Conception et provisionnement du cluster Kubernetes (EKS) et des ressources Cloud associées. |
| **Kubernetes (K8s)** | Orchestration des microservices, gestion de l'état (StatefulSets), mise à l'échelle (HPA), et des accès (Ingress). |
| **Helm** | Packaging et déploiement modulaire des applications sur Kubernetes. |
| **Jenkins** | CI/CD Pipeline as Code pour l'automatisation du Build, Test, Scan, Push (Docker Hub) et Déploiement. |
| **Docker** | Conteneurisation de tous les services de l'application. |
| **DevSecOps** | Intégration d'outils de scan de sécurité (Trivy pour les images, Checkov pour l'IaC). |

---

##  Architecture et Organisation

Le dépôt regroupe tous les artefacts nécessaires pour le déploiement E2E (End-to-End) :

* **`infra/`** : Code **Terraform** pour provisionner les prérequis AWS et le cluster EKS.
* **`helm-charts/`** : L'ensemble des charts Helm pour la gestion des microservices, du monitoring et du stockage sur EKS.
* **`frontend/` & `microservices/`** : Le code source et les Dockerfiles de l'application.

---

## Contexte et Rôle Personnel

> Ce projet est issu d'un travail de fin d'études réalisé en binôme sur une solution existante. Pour assurer une **clarté et une propriété sans équivoque** sur mon portfolio, j'ai consolidé le travail final dans ce dépôt.
>
> **Mon Rôle Principal :**
> J'ai conçu et réalisé l'intégralité de la conception de l'**Infrastructure as Code (Terraform)** pour le provisionnement d'AWS EKS. J'ai également contribué de manière essentielle à la conception et à la résolution des problèmes (débuggage) de l'**orchestration Kubernetes (Helm)** et des **pipelines CI/CD (Jenkins)**.
>
> **Maîtrise :** Je suis l'auteur de l'ajout actuel et **je maîtrise l'intégralité des choix d'architecture** ainsi que toutes les modifications apportées aux composants (IaC, K8s, CI/CD). Ce dépôt est désormais le point de référence pour toutes les évolutions futures.

---

##  Améliorations Futures et Amélioration Continue

Ce projet sert de base solide, et mon engagement se poursuit à travers l'exploration et l'intégration des axes d'amélioration suivants, axés sur la **stabilisation**, la **sécurité** et la **qualité opérationnelle** :

1.  **Fiabilisation de l'Observabilité :** Finaliser l'intégration de **Prometheus et Grafana** pour garantir le monitoring fiable des métriques du cluster EKS et des applications, et offrir une vue opérationnelle complète.
2.  **Gestion des Secrets :** Intégrer **HashiCorp Vault** pour remplacer les secrets statiques et centraliser la gestion des credentials, renforçant ainsi la sécurité de l'architecture.
3.  **Optimisations Kubernetes :** Réaliser des ajustements dans les manifestes K8s (Helm charts) pour améliorer la résilience, l'efficacité des ressources (requests/limits) et l'alignement avec les meilleures pratiques.

L'objectif est de toujours maintenir ce dépôt comme une solution de référence, démontrant mon engagement pour l'**amélioration continue** de la qualité logicielle et opérationnelle.
