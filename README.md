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

---
## 📈 Améliorations Futures et Amélioration Continue

Ce projet sert de base solide pour une architecture DevOps complète. Mon engagement se poursuit à travers l'exploration et l'intégration des axes d'amélioration suivants :

1.  **Observabilité Avancée :** Implémentation de Jaeger pour le Tracing distribué afin de monitorer le flux de requêtes à travers l'ensemble des microservices.
2.  **GitOps avec ArgoCD :** Migration de la phase de déploiement (actuellement via Jenkins) vers un modèle GitOps en utilisant ArgoCD pour une gestion du déploiement plus déclarative et résiliente sur Kubernetes.
3.  **Gestion des Secrets :** Remplacement de l'approche actuelle par une solution plus robuste et centralisée telle que **Vault** (HashiCorp) pour la gestion dynamique des secrets de l'application.
4.  **Optimisation des Coûts AWS :** Exploration des stratégies d'optimisation des coûts (Spot Instances, Karpenter) au niveau du cluster EKS.
