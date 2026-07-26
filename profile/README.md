# TrueTrace: Multi-Agent Deepfake & AML Autonomous Compliance System

<div align="center">

**Hệ thống tự động hóa tuân thủ phòng chống lừa đảo chuyên sâu và rửa tiền cho Ngân hàng bằng Multi-Agent AI**

[![Backend](https://img.shields.io/badge/Backend-Spring_Boot_3-6DB33F?style=for-the-badge&logo=spring-boot)](truetrace-backend/)
[![Engine](https://img.shields.io/badge/Engine-Python_3.11-3776AB?style=for-the-badge&logo=python)](truetrace-agent-engine/)
[![Dashboard](https://img.shields.io/badge/Dashboard-React_19-61DAFB?style=for-the-badge&logo=react)](truetrace-dashboard/)
[![Mobile](https://img.shields.io/badge/Mobile-Flutter-02569B?style=for-the-badge&logo=flutter)](truetrace-mobile-app/)

</div>

---

## 🎯 Vấn đề cần giải quyết

Các ngân hàng đang phải đối mặt với:

| Thách thức | Mô tả |
|---|---|
| 🎭 **Deepfake KYC Fraud** | Kẻ gian dùng AI giả mạo khuôn mặt/giọng nói để mở tài khoản ngân hàng ảo |
| 💰 **Mule Accounts** | Dòng tiền lừa đảo được chia nhỏ và dịch chuyển qua hàng trăm tài khoản trong vài phút |
| 📋 **Compliance Burden** | Nhân viên phải rà soát thủ công hàng ngàn giao dịch đáng ngờ để lập báo cáo STR |

## 🏗️ Kiến trúc Multi-Agent AI

TrueTrace triển khai mạng lưới 3 AI Agent phối hợp nhịp nhàng:

### Agent 1: Deepfake Inspector 🔍
> *Giám sát đầu vào KYC*

- Phân tích ảnh selfie và CCCD bằng AI Vision
- Phát hiện GAN artifacts, pixel noise, face swapping
- Xác thực CCCD (Căn cước công dân) 12 số
- Đối chiếu khuôn mặt selfie vs ảnh trên CCCD
- **Hành động**: Tự động APPROVE / REJECT / gửi MANUAL_REVIEW

### Agent 2: Money-Trail Graph Explorer 📊
> *Truy vết dòng tiền bất thường*

- Xây dựng đồ thị giao dịch real-time (Transaction Graph)
- Phát hiện mẫu Fan-out (1→N), Fan-in (N→1), Circular flow
- Phát hiện Structuring (chia nhỏ dưới ngưỡng báo cáo 200M VND)
- Phát hiện Velocity Anomaly (giao dịch bất thường tần suất cao)
- **Hành động**: Tự động phong tỏa tạm thời tài khoản đáng ngờ

### Agent 3: AML Report Generator 📝
> *Tự động lập hồ sơ pháp lý*

- Thu thập bằng chứng từ Agent 1 & Agent 2
- Sử dụng LLM (Qwen) tạo narrative bằng tiếng Việt
- Tạo Báo cáo Giao dịch Đáng ngờ (STR) theo Thông tư 09/2023/TT-NHNN
- **Hành động**: Báo cáo sẵn sàng để nhân viên bấm nút gửi trong 5 giây

## 📁 Cấu trúc dự án

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

## 🔧 Tech Stack

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

## 🚀 Quick Start

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

## 📜 Quy định pháp lý tham chiếu

- **Luật Phòng chống rửa tiền 2022** (Luật số 14/2022/QH15)
- **Nghị định 19/2023/NĐ-CP** — Hướng dẫn thi hành Luật PCRT
- **Thông tư 09/2023/TT-NHNN** — Báo cáo giao dịch đáng ngờ
- **Ngưỡng CTR**: 300 triệu VND (tiền mặt) / 500 triệu VND (điện tử)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
