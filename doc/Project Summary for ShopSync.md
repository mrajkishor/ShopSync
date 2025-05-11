

## 🧾 MCA Final Year Project Summary

### 📌 Project Title:

**ShopSync: AI-Powered Inventory and Logistics Suite for Small Shopkeepers**

---

### 🎯 Objective:

To build a **smart platform** that helps small shopkeepers **manage inventory**, **predict product demand**, and **get faster, better supplier delivery suggestions**—even if the shop is offline or has poor internet.

---

### 🧩 Problem Solved:

Shopkeepers often:

* Forget to reorder items before stock runs out.
* Don’t know which supplier delivers faster or cheaper.
* Can’t predict how much stock they’ll need.
* Lose time manually managing invoices and inventory.

**ShopSync** solves this using:

* AI to forecast future demand based on past sales.
* A scheduler to automate task execution (like reordering).
* A mobile-first invoice + inventory app with offline support.

---

### ⚙️ Key Features:

* 🧾 **Invoice App**: Shopkeepers create and share GST-compliant invoices.
* 📦 **Inventory Tracking**: Alerts for low-stock items.
* 📊 **Demand Forecasting**: AI model predicts future needs.
* 🧠 **Smart Scheduling**: Automatically reorders using a task scheduler.
* 👥 **Supplier Suggestions**: Shows best suppliers based on ratings.
* 📴 **Offline Support**: Works without internet using Edge AI and syncs later.

---

### 🏗️ Technologies Used:

| Layer            | Tech                          |
| ---------------- | ----------------------------- |
| Frontend (App)   | React Native, Next.js         |
| Backend Services | Spring Boot, Node.js          |
| AI               | TensorFlow Lite, PyTorch GNN  |
| Database         | Redis, PostgreSQL, SQLite     |
| Messaging        | Kafka (for async processing)  |
| Hosting          | Docker, Kubernetes (Minikube) |

---

### 🧪 Sample Use Case:

1. Shopkeeper sells 100 packets of bread daily.
2. The app tracks this and AI predicts a spike on weekends.
3. A scheduled task triggers automatic restocking suggestions.
4. Supplier with fastest delivery is recommended.
5. Invoice app tracks the full flow with downloadable bills.

---

### 📁 Project Deliverables:

* ✔️ Working invoice + inventory app (mobile + web)
* ✔️ AI model for demand prediction (trained on sample sales data)
* ✔️ Distributed task scheduler with retry + dead letter queue (DLQ)
* ✔️ System design diagrams, code, documentation, and test cases
* ✔️ Optional: Research paper on Edge AI in retail automation

---

### 💡 Innovation:

* Edge AI runs even without internet.
* Graph Neural Network for choosing best suppliers.
* DAG-based scheduler handles smart reordering automatically.

---

### 📈 Real-World Use:

This project can be scaled as a **startup product** in India’s ₹20B+ small retail market.

