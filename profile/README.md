# TrueTrace: Multi-Agent Deepfake & AML Autonomous Compliance System

<div align="center">

**He thong tu dong hoa tuan thu phong chong lua dao chuyen sau va rua tien cho Ngan hang bang Multi-Agent AI**

[![Backend](https://img.shields.io/badge/Backend-Spring_Boot_3-6DB33F?style=for-the-badge&logo=spring-boot)](truetrace-backend/)
[![Engine](https://img.shields.io/badge/Engine-Python_3.11-3776AB?style=for-the-badge&logo=python)](truetrace-agent-engine/)
[![Dashboard](https://img.shields.io/badge/Dashboard-React_19-61DAFB?style=for-the-badge&logo=react)](truetrace-dashboard/)
[![Mobile](https://img.shields.io/badge/Mobile-Flutter-02569B?style=for-the-badge&logo=flutter)](truetrace-mobile-app/)

</div>

---

## Van de can giai quyet

Cac ngan hang dang phai doi mat voi:

| Thach thuc | Mo ta |
|---|---|
| **Deepfake KYC Fraud** | Ke gian dung AI gia mao khuon mat/giong noi de mo tai khoan ngan hang ao |
| **Mule Accounts** | Dong tien lua dao duoc chia nho va dich chuyen qua hang tram tai khoan trong vai phut |
| **Compliance Burden** | Nhan vien phai ra soat thu cong hang ngan giao dich dang ngo de lap bao cao STR |

## Kien truc Multi-Agent AI

TrueTrace trien khai mang luoi 3 AI Agent phoi hop nhip nhang:

### Agent 1: Deepfake Inspector
> *Giam sat dau vao KYC*

- Phan tich anh selfie va CCCD bang AI Vision
- Phat hien GAN artifacts, pixel noise, face swapping
- Xac thuc CCCD (Can cuoc cong dan) 12 so
- Doi chieu khuon mat selfie vs anh tren CCCD
- **Hanh dong**: Tu dong APPROVE / REJECT / gui MANUAL_REVIEW

### Agent 2: Money-Trail Graph Explorer
> *Truy vet dong tien bat thuong*

- Xay dung do thi giao dich real-time (Transaction Graph)
- Phat hien mau Fan-out (1->N), Fan-in (N->1), Circular flow
- Phat hien Structuring (chia nho duoi nguong bao cao 200M VND)
- Phat hien Velocity Anomaly (giao dich bat thuong tan suat cao)
- **Hanh dong**: Tu dong phong toa tam thoi tai khoan dang ngo

### Agent 3: AML Report Generator
> *Tu dong lap ho so phap ly*

- Thu thap bang chung tu Agent 1 & Agent 2
- Su dung LLM (Qwen) tao narrative bang tieng Viet
- Tao Bao cao Giao dich Dang ngo (STR) theo Thong tu 09/2023/TT-NHNN
- **Hanh dong**: Bao cao san sang de nhan vien bam nut gui trong 5 giay

## Cau truc du an

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
# Clone all repositories
git clone https://github.com/Little-Boy-s-TrueTrace/truetrace.git

# Start all services with Docker Compose
cd truetrace-deployment
cp .env.example .env
docker-compose up -d

# Access points:
# Web Client:  http://localhost (port 80)
# Dashboard:   http://localhost/soc
# Kafka UI:    http://localhost:9000
```

## Quy dinh phap ly tham chieu

- **Luat Phong chong rua tien 2022** (Luat so 14/2022/QH15)
- **Nghi dinh 19/2023/ND-CP** -- Huong dan thi hanh Luat PCRT
- **Thong tu 09/2023/TT-NHNN** -- Bao cao giao dich dang ngo
- **Nguong CTR**: 300 trieu VND (tien mat) / 500 trieu VND (dien tu)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
