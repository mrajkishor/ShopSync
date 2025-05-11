

## 🛍️ **ShopSync: Simplified Overview for Users and Evaluators**

### 🔎 What is ShopSync?

**ShopSync** is a smart mobile and web-based application designed to help small shopkeepers manage their shop more efficiently. It acts like a personal assistant that helps track inventory, forecast product demand, and find trusted suppliers — even when the shopkeeper is offline.

---

### 🧰 What Does It Do?

#### 1. **Invoice & Inventory Management**

* Shopkeepers can easily generate and share invoices (PDF or WhatsApp).
* Tracks how much stock is available.
* Alerts when stock is low (e.g., "Only 5 packets of milk left").

#### 2. **Smart Demand Forecasting**

* Predicts how much stock is needed in the coming days.
* Example: "You’ll need 50 bread packets on Friday."

#### 3. **Supplier Recommendation**

* Suggests the best supplier based on past performance and prices.
* Example: "Anil Traders delivers fastest and has best ratings."

#### 4. **Order Optimization**

* Combines orders from nearby shops to save delivery time and money.
* Example: "Combine order with Suresh’s shop — save ₹40."

#### 5. **Offline & Online Support**

* Works without the internet and syncs later when online.
* Stores data safely in local storage and cloud.

---

### 🔬 How Does It Work (Behind the Scenes)?

#### 1. **Edge AI (On Device)**

* Forecasts demand using AI on the shopkeeper’s phone using TensorFlow Lite.
* Doesn’t need constant internet connection.

#### 2. **Cloud GNN (Graph Neural Networks)**

* Learns from thousands of shopkeepers' data to suggest better suppliers.
* Uses cloud servers to process patterns and make recommendations.

#### 3. **DAG-Based Task Scheduler**

* Tasks like restocking or deliveries are handled in sequence (like a to-do list with dependencies).
* Ensures everything happens in the right order, even if a step fails.

#### 4. **Data Storage & Communication**

* Uses Redis and PostgreSQL to store task data.
* Uses Kafka to handle task failures and retries.

---

### 📲 How a Shopkeeper Uses It (Example)

1. **Login** with mobile number.
2. Add items sold (e.g., milk, biscuits).
3. App **tracks sales** and **reduces stock**.
4. Based on past sales, app **forecasts demand**.
5. App **suggests supplier** based on other users' reviews.
6. Generates invoice, sends it to customer via **PDF/WhatsApp**.
7. Works **offline** if no internet; syncs later.

---

### 💡 Benefits to Shopkeepers

| Feature                 | Benefit                                    |
| ----------------------- | ------------------------------------------ |
| Demand Forecasting      | Avoid overstocking or running out of stock |
| Supplier Recommendation | Save time and money with best options      |
| Invoice Generator       | GST-compliant, shareable                   |
| Offline Mode            | Works anytime, anywhere                    |
| Community Insights      | Learn from what nearby shops are doing     |

---

### 📊 Who Should Use It?

* Small shop owners (Kirana, General stores)
* Retailers in towns and cities
* Shopkeepers who face stock or supplier problems

---

### 📚 For MCA Evaluation

| Evaluation Area    | Coverage                                 |
| ------------------ | ---------------------------------------- |
| **System Design**  | DAG Scheduler, Edge AI, Microservices    |
| **AI Integration** | TensorFlow Lite (offline) + GNN (cloud)  |
| **Research Scope** | Retail AI, task scheduling, supply chain |
| **Practical Use**  | Real-world impact on Indian SMBs         |
| **Innovation**     | Combines offline AI + supplier networks  |

