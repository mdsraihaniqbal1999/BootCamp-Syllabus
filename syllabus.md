# DevOps Bootcamp – Detailed Topic-Wise Syllabus

## Table of Contents

- [Module 1: Linux + DevOps Culture](#module-1-linux--devops-culture)
- [Module 2: AWS Foundations](#module-2-aws-foundations)
- [Module 3: Containers, ECS, Terraform & CI/CD](#module-3-containers-ecs-terraform--cicd)
- [Module 4: Python for DevOps + Serverless](#module-4-python-for-devops--serverless)
- [Module 5: Kubernetes on AWS (EKS)](#module-5-kubernetes-on-aws-eks)
- [Module 6: DevSecOps + Kubernetes Security](#module-6-devsecops--kubernetes-security-kyverno--security-tools)
- [Module 7: SRE + Incident Response](#module-7-sre--incident-response)

---

## MODULE 1: Linux + DevOps Culture

### Week 1: Linux & Shell Scripting Foundations + DevOps Fundamentals

#### Linux Filesystem & Permissions
- Filesystem hierarchy (`/`, `/home`, `/etc`, `/var`, `/usr`, `/opt`, `/tmp`)
- File permissions (read, write, execute) for owner, group, others
- `chmod`, `chown`, `chgrp` – symbolic and numeric modes
- Users and groups: `/etc/passwd`, `/etc/shadow`, `/etc/group`
- `sudo`, `su`, `useradd`, `usermod`, `groupadd`

#### Package Management
- `apt` (Debian/Ubuntu): update, upgrade, install, remove, purge
- `yum`/`dnf` (RHEL/CentOS): install, remove, search
- Repository configuration

#### Process Management & System Monitoring
- `ps`, `top`, `htop`, `pgrep`, `pkill`
- Foreground vs background processes, `jobs`, `nohup`
- `kill` signals (SIGTERM, SIGKILL, SIGHUP)
- `systemctl status`, `journalctl`
- `df`, `du`, `free`, `uptime`, `vmstat`, `iostat`

#### Important Files & Directories
- `/etc/hosts` – static hostname resolution
- `/etc/passwd` – user account info
- `/etc/fstab` – filesystem mount configuration
- `/var/log/` – syslog, auth.log, kern.log, application logs

#### SSH & Secure Access
- SSH protocol basics, `ssh` client usage
- Key-based authentication: `ssh-keygen`, `ssh-copy-id`, `~/.ssh/config`
- Disabling password auth, changing default port
- Environment variables: `export`, `env`, `printenv`
- Shell profiles: `~/.bashrc`, `~/.bash_profile`, `/etc/profile`
- Secure server hardening basics

#### Services & systemd
- Unit files (service, timer, socket)
- `systemctl` start/stop/enable/disable/status
- Creating custom systemd service units
- How applications run as managed services on Linux

#### Shell Scripting
- Variables, quoting, command substitution
- Command-line arguments (`$1`, `$2`, `$@`, `$#`)
- Wildcards and globbing
- I/O redirection (`>`, `>>`, `2>`, `&>`, `<`, `<<`, `|`, `tee`)
- Conditionals (if/elif/else, case)
- Loops (for, while, until)
- Functions, return codes, exit codes
- Building reusable automation scripts

#### DevOps Culture & SDLC
- DevOps principles: collaboration, automation, measurement, sharing
- CALMS framework
- SDLC phases and where DevOps fits
- CI/CD/CD concepts overview
- Blameless culture introduction

#### Projects
- Automated Backup & Disk Cleanup System
- Real-Time Log Monitoring & Alerting Script

---

## MODULE 2: AWS Foundations

### Week 2: AWS Networking, Security & Compute Foundations

#### VPC & Networking
- VPC creation, CIDR block planning
- Subnets: public vs private, availability zones
- Route Tables, Internet Gateway, NAT Gateway
- Public vs private networking design
- Production-grade network design principles

#### IAM Fundamentals
- Users, groups, roles, policies
- Least-privilege access model
- Policy types: identity-based, resource-based
- IAM best practices

#### Secure Server Access
- Bastion Hosts
- IAM Roles for EC2
- AWS Systems Manager Session Manager
- VPC Endpoints (Gateway & Interface)
- VPC Peering, Transit Gateway use cases

#### EC2 Fundamentals
- Instance types and families
- EBS volumes (gp2, gp3, io1, io2, st1, sc1)
- AMIs, key pairs
- EC2 monitoring (CloudWatch basics)

#### 2-Tier Application on EC2
- Application tier + PostgreSQL database tier
- Nginx reverse proxy configuration
- Route53 DNS, Elastic IP, SSL certificates
- Security groups for separate tiers
- How production teams structure AWS accounts, networking, and access control
- Cost awareness: right-sizing EC2, choosing instance families, spotting idle instances

#### Projects
- Production VPC from Scratch: Multi-AZ VPC with Public, Private App, and Private DB Subnets
- Secure EC2 Access using Bastion Host, IAM Roles, SSM Session Manager, and VPC Endpoints
- Deploy a 2-Tier Application on EC2 with Nginx, PostgreSQL, Route53, Elastic IP, and SSL

### Week 3: AWS Storage, CDN & 2-Tier App on EC2

#### Amazon S3
- Buckets, objects, versioning
- Encryption (SSE-S3, SSE-KMS, SSE-C)
- Access control: bucket policies, ACLs, pre-signed URLs
- Storage classes and lifecycle policies for cost optimisation
- Static website hosting
- S3 event notifications

#### CloudFront
- Caching behavior, TTLs
- Origin Access Control (OAC)
- SSL certificates
- Cache invalidation
- Cost levers

#### Route53 & ACM
- DNS record types (A, AAAA, CNAME, alias)
- Hosted zones
- ACM certificate provisioning and validation

#### High Availability & Bootstrapping
- Production application architecture patterns
- User data scripts for EC2 bootstrapping
- Configuration management basics
- Launch Templates

#### Auto Scaling & Load Balancing
- Auto Scaling Groups, scaling policies (target tracking, step, scheduled)
- Zero-downtime deployments
- ALB vs NLB: listeners, target groups, health checks, routing rules
- Connecting EC2 application tier to ALB and ASG end to end

#### Amazon RDS
- Networking (subnet groups, security groups)
- Backups (automated, manual snapshots)
- Multi-AZ deployment
- Parameter Store integration
- Instance sizing as cost lever
- Auto Scaling and RDS sizing for cost optimisation

#### AI-Assisted Troubleshooting
- Using AI copilots to debug failures faster
- Working effectively with AI in day-to-day operations

#### Projects
- Production 2-Tier Application with ALB, Auto Scaling Group, RDS PostgreSQL, ACM, and Route53
- Auto Scaling Validation and Zero-Downtime Deployment under Load
- Static Website Hosting using S3 + CloudFront + Route53 + ACM SSL

---

## MODULE 3: Containers, ECS, Terraform & CI/CD

### Week 4: Containerization with Docker & Docker Compose

#### Why Containers
- Container vs VM: architecture, isolation, resource overhead
- How containers replaced VM-based deployments

#### Docker Architecture
- Docker Engine, Images, Containers, Registries
- Docker Hub, private registries
- Building, tagging, storing, sharing images across environments

#### Dockerfiles
- Image layers and caching
- Instructions: `FROM`, `RUN`, `COPY`, `ADD`, `CMD`, `ENTRYPOINT`, `EXPOSE`, `WORKDIR`, `ENV`, `ARG`
- `.dockerignore`

#### Container Lifecycle & Operations
- `docker run`, `ps`, `logs`, `exec`, `stop`, `rm`
- Resource limits (CPU, memory)
- Logging and troubleshooting
- Container lifecycle management

#### Docker Networking
- Bridge network, custom networks
- Container-to-container communication
- Port mapping

#### Persistent Storage
- Volumes, bind mounts, named volumes
- Persistent storage for stateful apps

#### Configuration & Secrets
- Environment variables
- Secrets basics
- Configuration management in containers

#### Docker Compose
- Multi-container apps
- Networking, volumes
- Environment-specific configs (compose overrides)
- `depends_on`, healthchecks

#### Image Optimisation
- Multi-stage builds
- Reducing image size
- `.dockerignore` that cuts registry and runtime cost

#### Projects
- Containerize a Flask + PostgreSQL Application using Docker Compose, custom networks, persistent volumes, and environment variables
- Migrate a VM-Based 2-Tier Application to Docker with Nginx, PostgreSQL, health checks, persistent storage, and production-ready image optimisation

### Week 5: Running Containers in Production with AWS ECS

#### ECS Architecture
- Clusters, services, task definitions
- Container networking (awsvpc mode)
- Service discovery

#### Launch Types
- Fargate vs EC2: when to choose each
- Cost trade-off analysis

#### Load Balancing & Monitoring
- Application Load Balancers, target groups, health checks
- Logging (CloudWatch Logs)
- Monitoring (CloudWatch metrics, Container Insights)

#### ECS Security
- IAM roles (task execution role vs task role)
- Parameter Store
- Secrets Manager integration

#### ECS vs Kubernetes
- Real-world case studies
- Decision frameworks

#### Production Deployment Patterns
- High availability
- Scaling (service auto scaling)
- Right-sizing task CPU and memory to control spend

#### PostgreSQL-Backed Application on ECS
- Production best practices
- Connecting ECS to RDS

#### Load Testing Fundamentals
- How applications behave under increasing traffic
- Tools overview (k6, Locust, JMeter)

#### Projects
- Deploy a Production 2-Tier Application on ECS with ALB, SSL, Route53, and RDS PostgreSQL
- Load Test the Application and Analyse Performance Bottlenecks under Production-Like Traffic

### Week 6: Terraform Foundations & CI/CD for ECS Applications

#### Infrastructure as Code Fundamentals
- Why IaC, benefits, Terraform vs alternatives

#### Terraform Core
- Providers, resources, variables, outputs
- State management (local vs remote, locking)
- Dependency handling (implicit, explicit `depends_on`)
- Terraform planning (`plan`, `apply`, `destroy`)
- Lifecycle management (`create_before_destroy`, `prevent_destroy`, `ignore_changes`)
- Safe change deployment practices

#### Deploying ECS with Terraform
- Building ECS infrastructure via Terraform instead of console clicks
- VPC, ALB, ECS, Route53, SSL, RDS integration

#### GitHub Actions
- Workflows, jobs, steps
- Runners (GitHub-hosted vs self-hosted)
- Secrets and environments
- CI/CD pipelines that build, test, and deploy automatically

#### GitHub Workflows
- Repositories, branches, pull requests
- Code reviews, collaboration workflows
- Branch protection, tagging, stashing, repository management

#### Deployment Automation
- Container image versioning
- Deployment automation
- Rollback strategies

#### ECS Autoscaling & Monitoring
- ECS autoscaling policies
- CloudWatch alarms
- Monitoring dashboards

#### Tagging Strategy
- Tagging in Terraform for cost allocation and accountability

#### Projects
- Deploy Complete ECS Infrastructure using Terraform: VPC, ALB, ECS, Route53, SSL, RDS
- Build a CI/CD Pipeline that Automatically Builds, Deploys, and Updates the ECS Application

### Week 7: Microservices on ECS, Advanced Terraform & Advanced CI/CD

#### Microservices Architecture
- Patterns and service communication strategies
- Multiple services on ECS with independent deployments and scaling policies

#### Advanced Terraform
- Modules (writing, using, versioning)
- Remote state (S3 + DynamoDB locking)
- Workspaces for multi-environment
- Imports (importing existing resources)
- Lifecycle management (advanced)
- Multi-environment deployments
- Reusable Terraform modules shared across teams and environments
- Terraform best practices used by platform engineering teams in production

#### Advanced GitHub Actions
- Reusable workflows
- Composite actions
- Workflow templates
- Deployment approvals
- Multi-environment pipelines (dev, staging, prod)
- Cross-repository deployment: application and infrastructure code maintained separately

#### Production Operations
- Load testing, autoscaling validation
- Production troubleshooting

#### Production-Grade RDS
- Multi-AZ, Read Replicas
- Aurora patterns

#### Cost Visibility
- Per-service cost visibility through tagging
- Scaling discipline

#### Projects
- Deploy a Production Microservices Application on ECS using Reusable Terraform Modules and Multi-Environment Infrastructure
- Build an Advanced GitHub Actions Platform with Reusable Workflows, Automated Deployments, Autoscaling, and Production Release Strategies

---

## MODULE 4: Python for DevOps + Serverless

### Week 8: Python Foundations + AWS Automation

#### Python Environment
- Setup, virtual environments (`venv`)
- Project structure
- Package management (`pip`, `requirements.txt`)

#### Data Structures
- Dicts, lists, sets (DevOps-relevant usage)
- Comprehensions, common patterns

#### System Interaction
- `os` module
- `subprocess`: running shell commands from Python
- File operations

#### Data Parsing
- JSON and YAML parsing
- Config file handling

#### Error Handling
- Exceptions, `try`/`except`/`finally`
- Custom exceptions
- Exception management best practices

#### APIs
- Working with APIs using the `requests` module
- Authentication, headers, pagination

#### boto3 Architecture
- Sessions, clients vs resources
- Paginators
- Common AWS service interactions

#### Configuration Management
- Environment-based config: `.env`, `os.environ`
- Python logging best practices

#### AWS Lambda
- Execution model: cold starts, warm starts
- Concurrency limits
- Lambda triggers: S3, SQS, SNS, EventBridge
- Lambda Layers: packaging dependencies, sharing code
- Dead letter queues for failed invocations

#### Lambda Projects
- IAM key rotation Lambda: EventBridge schedule, Secrets Manager, SES report
- Daily cloud cost report Lambda: Cost Explorer data, per-service breakdown

### Week 9: Serverless Automation

#### System Tools from Python
- `subprocess` for running system tools
- Parsing command output

#### File Scanning Automation
- ClamAV setup, `freshclam`
- Scan result parsing
- File scanning automation running on ECS with S3 + SQS trigger

#### Event-Driven Patterns
- S3 event notification → SQS → Python consumer pattern
- S3 object tagging: Clean/Infected

#### Multi-Account Architecture
- Landing account vs clean account

#### Alerting
- SES email alerts for infected files

#### API Gateway + Lambda
- Proxy vs non-proxy integration

#### Lambda Orchestration
- Multi-Lambda orchestration patterns: chaining, fan-out, fan-in

#### Lambda Cost Optimisation
- Right-sizing memory
- Reducing cold starts

#### EventBridge
- EventBridge as the event bus
- Rules, targets, patterns

### Week 10: Database Migration + Cost Automation with Python

#### Migration Planning
- Pre-migration health check script

#### Database Migration
- `pg_dump` and `pg_restore` from Python subprocess
- `pgsync` for live data migration with minimal downtime

#### Data Validation
- Post-migration: row counts, checksum comparison

#### Containerising Migration Scripts
- Docker for migration scripts
- Deploying a migration job on ECS Fargate as a one-off task
- Lambda trigger for the ECS migration task

#### Cost Automation
- boto3 for pulling RDS and EC2 metrics via CloudWatch
- Identifying rightsizing candidates: underutilised instances, oversized storage
- Budget alerts: programmatic spend thresholds with notifications
- Automated tagging enforcement: scanning for untagged resources
- Building FinOps tooling in Python

---

## MODULE 5: Kubernetes on AWS (EKS)

### Week 11: Kubernetes Fundamentals + Local Clusters

#### Why Kubernetes
- The problems that broke before Kubernetes
- What Kubernetes solves

#### Control Plane Deep Dive
- API server, etcd, scheduler, controller manager

#### Worker Node Components
- kubelet, kube-proxy, container runtime (containerd)

#### Core Objects
- Pod, ReplicaSet, Deployment, Service

#### Local Setup
- Kind (Kubernetes in Docker) setup
- `kubectl` basics and everyday commands

#### Configuration
- ConfigMaps and Secrets: creating, mounting as env vars and volumes

#### Organisation
- Namespaces, labels, selectors, annotations

#### Resource Management
- Resource requests and limits
- Correct sizing as the first line of cost control

#### Networking
- Kubernetes DNS and service discovery internals

#### Health Checks
- Liveness, readiness, and startup probes
- Real failure scenarios

#### Updates
- Rolling upgrades and rollback strategies

#### Autoscaling
- HPA (Horizontal Pod Autoscaler): CPU, memory, custom metrics
- VPA (Vertical Pod Autoscaler)

#### Patterns
- Init containers and sidecar patterns

#### Disruption
- Pod Disruption Budgets for zero-downtime deployments

#### Debugging
- CrashLoopBackOff, OOMKilled: live debugging techniques

#### Workload Types
- StatefulSets, DaemonSets, and Jobs

### Week 12: CI/CD with OIDC + GitOps + Production EKS Foundation

#### GitOps Fundamentals
- Why GitOps over push-based deployments

#### ArgoCD on Kind
- Setup, apps, sync policies, health checks

#### End-to-End CI/CD
- GitHub Actions builds image, ArgoCD deploys

#### ArgoCD Advanced
- App-of-Apps pattern
- Rollback
- Multi-environment GitOps

#### Monitoring on Kind
- Prometheus + Grafana: request rate, pod health dashboards

#### EKS Cluster Setup
- `eksctl` and AWS console
- EKS add-ons: VPC CNI, CoreDNS, EBS CSI Driver, kube-proxy

#### IRSA (IAM Roles for Service Accounts)
- Kubernetes to AWS IAM with OIDC
- No hardcoded credentials

#### AWS Load Balancer Controller
- Installation with Helm
- Ingress for internal and external traffic routing

#### ExternalDNS
- Automatic Route 53 record management

#### Domain & SSL
- SSL/TLS termination with ACM

### Week 13: 3-Tier App on EKS + Docker Optimisation

#### 3-Tier Application
- Frontend + backend + RDS PostgreSQL on EKS

#### Database Migrations
- Using Kubernetes Jobs
- Init Containers
- DB connection readiness checks

#### IRSA in Practice
- Backend pod accessing Secrets Manager without credentials

#### External Secrets Operator
- Syncing Secrets Manager into Kubernetes Secrets

#### Ingress Rules
- Routing traffic to frontend vs backend

#### Deployment Strategies
- Blue-Green deployment on EKS with weighted routing

#### Troubleshooting
- ImagePullBackOff, pending pods, service not reachable

#### StatefulSets Deep Dive
- Production patterns and failure recovery

#### Storage
- PersistentVolume, PVC, StorageClass
- Static vs dynamic provisioning on EKS
- EBS vs EFS: choosing the right storage, cost impact
- Volume snapshots and backup strategies on EKS

#### Docker Image Optimisation
- Multi-stage Docker builds: drastically smaller production images
- Distroless and minimal base images
- Layer caching, build context, `.dockerignore`

### Week 14: Microservices on EKS + Terraform for EKS

#### Production EKS with Terraform
- VPC, subnets, node groups, add-ons
- Terraform module structure for EKS: separation of concerns
- Managing dev/staging/prod with Terraform workspaces
- IRSA setup via Terraform: no manual console steps
- Terraform drift detection on EKS infrastructure
- EKS upgrade strategy with Terraform

#### Node Groups
- Instance types
- Spot vs on-demand for cost
- Taints and tolerations

#### Microservices Design
- Bounded context, single responsibility
- Splitting the monolith: frontend, order, inventory, and user service

#### PostgreSQL on Kubernetes
- CloudNativePG (CNPG): HA, automated failover, backups, read replicas

#### Service Communication
- ClusterIP vs headless vs service mesh

#### Network Policies
- Microservice traffic isolation between namespaces

#### Gateway API
- Advanced ingress routing

#### GitOps for Multi-Environment
- ArgoCD ApplicationSet for environment promotion across dev/staging/prod

#### CI for Microservices
- Matrix builds in GitHub Actions for multiple microservices

### Week 15: Full Observability Stack (Prometheus, Loki, Tempo & Grafana)

#### Prometheus
- Metrics collection
- PromQL
- Scrape configs
- Prometheus Operator

#### Loki
- Log storage and querying
- LogQL basics

#### Fluent Bit on EKS
- Log aggregation, filtering, routing to Loki

#### Grafana
- Dashboards: Kubernetes cluster, app metrics, AWS resource metrics

#### AlertManager
- Routing alerts to Slack and PagerDuty
- Grouping and silencing

#### CloudWatch Integration
- Container Insights alongside Prometheus

#### OpenTelemetry (Tracing)
- Distributed tracing: instrumentation, collectors, exporters
- Tracing a request across multiple microservices end to end

#### Tracing Backend
- Jaeger or Tempo as tracing backend

#### SLOs & SLIs
- Definitions, writing measurable objectives
- Error budget dashboards in Grafana
- Multi-window, multi-burn-rate alerting for SLOs

#### AlertManager Advanced
- Inhibition rules, routing trees, deduplication

#### Log-Based Alerting
- Grafana with Loki rules

### Week 16: Service Mesh (Istio) + Autoscaling + Cost Optimisation

#### Service Mesh Fundamentals (Istio)
- What problems a service mesh solves
- Istio installation and architecture: control plane, data plane, sidecars

#### Security
- mTLS between all microservices: automatic, no code changes

#### Traffic Management
- VirtualService, DestinationRule, Gateway
- Canary deployments with Istio traffic splitting

#### Observability
- Visualising service mesh traffic with Kiali

#### Network Policies
- Zero-trust pod-to-pod communication
- Egress controls and namespace isolation

#### Resilience
- Pod topology spread constraints for multi-AZ resilience

#### Autoscaling
- Karpenter architecture: how it differs from Cluster Autoscaler
- NodePool and EC2NodeClass configuration
- Karpenter bin packing and consolidation
- KEDA: event-driven pod autoscaling on queue depth, Kafka lag, cron, and custom metrics

#### Cost Optimisation
- Spot + On-Demand mixed node fleets
- EKS Auto Mode: what it is and when to use it
- OpenCost and Kubecost: per-namespace, per-team, per-service cost attribution
- Tagging strategy as cost governance: enforcing tags with Kyverno and OPA
- Budget alerts, automated enforcement, weekly FinOps reporting with rightsizing recommendations
- Building a cost culture: making engineers aware of infrastructure costs

#### Policy Enforcement
- Kyverno policy enforcement: blocking deployments without resource limits
- Pod Security Admission: restricted, baseline, privileged modes

---

## MODULE 6: DevSecOps + Kubernetes Security (Kyverno + Security Tools)

### Week 17: Shift-Left Security + Pipeline Hardening

#### DevSecOps Mindset
- Where security fits in the SDLC

#### SAST (Static Application Security Testing)
- Semgrep: code-level vulnerability scanning in pull requests

#### DAST (Dynamic Application Security Testing)
- OWASP ZAP: running against staging before every production release

#### SCA (Software Composition Analysis)
- Dependency auditing with Trivy and Grype

#### Secret Scanning
- Pre-commit secret scanning
- GitHub secret scanning

#### Container Supply Chain Security
- Trivy blocking critical CVEs
- Image signing with Cosign
- SBOM generation with Syft

#### IaC Security Scanning
- Checkov linting Terraform and Kubernetes manifests

#### Secrets Management in the Pipeline
- OIDC for AWS auth
- External Secrets Operator

#### Full Security Pipeline
- Building the full security pipeline end-to-end in GitHub Actions
- Hard fail gates: nothing progresses if a gate does not pass
- Writing Checkov exceptions with documented justification
- Managing Trivy ignore files: accepting risk intentionally, not accidentally
- Cosign signature verification in ArgoCD: blocking unsigned images

#### Dependency Updates
- Dependabot and Renovate

### Week 18: Kubernetes Runtime Security + Policy as Code (Kyverno) + Zero Trust

#### Runtime Threat Detection
- Falco for runtime threat detection on EKS
- Custom rules for suspicious process execution, file access, and network activity
- Falco alerting to Slack in real time

#### CIS Benchmark
- CIS Kubernetes Benchmark scanning with kube-bench

#### Zero Trust Networking
- Network policies for zero trust between namespaces: default deny all, explicit allow only

#### Audit Logs
- Kubernetes audit logs: what's happening in your cluster and how to query it

#### Integrated Security Pipeline
- Connecting every security tool into a single coherent pipeline
- Cluster-side controls: Kyverno, Falco, network policies, pod security standards, kube-bench working together

#### Incident Response
- Incident response workflow: what happens when Falco fires a critical alert

#### Security Reporting
- Generating a weekly security health report

---

## MODULE 7: SRE + Incident Response

### Week 19: SRE Foundations + Chaos Engineering

#### Core SRE Concepts
- Reliability, SLIs, SLOs, SLAs
- Error budgets, incidents, postmortems

#### SLI, SLO, SLA
- Precise definitions
- Writing measurable objectives

#### Error Budgets
- How they make deployment decisions instead of gut feelings
- Error budget policy: deployment freezes, negotiating reliability work vs feature work

#### DORA Metrics
- Deployment frequency, lead time, MTTR, change failure rate

#### On-Call Culture
- Runbook discipline: what a good runbook looks like

#### Postmortem Culture
- Blameless analysis, timeline reconstruction
- RCAs that prevent recurrence

#### Chaos Engineering
- Philosophy: breaking things deliberately before they break unexpectedly
- LitmusChaos on EKS: pod failure, network delay, CPU stress, disk fill experiments
- Defining steady-state hypotheses and blast radius limits

#### Capacity Planning
- Basics and the capacity vs cost trade-off

#### SRE Dashboard
- Building a production-ready dashboard: error budget burn, DORA metrics, on-call health, alert volume

#### Reliability Reviews
- Formal review of a service before it goes to production