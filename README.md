# ShopSync: Edge-Powered Inventory and Logistics Suite

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Version](https://img.shields.io/badge/version-1.0.0-blue)

**ShopSync** is an AI-driven inventory and logistics optimization platform for small and medium businesses (SMBs), integrated with **IMS-Invoice-services**, a mobile-first invoicing app for shopkeepers. Powered by a custom **distributed task scheduler**, **Edge AI**, and **Cloud GNN**, ShopSync enables shopkeepers to manage sales, inventory, and suppliers efficiently while optimizing restocking and logistics with real-time insights.

This project is developed as part of an MCA final-year project, targeting Indian retail SMBs ($20B+ market). It showcases advanced system design, machine learning, and distributed computing, with applications in retail logistics, crowdsourced data, and supplier optimization.

---

## 📖 Introduction

ShopSync empowers shopkeepers with a seamless solution for daily operations and strategic decision-making:
- **IMS-Invoice-services**: A React Native/Next.js app for sales tracking, GST-compliant invoicing, inventory management, and supplier tracking.
- **ShopSync Core**: An AI-driven suite using **Edge AI** (TensorFlow Lite) for demand forecasting, **Cloud GNN** (PyTorch) for supplier recommendations, and a **Spring Boot-based distributed task scheduler** for logistics optimization.
- **Key Scenarios**:
  - Real-time supplier selection (e.g., “Order from Anil Traders, 2 hours”).
  - Crowdsourced supplier database (e.g., “100 shopkeepers trust Anil Traders”).
  - Shopkeeper-as-supplier order optimization (e.g., “Combine Suresh’s order, save 30 minutes”).
  - Deduplication of supplier data for accuracy.

Built for non-tech-savvy shopkeepers, ShopSync offers a simple UI (Hindi support), offline capabilities, and scalability for thousands of users. The project demonstrates enterprise-grade system design (Kubernetes, Kafka, GNN) and shows scalable startup potential in the Indian retail market.

---

## ✨ Features

- **Invoicing and Operations (IMS)**:
  - Sales tracking, GST-compliant invoice generation (PDF, WhatsApp share).
  - Inventory management with low-stock alerts.
  - Supplier management with shopkeeper-as-supplier role.
  - Offline support (SQLite), cloud sync (DynamoDB/PostgreSQL).
- **AI-Driven Optimization (ShopSync)**:
  - **Edge AI**: Local demand forecasting (e.g., “80 packets needed Friday”).
  - **Cloud GNN**: Supplier reliability prediction, recommendations (e.g., “Anil Traders, 95% reliable”).
  - Crowdsourced supplier database for community-driven insights.
- **Distributed Task Scheduler**:
  - DAG-based task execution for supplier selection, delivery optimization, order combining.
  - Retry logic, idempotency, distributed locking (Redis).
  - Scalable with Kubernetes, Kafka for async processing.
- **Observability**:
  - Prometheus metrics, Grafana dashboards for task latency, supplier performance.
  - Structured logging (SLF4J) with correlation IDs.
- **Security**:
  - JWT-based authentication, role-based access control.
  - Secure APIs, RBAC for Kubernetes deployment.
- **Scalability**:
  - Horizontal scaling of workers (Kubernetes).
  - Rate limiting, throttling (Redis token bucket).

---

## 🏗️ Architecture

![Architecture Diagram](docs/architecture.png) *(Placeholder: Diagram in `docs/` ...to be added...)*

- **Frontend**:
  - Mobile: React Native (IMS app, ShopSync insights).
  - Web: Next.js (responsive dashboard, POS support).
- **Backend**:
  - **IMS**: AWS Lambda, DynamoDB, SQLite (offline).
  - **ShopSync**: Spring Boot (scheduler), AWS SageMaker (GNN), TensorFlow Lite (Edge AI).
  - **Scheduler**: Redis (task queuing), Kafka (DLQ), PostgreSQL (persistent storage).
- **AI Components**:
  - Edge AI: Demand forecasting on shopkeeper devices.
  - Cloud GNN: Graph-based supplier optimization (PyTorch Geometric).
- **DevOps**:
  - Docker Compose for local setup.
  - Kubernetes (Minikube/K3s) for deployment.
  - GitHub Actions for CI/CD.

---

## 🛠️ Tech Stack

| **Component**         | **Technology**                          |
|-----------------------|-----------------------------------------|
| **Frontend**          | React Native, Next.js, Tailwind CSS     |
| **Backend**           | Spring Boot, AWS Lambda, Node.js        |
| **Database**          | PostgreSQL, DynamoDB, SQLite, Redis     |
| **AI**                | TensorFlow Lite, PyTorch Geometric, SageMaker |
| **Messaging**         | Kafka (DLQ, async tasks)                |
| **Scheduler**         | Spring Boot, DAG executor               |
| **DevOps**            | Docker, Kubernetes, GitHub Actions      |
| **Observability**     | Prometheus, Grafana, SLF4J              |
| **Security**          | JWT, RBAC, Redis SETNX                  |

---

## 🚀 Getting Started

### Prerequisites
- **Node.js** (v16+)
- **Java** (JDK 17)
- **Python** (3.8+)
- **Docker** & **Docker Compose**
- **Kubernetes** (Minikube/K3s)
- **AWS CLI** (for cloud deployment)
- **Redis**, **Kafka**, **PostgreSQL** (via Docker)

### Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/shopsync.git
   cd shopsync
   ```

2. **Set Up Environment**:
   - Copy `.env.example` to `.env` and configure:
     ```bash
     cp .env.example .env
     ```
     Update AWS credentials, database URLs, JWT secret.

3. **Install Dependencies**:
   - Frontend (IMS):
     ```bash
     cd frontend/ims
     npm install
     ```
   - Backend (Scheduler):
     ```bash
     cd backend/scheduler
     mvn clean install
     ```
   - AI (GNN):
     ```bash
     cd ai/gnn
     pip install -r requirements.txt
     ```

4. **Run Locally with Docker Compose**:
   ```bash
   docker-compose up -d
   ```
   - Services: Redis, Kafka, PostgreSQL, IMS API, Scheduler, GNN inference.

5. **Access the App**:
   - Mobile: Run React Native app (`npm run start`).
   - Web: Open `http://localhost:3000` (Next.js).
   - API: `http://localhost:8080/api/tasks` (Scheduler).

---

## 🌐 Deployment

### Local Deployment (Minikube)
1. Start Minikube:
   ```bash
   minikube start
   ```
2. Apply Kubernetes manifests:
   ```bash
   kubectl apply -f k8s/
   ```
3. Access services via Minikube IP.

### Cloud Deployment (AWS)
1. Configure AWS CLI with credentials.
2. Deploy scheduler and GNN:
   ```bash
   cd deploy/aws
   ./deploy.sh
   ```
3. Monitor via Grafana (`http://grafana.shopsync-demo.com`).

### CI/CD
- GitHub Actions workflows in `.github/workflows/`:
  - `build.yml`: Test, build, lint.
  - `deploy.yml`: Push Docker images to ECR, deploy to Kubernetes.

---

## 📚 API Documentation

- **Scheduler APIs**:
  - `POST /api/tasks`: Submit a task (DAG-supported).
  - `GET /api/tasks/{id}`: Get task status.
  - Swagger: `http://localhost:8080/swagger-ui.html`
- **IMS APIs**:
  - `GET /suppliers`: Fetch supplier data.
  - `GET /sales`: Fetch sales data for AI.
  - Docs: `/docs/ims-api.md`

---

## 🤝 Contributing

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/your-feature`).
3. Commit changes (`git commit -m "Add your feature"`).
4. Push to branch (`git push origin feature/your-feature`).
5. Open a Pull Request.

Please follow the [Code of Conduct](CODE_OF_CONDUCT.md) and [Contributing Guidelines](CONTRIBUTING.md).

---

## 📝 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙏 Acknowledgments

- **MCA Guide**: For valuable feedback and guidance.
- **Shopkeepers**: For inspiring the project with real-world challenges.
- **Open Source**: TensorFlow, PyTorch, Spring Boot, and Kubernetes communities.
---

*Happy optimizing, shopkeepers! 🚀 Reach out at [mrajkishor331@gmail.com] for queries.*
