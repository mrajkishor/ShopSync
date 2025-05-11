
### Checklist for Starting and Executing ShopSync Project

#### Project Overview (Recap)
- **ShopSync** is a SaaS platform for shopkeepers/SMBs to optimize inventory, demand forecasting, and logistics using:
  - **Edge AI** (TensorFlow Lite) for offline demand predictions.
  - **Graph Neural Networks (GNNs)** for cloud-based forecasting.
  - **Distributed DAG Scheduler** for logistics (restocking, delivery).
  - **Microservices** (Node.js) and **MFE** (React/Module Federation) for scalability.
  - Integrates with your invoice app for sales data.
- **Goals**: FAANG-level tech, MCA marks, research paper, profitable SaaS startup, original work.
- **Timeline**: 6 months (assuming typical MCA project duration).

This checklist is divided into **phases** with actionable tasks, deliverables, and timelines. Each task is designed to keep your project on track, reusable with your side projects, and aligned with your goals.

---

### Phase 1: Planning and Research (Month 1)
**Objective**: Set a strong foundation with research, tools, and system design.
**Estimated Time**: 4 weeks

- [ ] **Define Scope and Requirements** (2 days)
  - Finalize features: Offline demand forecasting, inventory tracking, logistics scheduling, analytics dashboard, invoice app integration.
  - Document FAANG-level tech stack: Edge AI (TensorFlow Lite), GNNs (PyTorch), microservices (Node.js), MFE (React), DAG scheduler.
  - List MCA evaluation criteria: Demo, documentation, research paper, presentation.
  - **Deliverable**: 1-page project scope document (use Google Docs).

- [ ] **Research Key Technologies** (1 week)
  - **Edge AI**: Read TensorFlow Lite docs (https://www.tensorflow.org/lite) and 2-3 arXiv papers on “Edge AI retail” or “lightweight GNNs”.
  - **GNNs**: Study PyTorch Geometric (https://pytorch-geometric.readthedocs.io) and arXiv papers on “Graph Neural Networks supply chain”.
  - **DAG Scheduling**: Review Apache Airflow’s DAG concepts and 1-2 papers on “distributed task scheduling”.
  - **Microservices/MFE**: Check Module Federation docs (https://webpack.js.org/concepts/module-federation/).
  - **Deliverable**: Notes with 5-10 key insights from papers/docs (use Notion or Markdown).

- [ ] **Design System Architecture** (1 week)
  - Sketch microservices: Auth, Inventory, Forecasting, Logistics, Analytics.
  - Define MFE modules: Dashboard, Inventory, Logistics, Analytics.
  - Plan Edge AI pipeline: Local model (TensorFlow Lite) + cloud GNN (PyTorch).
  - Map DAG scheduler tasks: Restocking, delivery scheduling.
  - Plan invoice app integration: APIs for sales data.
  - **Deliverable**: Architecture diagram (use Draw.io or Lucidchart).

- [ ] **Set Up Development Environment** (3 days)
  - Install tools: VSCode, Node.js, Python, Docker, Kubernetes (minikube for local testing).
  - Set up your npm module for MFE pre-commit hooks (reuse your side project).
  - Install TensorFlow Lite, PyTorch, MongoDB, SQLite.
  - Configure AWS IoT Greengrass (free tier) for edge deployment testing.
  - **Deliverable**: Working dev environment with a “Hello World” microservice.

- [ ] **Identify Datasets** (3 days)
  - Use your invoice app’s dummy sales data (or generate synthetic data: shopkeeper sales, stock levels).
  - Explore open-source datasets: Kaggle’s “Retail Dataset” or “Supply Chain Shipment” datasets.
  - **Deliverable**: CSV file with sample data for training AI models.

- [ ] **Plan Research Paper** (2 days)
  - Choose topic: “Edge AI for Offline Inventory Management” or “Distributed DAG Scheduling for SMB Logistics”.
  - Outline sections: Intro, Related Work, Methodology, Experiments, Results.
  - **Deliverable**: 1-page paper outline.

**Phase 1 Milestones**:
- Project scope document.
- Research notes and architecture diagram.
- Working dev environment.
- Sample dataset and paper outline.

---

### Phase 2: Prototyping Core Components (Months 2-3)
**Objective**: Build and test Edge AI, DAG scheduler, and MFE frontend prototypes.
**Estimated Time**: 8 weeks

- [ ] **Develop Edge AI Model** (3 weeks)
  - Create a lightweight GNN model using TensorFlow Lite for offline demand forecasting.
  - Input: Sales data from invoice app (e.g., daily bread packet sales).
  - Output: Predictions (e.g., “50 packets needed tomorrow”).
  - Train on synthetic/retail dataset, prune model for edge devices (e.g., mobile, Raspberry Pi).
  - Test offline predictions on a local device.
  - **Deliverable**: Working Edge AI model (Python script + saved model).

- [ ] **Enhance DAG Scheduler** (2 weeks)
  - Reuse your existing DAG scheduler.
  - Add features: Resource constraints (e.g., supplier capacity), cost optimization (e.g., cheapest delivery route).
  - Implement cycle detection (DFS-based, as discussed).
  - Test with dummy logistics tasks: Restock 50 packets from Supplier A, deliver to Shop B.
  - **Deliverable**: Updated DAG scheduler code with test cases.

- [ ] **Build Microservices Backend** (2 weeks)
  - Develop core microservices:
    - **Inventory Service**: Tracks stock levels, pulls data from invoice app API.
    - **Forecasting Service**: Calls Edge AI model for predictions.
    - **Logistics Service**: Uses DAG scheduler for task orchestration.
  - Use Node.js/Express, MongoDB for cloud data, SQLite for edge.
  - Containerize with Docker.
  - **Deliverable**: 3 microservices with basic APIs (e.g., `/inventory`, `/forecast`, `/schedule`).

- [ ] **Create MFE Frontend Prototype** (1 week)
  - Reuse your e-commerce MFE framework (React/Module Federation).
  - Build one module: Inventory dashboard (shows stock levels, low-stock alerts).
  - Use Tailwind CSS for simple, shopkeeper-friendly UI.
  - Connect to Inventory Service API.
  - **Deliverable**: MFE dashboard prototype (deployed locally).

**Phase 2 Milestones**:
- Edge AI model predicting demand offline.
- Enhanced DAG scheduler with logistics test cases.
- 3 microservices with APIs.
- MFE dashboard prototype.

---

### Phase 3: Integration and Testing (Month 4)
**Objective**: Integrate components, add analytics, and test end-to-end.
**Estimated Time**: 4 weeks

- [ ] **Integrate Invoice App** (1 week)
  - Build APIs to pull sales data from your invoice app (e.g., daily sales CSV).
  - Feed data to Edge AI model for forecasting.
  - Test integration: Sales data → Inventory Service → Forecasting Service.
  - **Deliverable**: Working invoice app integration.

- [ ] **Add Analytics Service and Dashboard** (1 week)
  - Develop Analytics Service: Generates KPIs (sales trends, inventory turnover).
  - Add MFE module: Analytics dashboard (charts using Chart.js).
  - Connect to Inventory and Forecasting Services.
  - **Deliverable**: Analytics dashboard showing KPIs.

- [ ] **Deploy Edge AI to Devices** (1 week)
  - Use AWS IoT Greengrass to deploy Edge AI model to a test device (e.g., Raspberry Pi or laptop simulating POS).
  - Test offline predictions and edge-to-cloud sync.
  - **Deliverable**: Edge AI model running on a test device.

- [ ] **End-to-End Testing** (1 week)
  - Test full workflow: Invoice data → Edge AI forecast → Inventory update → DAG scheduler restocking → Analytics dashboard.
  - Check for bugs, performance (e.g., prediction latency), and cycle-free DAG execution.
  - **Deliverable**: Test report with 5-10 test cases (use Jest or Postman).

**Phase 3 Milestones**:
- Invoice app integrated with platform.
- Analytics dashboard deployed.
- Edge AI running on a device.
- End-to-end system tested.

---

### Phase 4: Deployment and Documentation (Month 5)
**Objective**: Deploy the platform, write documentation, and draft research paper.
**Estimated Time**: 4 weeks

- [ ] **Deploy SaaS Platform** (1 week)
  - Deploy microservices to Kubernetes (use AWS EKS or GCP free tier).
  - Host MFE frontend on Vercel or Netlify.
  - Set up MongoDB cloud instance (free tier).
  - Test cloud deployment: Dashboard, APIs, edge sync.
  - **Deliverable**: Live SaaS platform (accessible via URL).

- [ ] **Write Documentation** (1 week)
  - System design: Architecture, microservices, Edge AI pipeline, DAG scheduler.
  - Setup guide: How to run the project locally.
  - API docs: Endpoints for Inventory, Forecasting, Logistics.
  - **Deliverable**: 20-30 page documentation PDF.

- [ ] **Draft Research Paper** (2 weeks)
  - Write sections: Intro, Related Work, Methodology (Edge AI, DAG), Experiments, Results.
  - Experiment: Compare Edge AI predictions vs. baseline (e.g., linear regression).
  - Target: IEEE format, 6-8 pages.
  - **Deliverable**: Draft paper (submit to arXiv or MCA-affiliated journal).

**Phase 4 Milestones**:
- Deployed SaaS platform.
- Complete documentation.
- Draft research paper.

---

### Phase 5: MCA Presentation and Final Touches (Month 6)
**Objective**: Polish the project, prepare demo, and present for MCA evaluation.
**Estimated Time**: 4 weeks

- [ ] **Polish Demo** (1 week)
  - Enhance MFE dashboard: Add animations, better UX for shopkeepers.
  - Record a 5-min demo video: Show offline Edge AI, DAG scheduling, invoice integration.
  - **Deliverable**: Polished demo video.

- [ ] **Prepare Presentation** (1 week)
  - Slides: Intro, Problem (SMB inventory issues), Solution (ShopSync), Tech Stack, Demo, Research, Business Potential.
  - Highlight: Offline capability, shopkeeper focus, FAANG-level tech.
  - **Deliverable**: 15-20 slide PPT.

- [ ] **Final Testing and Bug Fixes** (1 week)
  - Stress-test: Run system with 1000+ dummy transactions.
  - Fix UI bugs, optimize API response times.
  - **Deliverable**: Bug-free system.

- [ ] **Submit and Present** (1 week)
  - Submit: Code (GitHub repo), documentation, paper, demo video.
  - Practice presentation: Focus on shopkeeper impact, tech innovation.
  - Present to MCA evaluators.
  - **Deliverable**: Successful MCA submission and presentation.

**Phase 5 Milestones**:
- Polished demo and presentation.
- Bug-free system.
- MCA submission and presentation done.

---

### Additional Tips
- **Reuse Existing Work**:
  - Invoice app APIs for data integration.
  - E-commerce MFE framework for frontend.
  - DAG scheduler for logistics.
  - npm module for code quality.
- **Time Management**:
  - Use a tool like Trello or Notion to track tasks.
  - Dedicate 10-15 hours/week to stay on track.
- **Research Support**:
  - Join arXiv, Google Scholar for papers.
  - Check TensorFlow Lite tutorials (YouTube/Google).
- **FAANG Prep**:
  - Document system design (e.g., scalability, fault tolerance) for interviews.
  - Practice explaining Edge AI and DAG in 2 minutes.
- **Startup Plan**:
  - After MCA, pitch ShopSync to local shopkeepers for beta testing.
  - Explore angel investors or incubators (e.g., Y Combinator).

---

### Quick Checklist Summary
1. **Month 1**: Scope, research (Edge AI, GNNs, DAG), architecture, dev setup, dataset, paper outline.
2. **Months 2-3**: Edge AI model, DAG scheduler, microservices, MFE dashboard.
3. **Month 4**: Invoice integration, analytics, edge deployment, end-to-end testing.
4. **Month 5**: Cloud deployment, documentation, research paper.
5. **Month 6**: Demo polish, presentation, final testing, MCA submission.

---

### Deliverables Recap
- **Code**: GitHub repo with microservices, MFE, Edge AI, DAG scheduler.
- **Demo**: Live SaaS platform + 5-min video showing offline predictions, logistics, dashboard.
- **Documentation**: 20-30 page PDF (system design, APIs, setup).
- **Research Paper**: 6-8 page draft on Edge AI or DAG scheduling.
- **Presentation**: 15-20 slide PPT for MCA evaluators.
