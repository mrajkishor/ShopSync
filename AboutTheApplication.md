
## 🛍️ **What is ShopSync?**

**ShopSync** is a smart digital assistant for shopkeepers. It helps small shops manage their **sales**, **inventory**, and **supplier restocking** efficiently, even if the shopkeeper is **offline** or not very tech-savvy.

The system has two main parts:

1. **IMS App** – For shopkeepers to create invoices, track inventory, and manage sales.
2. **ShopSync AI Engine** – Works behind the scenes to **predict demand**, **suggest suppliers**, and **optimize delivery**.

---

## 🔄 **How It Works – Step-by-Step**

### 1. **Shopkeeper uses the mobile app**

* They create invoices for each sale (e.g., sold 20 packets of biscuits).
* The app tracks which items are running low (inventory).
* This data is stored locally (offline) and synced to the cloud later.

> 📱 *“The app helps me print invoices, manage stock, and remember when to reorder.”* – a typical shopkeeper

---

### 2. **Demand Prediction (Edge AI on Mobile)**

* The app uses AI (TensorFlow Lite) to **predict demand locally**.
* For example: "You may need 80 bread packets this weekend."
* This forecast is based on past sales stored in the app.

> 🤖 *“Even if I’m offline, the app tells me what I might run out of soon.”*

---

### 3. **Smart Restocking (Cloud AI + DAG Scheduler)**

* When internet is available, ShopSync sends the data to the cloud.
* A **DAG Scheduler** in the cloud checks:

  * Which items are low?
  * Which suppliers are nearby and available?
  * Can multiple orders be combined?
* It uses a **GNN model** (Cloud AI) to **suggest the best supplier** based on reliability, delivery time, and cost.

> 🧠 *“It combines data from all shops to suggest that ‘Anil Traders’ is the best supplier near me.”*

---

### 4. **Automated Task Orchestration**

* The **distributed task scheduler** (like a smart manager) runs tasks in order:

  1. Forecast demand ➝
  2. Find supplier ➝
  3. Place order ➝
  4. Track delivery status ➝
  5. Update inventory
* This sequence is represented as a **Directed Acyclic Graph (DAG)**.

> ⚙️ *“Behind the scenes, tasks are connected in a smart chain – if one fails, it retries.”*

---

### 5. **If Something Fails – Retry and DLQ**

* If a task (like placing an order) fails, the system **retries** it 3 times with increasing delay.
* If it still fails, it goes to a **Dead Letter Queue (DLQ)** for manual review.

> 🔁 *“The app is reliable – it retries tasks if there’s a network issue or API fails.”*

---

### 6. **Analytics and Dashboards (MFE Web App)**

* On the web dashboard (Nx + Webpack), shopkeepers or admins can:

  * See sales trends
  * Monitor inventory
  * Track supplier performance
  * View delivery status

> 📊 *“The web dashboard helps me understand what’s selling, and what I need to stock more of.”*

---

### 7. **Tech Summary (For Teachers)**

| Feature                 | Tech Used                                           |
| ----------------------- | --------------------------------------------------- |
| Mobile App              | React Native + SQLite + DynamoDB                    |
| Forecasting             | TensorFlow Lite (Edge AI)                           |
| Supplier Recommendation | PyTorch GNN (Cloud AI)                              |
| Scheduler               | Spring Boot DAG Scheduler + Redis + Kafka           |
| Frontend Web App        | Next.js with Micro Frontends (MFE via Nx + Webpack) |
| Deployment              | Docker + Kubernetes (Minikube)                      |
| Observability           | Prometheus + Grafana                                |
| Retry + DLQ             | Redis ZSET + Kafka                                  |
| Auth & Security         | JWT + RBAC                                          |

---

## 👩‍🏫 This Project

* ✅ Demonstrates **AI + Distributed Systems** in one integrated project.
* ✅ Uses **Edge + Cloud computing** — a current research trend.
* ✅ Follows **software engineering best practices**: microservices, MFE, retries, monitoring, security etc.
* ✅ Shows **startup potential** with practical real-world value.

