# 🔄 Online Learning (Incremental Learning)

This repository contains concise and structured notes on **Online Learning**, a machine learning paradigm designed for **streaming, large-scale, and continuously evolving data**. These notes are adapted from my Notion study material and are suitable for **students, interviews, and quick revision**.

---

## 🚀 What is Online Learning?

Online Learning is a machine learning approach where the model **updates itself incrementally** as new data arrives. Instead of training once on a full dataset, the model learns **one data point or a small batch at a time**, making it highly adaptive to change.

This approach is ideal when datasets are **too large to fit into memory** or when data is generated continuously.

---

## 🧠 Key Characteristics

- Incremental model updates
- Works with **data streams** and mini-batches
- Low memory consumption
- Fast adaptation to new patterns
- Better handling of **concept drift**

---

## ⏱️ When to Use Online Learning

Online Learning is preferred when:

- 📊 Data arrives continuously (streaming data)
- 🌍 Data distribution changes over time
- 💾 Dataset is too large to fit in memory
- ⚡ Real-time or near real-time predictions are required
- 🔁 Frequent model updates are needed

### ✅ Common Use Cases

- Recommendation systems
- Fraud detection
- Stock price prediction
- Online advertising (CTR prediction)
- IoT and sensor data processing

---

## ⚙️ How to Implement Online Learning

### 1️⃣ Data Stream Processing

- Process data one instance at a time or in mini-batches
- No assumption of full dataset availability

### 2️⃣ Incremental Model Updates

- Update model parameters after each data point
- Commonly uses gradient-based optimization (e.g., SGD)

### 3️⃣ Continuous Evaluation

- Uses **prequential evaluation** (predict → learn → evaluate)
- Performance is monitored continuously

### 4️⃣ Concept Drift Handling

- Sliding windows
- Decay factors (recent data weighted more)

---

## 📉 Learning Rate

### 🔹 What is Learning Rate?

The **learning rate (η)** controls how much model parameters change when new data arrives.

### ⚖️ Trade-offs

- 🔼 High learning rate → Fast learning, unstable updates
- 🔽 Low learning rate → Stable updates, slow adaptation

### 🛠️ Common Strategies

- Constant learning rate
- Time-decayed learning rate
- Adaptive optimizers (AdaGrad, RMSProp, Adam)

---

## 💾 Out-of-Core Learning

### 🔹 What is Out-of-Core Learning?

Out-of-Core Learning enables training on datasets that **do not fit into memory** by loading data in **small chunks**.

### 🔗 Relation to Online Learning

- Often combined with online or mini-batch learning
- Enables scalable learning on massive datasets

### ✅ Benefits

- Minimal memory usage
- Suitable for big data environments

---

## ⚠️ Disadvantages of Online Learning

- ❌ Sensitive to noisy and outlier data
- ❌ Difficult to debug due to continuous updates
- ❌ Highly sensitive to learning rate selection
- ❌ Risk of catastrophic forgetting
- ❌ Complex evaluation compared to batch learning

---

## 🔁 Online Learning vs Batch Learning

| Feature       | Online Learning | Batch Learning |
| ------------- | --------------- | -------------- |
| Learning Type | Incremental     | Offline        |
| Data Handling | Streaming       | Static         |
| Adaptability  | High            | Low            |
| Memory Usage  | Low             | High           |
| Concept Drift | Better Handling | Poor Handling  |

---

## 📝 Summary

Online Learning is powerful for **dynamic and real-time systems**, offering adaptability and scalability. However, it requires careful tuning, monitoring, and evaluation to avoid instability.

---

⭐ If you find these notes useful, consider starring the repository!
