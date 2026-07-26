# Self-Healing Infrastructure Project 

## Overview
A cutting-edge Kubernetes application showcasing self-healing capabilities with GitOps, observability, and chaos engineering. Built for production resilience and developer efficiency.

## 📂 Project Structure
```bash
self-healing-infrastructure/
├── app/          # Flask app source code
├── docker/       # Dockerfiles and container config
├── kubernetes/   # K8s manifests (deployments, services, etc)
├── monitoring/   # Observability tools (Prometheus, Grafana)
├── chaos/        # Chaos engineering experiments
├── automation/   # Self-healing scripts
├── terraform/    # IaC for cloud infra
├── argocd/       # GitOps config
├── github-actions/# CI/CD pipelines
├── scripts/      # Utility scripts
├── architecture/ # System diagrams
├── docs/         # Documentation
└── screenshots/  # Demo visuals
```

#  Core Achievements
- *Production-Ready K8s Deployment*: Flask app with 3 replicas, liveness, and readiness probes
- *Self-Healing Demonstrated*: Chaos test via pod deletion → auto-recovery
- *GitOps with ArgoCD*: Continuous sync from GitHub → K8s cluster
- *Local Development*: Minikube + Docker for rapid iteration

#  Key Implementation Highlights
*1. Local Kubernetes Cluster Setup*
!screenshots/Minikube-start.png
Launched local Kubernetes cluster using `minikube start --driver=docker` for efficient development.

*2. Docker Environment Configuration*
!screenshots/Eval-docker-env.png
Configured Docker CLI to use Minikube's Docker daemon with `eval (minikube docker-env)` for streamlined image building.

*3. Kubernetes Deployment*
!screenshots/Kubectl-apply.png
Deployed Flask app to `self-healing` namespace with 3 replicas, liveness, and readiness probes using `kubectl apply -f kubernetes/base/`.

*4. Pre-Chaos Verification*
!screenshots/Pods-running.png
Verified all pods are in `Running` state in `self-healing` namespace before chaos testing.

*5. Chaos Engineering: Pod Deletion Test*
!screenshots/Chaos-pod-delete.png
Simulated pod failure by deleting a pod. Kubernetes automatically recreated it, demonstrating self-healing.

*6. Application Health Post-Chaos*
!screenshots/App-healthy.png
Application remained `Healthy` in browser despite pod deletion, proving zero downtime.

*7. Cluster Health Post-Recovery*
!screenshots/Cluster-nodes.png
All Kubernetes nodes in `Ready` state after chaos recovery, showing cluster resilience.

*8. GitOps Deployment with ArgoCD*
!screenshots/8-argocd-gitops-deployment.png
Application deployed via ArgoCD, continuously syncing from GitHub repo (`kubernetes/base` path).

#  Tech Stack
- *Kubernetes*: Container orchestration
- *Docker*: Containerization
- *ArgoCD*: GitOps deployment
- *Minikube*: Local K8s development
- *Flask*: Application framework

#  Self-Healing Features
- *Pod Auto-recovery*: K8s recreates failed pods
- *Node Health*: K8s manages node failures
- *GitOps Sync*: ArgoCD ensures desired state

#  Highlights
- Production-ready K8s deployment with probes
- Self-healing demonstrated via chaos test
- GitOps workflow with ArgoCD
- Clean, modular project structure
- IaC and CI/CD pipelines coming soon

# 📈 Next Steps
- AWS EKS Deployment
- Observability with Prometheus/Grafana
