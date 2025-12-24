# Cloud-Native Reference Project on Azure Kubernetes Service (AKS)

## Introduction

The main goal of this project is to **gain hands-on experience with designing, building, deploying, and operating cloud-native applications** on **Microsoft Azure Kubernetes Service (AKS)**.

Rather than focusing solely on implementation, this project emphasizes **architectural decision-making**:  
*Which technologies to choose, why they are chosen, and what trade-offs they introduce.*

This repository serves as a **learning playground and reference architecture** covering the full lifecycle of a modern cloud-native application, from infrastructure provisioning to deployment, observability, and secure software development practices.

---

## Project Objectives

The key objectives of this project are:

- Understand how to design and provision Kubernetes infrastructure on Azure
- Gain experience with Infrastructure as Code (IaC) approaches
- Learn how to expose applications securely using ingress and certificates
- Explore deployment strategies and CI/CD patterns for Kubernetes
- Implement observability (logging and monitoring) as first-class concerns
- Apply secure coding, quality checks, and DevOps best practices
- Practice architectural trade-off analysis and documentation

---

## Infrastructure

The application platform is built on **Azure Kubernetes Service (AKS)**.  
AKS is a fully managed Kubernetes offering that abstracts away much of the control-plane management while still providing flexibility and control over workloads, networking, and security.

### Infrastructure Components

The infrastructure consists of:

- Azure Kubernetes Service (AKS)
- Networking (VNet, subnets, ingress)
- Supporting Azure services (Key Vault, database, caching)
- Identity and access management
- Certificates and secrets

---

## Infrastructure as Code (IaC)

All infrastructure should be reproducible, version-controlled, and automated using **Infrastructure as Code**.

The following tools are evaluated to determine which best fits the project goals:

- **Bicep** – Native Azure DSL with tight Azure integration
- **Terraform** – Cloud-agnostic, mature ecosystem, strong state management
- **Pulumi** – Infrastructure defined using general-purpose programming languages
- **Ansible** – Configuration management and orchestration, less declarative for cloud provisioning

### Learning Goals

- Compare Azure-native vs cloud-agnostic approaches
- Evaluate maintainability, readability, and team scalability
- Understand state management and deployment workflows
- Decide which tool best aligns with long-term architectural goals

---

## Ingress and Traffic Management

External access to the Kubernetes workloads requires an **Ingress solution**.

This project investigates available options such as:

- Kubernetes Ingress Controllers
- API Gateway–based solutions
- Cloud-native Azure integrations

### Key Considerations

- TLS termination and certificate management
- Routing and path-based rules
- Security and authentication capabilities
- Operational complexity and observability

---

## Supporting Azure Resources

In addition to AKS, several supporting resources are required. Each introduces architectural decisions that must be evaluated:

### Secrets and Configuration Management
- **Azure Key Vault**
- Comparison with alternatives such as HashiCorp Vault

### Data Storage
- Managed PostgreSQL database
- Backup, scaling, and availability considerations

### Certificate Management
- cert-manager (Kubernetes-native)
- Self-signed or Key Vault–issued certificates

### Caching
- Distributed caching strategies
- Azure-native caching services

---

## Observability and Logging

Observability is treated as a **core architectural concern**, not an afterthought.

### Logging

Centralized and structured logging is essential in distributed systems.

Evaluated tools include:
- **Seq** – Structured logging for .NET workloads
- **Azure Application Insights** – Azure-native APM and logging

### Monitoring and Metrics

Monitoring provides insight into system health, performance, and capacity.

Evaluated tools include:
- **Prometheus** – Metrics collection and alerting
- **Grafana** – Visualization and dashboards

### Learning Goals

- Understand the difference between logs, metrics, and traces
- Design dashboards that provide actionable insights
- Identify failure modes in Kubernetes environments

---

## Deployment and CI/CD

A modern cloud-native platform requires automated, reliable deployment pipelines.

Deployment strategies explored in this project include:

- **Azure DevOps Pipelines**
- **GitHub Actions**
- **Argo CD (GitOps)**
- **Helm charts** for application packaging and versioning

### Deployment Topics

- Git-based workflows and triggers
- Environment promotion (dev, test, prod)
- Rollbacks and deployment safety
- GitOps principles and declarative deployments

---

## Code Quality, Optimization, and Security

Beyond functionality, production-grade software must meet quality and security standards.

### Code Quality
- **SonarQube** for static code analysis and maintainability

### Security
- **OWASP ZAP** for vulnerability scanning and penetration testing
- Secure container images and dependency scanning
- Secrets handling and least-privilege access

---

## Application Architecture

To support the infrastructure and deployment experiments, a sample application is used.

### Backend
- **.NET 10 Minimal API**
- Stateless, containerized services
- REST-based communication

### Frontend
- **Blazor (.NET 10)**
- **MudBlazor** UI components

The application is intentionally simple to keep the focus on **platform architecture rather than business complexity**.

---

## Source Control and Development Workflow

A clear development workflow is defined to simulate a real-world team environment.

### Topics Covered

- Branching strategy (e.g., trunk-based or GitFlow-inspired)
- Pull requests and code reviews
- Automated checks before merge
- Pipeline triggers on merge to main branches

---

## Conclusion

This project is not intended to be a final or perfect solution.  
Instead, it serves as an **architectural learning journey** that emphasizes:

- Making conscious technical choices
- Understanding trade-offs
- Building operational awareness
- Designing for maintainability, security, and scalability

The outcome is a practical reference architecture and a deeper understanding of **cloud-native software architecture on Azure**.
