# TrueTrace: Multi-Agent Deepfake & AML Autonomous Compliance System

<div align="center">

**Automated compliance system for anti-fraud and anti-money laundering in banking, powered by Multi-Agent AI**

[![Backend](https://img.shields.io/badge/Backend-Spring_Boot_3-6DB33F?style=for-the-badge&logo=spring-boot)](truetrace-backend/)
[![Engine](https://img.shields.io/badge/Engine-Python_3.11-3776AB?style=for-the-badge&logo=python)](truetrace-agent-engine/)
[![Dashboard](https://img.shields.io/badge/Dashboard-React_19-61DAFB?style=for-the-badge&logo=react)](truetrace-dashboard/)
[![Mobile](https://img.shields.io/badge/Mobile-Flutter-02569B?style=for-the-badge&logo=flutter)](truetrace-mobile-app/)

</div>

---

## The Problem

Banks are facing critical challenges:

| Challenge | Description |
|---|---|
| **Deepfake KYC Fraud** | Criminals use AI to forge faces and voices to open fraudulent bank accounts |
| **Mule Accounts** | Fraud proceeds are split and moved through hundreds of accounts in minutes |
| **Compliance Burden** | Officers must manually review thousands of suspicious transactions to file STR reports |

## Multi-Agent AI Architecture

TrueTrace deploys a network of 3 AI Agents working in coordination:

### Agent 1: Deepfake Inspector
> *Monitors KYC submissions*

- Analyzes selfie and CCCD (Citizen Identity Card) images using AI Vision
- Detects GAN artifacts, pixel noise, and face swapping
- Validates 12-digit CCCD number format
- Cross-references selfie against the photo on the CCCD
- **Action**: Automatically APPROVE / REJECT / escalate to MANUAL_REVIEW

### Agent 2: Money-Trail Graph Explorer
> *Traces abnormal money flows*

- Builds a real-time transaction graph (sliding window)
- Detects Fan-out (1->N), Fan-in (N->1), and Circular flow patterns
- Detects Structuring (splitting below the 200M VND reporting threshold)
- Detects Velocity Anomalies (abnormally high transaction frequency)
- **Action**: Automatically freezes suspicious accounts temporarily

### Agent 3: AML Report Generator
> *Automates legal documentation*

- Collects evidence from Agent 1 & Agent 2
- Uses LLM (Qwen) to generate bilingual narratives
- Creates Suspicious Transaction Reports (STR) per Circular 09/2023/TT-NHNN
- **Action**: Report ready for officer to review and submit in 5 seconds

## Project Structure

```
truetrace/
├── agent-deepfake-inspector/    # Agent 1: System prompts & detection rules
├── agent-money-trail/           # Agent 2: Pattern detection & risk scoring
├── agent-aml-reporter/          # Agent 3: STR templates & regulatory references
├── truetrace-backend/           # Spring Boot Banking + AML REST API
├── truetrace-agent-engine/      # Python Multi-Agent Orchestration Engine
├── truetrace-dashboard/         # Go + React Compliance Command Center
├── truetrace-web-client/        # Next.js Customer Web Portal
├── truetrace-mobile-app/        # Flutter Mobile Banking App
├── truetrace-deployment/        # Docker Compose & K8s configs
├── truetrace-terraform/         # AWS Infrastructure as Code
└── .github/                     # CI/CD & Organization templates
```

## Tech Stack

| Layer | Technology |
|---|---|
| **Backend API** | Java 17, Spring Boot 3, PostgreSQL, Kafka |
| **Agent Engine** | Python 3.11, Kafka, Redis, Qwen LLM |
| **Dashboard** | Go 1.26, React 19, TypeScript, Vite |
| **Web Client** | Next.js 16, React 19, TailwindCSS |
| **Mobile** | Flutter 3, Dart, BLoC Pattern |
| **Infrastructure** | Docker, Kubernetes, Terraform, AWS |
| **Messaging** | Apache Kafka (event streaming) |
| **AI/ML** | Qwen LLM, AI Vision API |

## Quick Start

```bash
# Clone all repositories (submodules)
git clone --recursive https://github.com/Little-Boy-s-TrueTrace/truetrace.git
cd truetrace

# Start all services with Docker Compose
cd truetrace-deployment
cp .env.example .env
docker compose up --build -d

# Access points (all through Nginx gateway on port 80):
# Customer Portal:       http://localhost
# Compliance Dashboard:  http://localhost/soc/
# Kafka UI:              http://localhost:9000
```

## Regulatory References

- **Law on Anti-Money Laundering 2022** (Law No. 14/2022/QH15)
- **Decree 19/2023/ND-CP** -- Guidelines for implementing the AML Law
- **Circular 09/2023/TT-NHNN** -- Suspicious Transaction Reporting
- **CTR Thresholds**: 300 million VND (cash) / 500 million VND (electronic)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
