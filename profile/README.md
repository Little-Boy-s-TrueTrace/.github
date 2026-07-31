# TrueTrace: Multi-Agent Deepfake & AML Autonomous Compliance System

<div align="center">

**Autonomous compliance platform for anti-fraud and anti-money laundering in banking, powered by Multi-Agent AI and Alibaba Cloud**

[![Hackathon](https://img.shields.io/badge/Hackathon-Alibaba%20Cloud%20%26%20Qoder%20HCMC%20FSI-blue?style=for-the-badge)](https://lu.ma/h8u9qz3b)
[![Track](https://img.shields.io/badge/Track-BUILD%20(Developer)-green?style=for-the-badge)](https://qoder.com)
[![Team](https://img.shields.io/badge/Team-Little%20Boy's-purple?style=for-the-badge)](#team)

[![Backend](https://img.shields.io/badge/Backend-Spring_Boot_3-6DB33F?style=flat-square&logo=spring-boot)](https://github.com/Little-Boy-s-TrueTrace/truetrace-backend)
[![Engine](https://img.shields.io/badge/Engine-Python_3.12-3776AB?style=flat-square&logo=python)](https://github.com/Little-Boy-s-TrueTrace/truetrace-agent-engine)
[![Dashboard](https://img.shields.io/badge/Dashboard-React_19-61DAFB?style=flat-square&logo=react)](https://github.com/Little-Boy-s-TrueTrace/truetrace-dashboard)
[![Web](https://img.shields.io/badge/Web-Next.js_16-black?style=flat-square&logo=next.js)](https://github.com/Little-Boy-s-TrueTrace/truetrace-web-client)
[![Mobile](https://img.shields.io/badge/Mobile-Flutter_3-02569B?style=flat-square&logo=flutter)](https://github.com/Little-Boy-s-TrueTrace/truetrace-mobile-app)
[![AI](https://img.shields.io/badge/AI-Alibaba%20Qwen--VL%20%26%20Qwen--Plus-FF6A00?style=flat-square)](https://www.alibabacloud.com/)

**Built with [Qoder](https://qoder.com)** -- AI-Powered Spec-Driven Development

</div>

---

## The Problem

Financial institutions in Vietnam face three escalating compliance challenges that manual processes cannot scale to address:

| Challenge | Impact |
|---|---|
| **Deepfake Identity Fraud** | AI-generated faces and altered CCCD documents bypass KYC onboarding, enabling criminal accounts |
| **Money Laundering Networks** | Sophisticated layering via mule accounts, structuring, and circular flows evade rule-based detection |
| **STR Reporting Burden** | Each Suspicious Transaction Report requires **2-4 hours** of manual drafting per case |

## The Solution: 3 Autonomous AI Agents

TrueTrace deploys three specialized AI agents working as a collaborative team:

### Agent 1: Deepfake Inspector
> *Powered by Alibaba Cloud Qwen-VL Vision AI*

- Analyzes selfie and CCCD (Citizen Identity Card) images
- Detects GAN artifacts, deepfakes, and face swapping
- Validates face match, liveness, and document integrity
- **Result**: Auto **APPROVE** / **REJECT** / escalate to **MANUAL_REVIEW** in **< 10 seconds**

### Agent 2: Money-Trail Graph Explorer
> *Real-time graph analytics with sliding window*

- Builds real-time transaction graph detecting **6 AML patterns simultaneously**:
  - Fan-out (1 to N) | Fan-in (N to 1) | Circular flow (cycle detection)
  - Structuring (near VND 200M threshold) | Velocity anomaly | Rapid mule dispersion
- **Result**: **Auto-freeze** account when risk score >= 7.0 in **real-time**

### Agent 3: AML Report Generator
> *Powered by Alibaba Cloud Qwen-Plus LLM via DashScope*

- Collects evidence from Agent 1 & Agent 2
- Generates bilingual (English/Vietnamese) Suspicious Transaction Reports
- Compliant with SBV Circular 09/2023/TT-NHNN
- **Result**: Draft STR ready for human review in **< 1 minute**

> **Human-in-the-Loop**: All AI decisions require authorized human approval before regulatory action. STR submission always requires a named reviewer.

## Repositories

| Repository | Tech Stack | Description |
|---|---|---|
| [**truetrace**](https://github.com/Little-Boy-s-TrueTrace/truetrace) | Git Superproject | Root repository with all submodules, README, SPEC, architecture docs |
| [**truetrace-backend**](https://github.com/Little-Boy-s-TrueTrace/truetrace-backend) | Java 17 / Spring Boot 3 | Core banking ledger, accounts, transactions, KYC/AML/STR API, Kafka publisher |
| [**truetrace-agent-engine**](https://github.com/Little-Boy-s-TrueTrace/truetrace-agent-engine) | Python 3.12 / AsyncIO / Kafka | Multi-Agent orchestrator coordinating 3 AI agents |
| [**truetrace-dashboard**](https://github.com/Little-Boy-s-TrueTrace/truetrace-dashboard) | React 19 / TypeScript / Go | Compliance admin console (SOC) for bank officers |
| [**truetrace-web-client**](https://github.com/Little-Boy-s-TrueTrace/truetrace-web-client) | Next.js 16 / Node 22 | Customer portal for registration, KYC, and transfers |
| [**truetrace-mobile-app**](https://github.com/Little-Boy-s-TrueTrace/truetrace-mobile-app) | Flutter 3 / Dart | Mobile banking application |
| [**truetrace-deployment**](https://github.com/Little-Boy-s-TrueTrace/truetrace-deployment) | Docker Compose / Helm / K8s | Container orchestration and Nginx gateway |
| [**truetrace-terraform**](https://github.com/Little-Boy-s-TrueTrace/truetrace-terraform) | HCL / Terraform | Cloud infrastructure definitions (AWS) |
| [**agent-deepfake-inspector**](https://github.com/Little-Boy-s-TrueTrace/agent-deepfake-inspector) | Python / Qwen-VL | Agent 1 policy, prompts, and validation schemas |
| [**agent-money-trail**](https://github.com/Little-Boy-s-TrueTrace/agent-money-trail) | Python / Graph Analytics | Agent 2 pattern detection and risk scoring rules |
| [**agent-aml-reporter**](https://github.com/Little-Boy-s-TrueTrace/agent-aml-reporter) | Python / Qwen LLM | Agent 3 STR templates and regulatory references |

## Quick Start

```bash
git clone --recursive https://github.com/Little-Boy-s-TrueTrace/truetrace.git
cd truetrace/truetrace-deployment
cp .env.example .env
docker compose up --build -d --wait

# Access points (all through Nginx gateway):
# Customer Portal:       http://localhost
# Compliance Dashboard:  http://localhost/soc/
# Kafka UI:              http://localhost:9000
```

## Tech Stack

| Layer | Technology |
|---|---|
| **Backend API** | Java 17, Spring Boot 3, PostgreSQL 16, Apache Kafka |
| **Agent Engine** | Python 3.12, AsyncIO, aiokafka, Redis |
| **AI Models** | Alibaba Cloud Qwen-VL (Vision), Qwen-Plus (LLM) via DashScope API |
| **Dashboard** | Go 1.24, React 19, TypeScript, Vite |
| **Web Client** | Next.js 16, React 19, TailwindCSS |
| **Mobile** | Flutter 3, Dart, Material Design 3 |
| **Infrastructure** | Docker Compose (11 containers), Kubernetes, Terraform, Nginx |
| **Cloud Platform** | Alibaba Cloud (ApsaraDB, OSS, Model Studio, ARMS, SLS, WAF) |

## Testing

87+ automated tests across all tiers:
- **Python**: 24 pytest tests (agents, graph analyzer, multi-agent pipeline E2E)
- **Java**: 36 JUnit 5 tests (banking API, KYC, AML freeze/unfreeze, STR lifecycle)
- **React**: 27 Vitest tests (dashboard UI, alert actions, search filtering)
- **CI/CD**: GitHub Actions with full-stack Docker Compose smoke test

## Team

**Little Boy's** -- Alibaba Cloud & Qoder Hackathon HCMC 2026

## License

This project is licensed under the MIT License -- see the [LICENSE](https://github.com/Little-Boy-s-TrueTrace/.github/blob/main/LICENSE) file for details.
