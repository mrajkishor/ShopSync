

### ✅ **Phase-wise Breakdown (14–30 May)**

#### 🟩 **Phase 1: Finalize Core Features** (14–15 May)

**Goal**: Complete DAG Scheduler, DLQ, Retry

* [x] Finish `RetryHandler`, `DLQService`, `DelayQueuePoller`
* [x] Implement cycle detection + topological sort
* [ ] Create 2-3 sample DAG test cases
* [ ] Add status tracking (RUNNING → FAILED → RETRYING → COMPLETED)

> 🔚 **By 15 May**: DAG is working with retries + DLQ

---

#### 🟨 **Phase 2: Build & Connect Microservices** (16–20 May)

**Goal**: Inventory, Forecast, Logistics (Node.js/Java)

* [ ] Inventory service pulls invoice data
* [ ] Forecasting service (mocked Edge AI response)
* [ ] Logistics service calls DAG scheduler to plan delivery
* [ ] Redis/PostgreSQL integration where needed
* [ ] Create REST APIs for `/forecast`, `/inventory`, `/schedule`

> 🔚 **By 20 May**: All backend services working with mocked data

---

#### 🟦 **Phase 3: MFE Frontend + Analytics** (21–24 May)

**Goal**: UI to show stock levels, predictions, DAG status

* [ ] Set up Nx with MFE shell + modules (Inventory, Analytics)
* [ ] Inventory dashboard: Show items, alerts
* [ ] Forecast chart (use dummy predictions)
* [ ] DAG visual (or just JSON execution trace)
* [ ] Connect APIs to UI

> 🔚 **By 24 May**: Functional UI with real API hooks

---

#### 🟥 **Phase 4: Documentation, Testing & Deployment** (25–29 May)

**Goal**: Make it MCA + FAANG + demo-ready

* [ ] 25–26 May:

  * Final testing, screenshots, bug fixing
  * Prepare 5-min video: "Shopkeeper creates invoice → Edge AI predicts → DAG restocks"
* [ ] 27–29 May:

  * Write PDF report (25–30 pages)
  * Prepare PPT (15–20 slides)
  * Final README, research paper outline
  * Push all to GitHub, create release

---

#### 🚀 **30 May: Submission Day**

* Upload to LMS, bind report, present demo




