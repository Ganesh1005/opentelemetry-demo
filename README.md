# E-Commerce DevOps Implementation (OpenTelemetry Astronomy Shop)

> **Note:** This repository is **my fork** of the OpenTelemetry Demo. I used it to build a production-style DevOps + Observability implementation across polyglot microservices. All work here is for learning/showcase purposes and runs entirely in **my own environment** (no upstream secrets used).

---

## 🚀 What I built

- **Microservices at scale** – Worked across **10+ services** in **.NET, Java, Go, Python, Rust, Node/TypeScript, PHP, Ruby, Kotlin** with independent builds/deploys.
- **Kubernetes-native deploys** – Split the monolithic demo into **per-service manifests** under `kubernetes/<service>/{deploy,svc}.yaml` enabling targeted rollouts, faster iteration, and clearer ownership.
- **CI/CD** – GitHub Actions for build/test + **GitOps with Argo CD** for continuous delivery to Kubernetes.
- **IaC** – Provisioned AWS (VPC, subnets, **EKS**, security groups, ALB, Route 53) via **Terraform**; cluster add-ons via Helm/ArgoCD.
- **Observability** – End-to-end **OpenTelemetry** traces/metrics/logs through the **OTel Collector**, visualized in Prometheus + Jaeger/Tempo, with dashboards for the full checkout journey.
- **Failure scenarios** – Used feature flags to inject latency / partial outages / payment errors and drove MTTR down using correlated telemetry.

**Outcome:** A production-style setup that demonstrates how enterprises run **polyglot microservices** on **Kubernetes** with **CI/CD** and **observability**—optimized for fast feedback and safe rollouts.

---

## 📁 What’s in this fork

- ✅ **Per-service Kubernetes manifests:** `kubernetes/<service>/{deploy.yaml, svc.yaml}`
- ✅ OpenTelemetry Collector config + service-level instrumentation tweaks
- ✅ Minor service/config fixes for smoother per-service deploys
- 🔕 **CI in this fork is intentionally disabled** to avoid red badges (forks don’t have upstream secrets). I run pipelines in my own CI/CD environment.

> If you’d like to see the **Terraform/Argo CD** setup I use to provision EKS and sync these manifests, I can share a walkthrough or excerpts on request.

---

## 🧪 Quick start (local, minimal)

```bash
# From repo root
make build                # or build service-by-service
docker compose up -d

