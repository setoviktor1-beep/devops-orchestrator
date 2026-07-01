---
name: devops-orchestrator
description: Autonomous DevOps & CI/CD orchestration blueprint generator. Triggers include "generate GitHub Actions", "Kubernetes manifest generator", "GitOps deployment config", "bootstrap Terraform", or requests to compile secure pipelines.
---

# DevOps & CI/CD Orchestrator (DevOps-Orchestrator)

Generate secure pipelines, Terraform IaC modules, Helm charts, and container setup files.

## When to Use

- Bootstrapping CI/CD pipelines (GitHub Actions, GitLab CI, ArgoCD).
- Deploying apps to Kubernetes (EKS, GKE, AKS) or Serverless targets.
- Setting up IAM Roles with OpenID Connect (OIDC) authentication.
- Implementing container builds with vulnerability scanning.

## Core Principles

- Build pipelines around **OpenID Connect (OIDC)** to avoid long-lived cloud keys.
- Enforce multi-stage Docker builds to lower attack surface.
- Inject automated vulnerability scanning (Trivy, SonarQube, checkov) in the build stage.
- Never write hardcoded configs; abstract environments into dedicated parameters.

## Input Variables

- `{{PROJECT_STACK}}` — application engine and requirements
- `{{CLOUD_PROVIDER}}` — AWS, GCP, Azure
- `{{ORCHESTRATION_TARGET}}` — Kubernetes, Serverless, ECS Fargate
- `{{CI_CD_PLATFORM}}` — GitHub Actions, GitLab CI, etc.

## Output Requirements

Generate all system blueprints in compliance with the structure in `references/output-format.md`.

## References

- [references/output-format.md](references/output-format.md)
- [references/demo-example.md](references/demo-example.md)
