
### ✅ **ShopSync MCA Project Checklist**

---

### 🔹 Phase 1: Planning & Requirements (Week 1)
- [ ] Define project objective and problem statement
- [ ] Identify target users: shopkeepers, suppliers
- [ ] Finalize modules: Invoicing, Inventory, Forecasting, DAG Scheduler, Supplier Insights
- [ ] Choose tech stack: React Native, Spring Boot, Redis, Kafka, PostgreSQL, TensorFlow Lite, PyTorch GNN
- [ ] Draft system architecture diagram (microservices + edge + cloud)
- [ ] Draft database schema and Redis/Kafka schema
- [ ] Prepare project timeline (Gantt chart or Trello)

---

### 🔹 Phase 2: Core Modules Development (Weeks 2–6)

#### 🧾 IMS (Invoice + Inventory Management)
- [ ] Create user authentication (JWT)
- [ ] Build invoice CRUD APIs (items, totals, tax)
- [ ] Create inventory management module (low stock alert)
- [ ] Build frontend (React Native + Next.js with MFE)
- [ ] Enable offline support (SQLite) and sync (PostgreSQL)

#### 🔁 Distributed Task Scheduler
- [ ] Design Task, Job, DAG entities
- [ ] Implement Redis ZSET queue and priority logic
- [ ] Create POST `/tasks` API with tenant and delay support
- [ ] Build delay poller (Redis + Spring @Scheduled)
- [ ] Add retry logic with exponential backoff
- [ ] Push failed tasks to DLQ (Redis List)

#### ⚙️ Forecasting Module
- [ ] Train local demand prediction model (TensorFlow Lite)
- [ ] Build Edge AI script to run predictions from sales data
- [ ] Sync prediction result to cloud using API
- [ ] Add supplier restocking logic triggered by forecast

#### 🌐 Supplier Intelligence (Cloud GNN)
- [ ] Prepare supplier graph dataset (JSON or synthetic)
- [ ] Train simple GNN (PyTorch Geometric)
- [ ] Serve GNN as REST API for reliability prediction
- [ ] Integrate GNN results into supplier suggestions

---

### 🔹 Phase 3: Integration, Testing & Observability (Weeks 7–8)
- [ ] Integrate all modules: Forecast → Scheduler → Inventory
- [ ] Add task status tracking (GET `/tasks/{id}`)
- [ ] Create analytics dashboard (sales, stock, predictions)
- [ ] Add Prometheus metrics + Grafana dashboard
- [ ] Log events (SLF4J) and set correlation ID per task
- [ ] Manually test all modules + write test report

---

### 🔹 Phase 4: Documentation & MCA Report (Weeks 9–10)
- [ ] Write system documentation (API, modules, deployment)
- [ ] Add screenshots of app, APIs, Grafana, logs
- [ ] Include UML diagrams: DFD, ER, flowchart, class
- [ ] Write research paper: Edge AI + DAG scheduling
- [ ] Complete Annexure A, guide certificate, summary
- [ ] Finalize project in GitHub + prepare submission ZIP

---

### 📁 **Expected Deliverables**
- [ ] Full codebase with modular structure
- [ ] README with architecture, API usage
- [ ] 20–30 page project report (PDF)
- [ ] PPT for viva (10–15 slides)
- [ ] Demo video (offline + online use case)
- [ ] Research paper draft (IEEE or academic format)

