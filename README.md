
---

# 🚗 **Driving Style Profiling Using Deep Autoencoders**  

Official Implementation of the Research Paper

📄 Vehicle Profiling Using Deep Autoencoders for Safety Applications

📌 About This Project

This repository contains the official implementation of our research paper, which focuses on using deep autoencoders to analyze and classify driving behavior. The goal is to develop driver-specific profiles and detect irregular driving patterns across different road conditions, including urban and highway driving scenarios.

🔹 **Goal**: Develop AI-based driving profiles for each user and assess driving irregularities in different road conditions.  
🔹 **Techniques Used**: **CNN & LSTM Autoencoders**, Time-Series Data Analysis, Reconstruction Loss Thresholding.  

---

## 📌 **Overview**  

🚦 **Why Driving Style Profiling?**  
Driving behavior is unique to each individual and varies across different road conditions. By creating **user-specific driving profiles**, this system can:  
✔ Detect irregular driving patterns (**potential theft or anomalies**).  
✔ Analyze **urban and highway driving** scenarios.  
✔ Improve **vehicular safety and monitoring**.  

👨‍💻 **How It Works?**  
- A deep **autoencoder model (CNN & LSTM-based)** is trained on driving sensor data.
- The trained model learns **the driving style** of a user based on time-series sequences.
- When tested on other users' data, the model computes **a reconstruction loss**.
- If the loss is above a threshold, it **flags the driving pattern as different** from the trained user.  

---


## 📊 **Dataset Description**  

The system was trained on **driving behavior data collected from vehicles**, including:  
- **Speed**  
- **Acceleration**  
- **Heading Degree**  
- **Transversal Acceleration**  
- **Combined Acceleration**  
- **Heading Rate**  
- **User-specific behavior data**  

### 🚲 **Dataset Variants**  
- **Urban Driving Data**: Captured from **bike riders** traversing the same path.  
- **Highway Driving Data**: Collected from **cars driving on a motorway**.  

---

## 🔥 **Model Architecture**  

Two **deep autoencoder architectures** were used to **profile driver behavior**:  

### **1️⃣ Convolutional Autoencoder (CNN-AE)**
- **3 Conv1D Layers** (extract spatial & temporal features).  
- **Dropout Layers** (to prevent overfitting).  
- **Conv1DTranspose Layers** (to reconstruct input sequences).  
- **Mean Squared Error (MSE) Loss Function**.  
- **Adam Optimizer (LR=0.001)**.  

### **2️⃣ LSTM Autoencoder (LSTM-AE)**
- **LSTM Encoder** to capture temporal dependencies.  
- **LSTM Decoder** to reconstruct the input driving sequences.  
- **Better suited for sequential patterns in driving data.**  

📈 **Loss Function:** Mean Squared Error (MSE)  
⚙ **Optimizer:** Adam  

---


## 🚀 **Results & Findings**  

📊 **Key Insights from the Research**:  
✔ The **trained user** consistently had the **lowest reconstruction loss**.  
✔ **Other users driving the same path** had **higher losses**, showing distinct driving styles.  
✔ **LSTM performed better** in capturing **temporal driving behaviors** than CNN.  
✔ The system successfully **detected abnormal driving styles** that deviated from the trained profile.  

---

## 🔧 **Adjusting Sensitivity of the System**  

You can **tune the threshold factor** to make the system **more or less sensitive**:
```python
threshold = average_training_loss * 2  # Modify this multiplier as needed
```
- **Higher Threshold** → Fewer alerts, more tolerance for variation.  
- **Lower Threshold** → More sensitivity to driving pattern changes.  

---

## 📌 **Potential Applications**  

🚗 **Security & Anti-Theft Monitoring**  
✔ Detect unauthorized vehicle usage.  
✔ Alert when a different driver operates the vehicle.  

📊 **Driving Behavior Analytics**  
✔ Profile drivers for insurance & fleet management.  
✔ Identify reckless or aggressive driving.  

🏎 **Autonomous Vehicles**  
✔ Improve safety by learning user driving styles.  
✔ Adaptive driving recommendations.  

---

## 🎯 **Future Improvements**  
🔹 Integrate **real-time streaming data** from onboard sensors.  
🔹 Expand training to **more road environments**.  
🔹 Develop a **mobile app interface** for real-time monitoring.  
🔹 Implement **real-time anomaly detection**.  

---

## 🤝 **Contributing**  
Contributions are welcome! Feel free to:  
✔ Open an **Issue** for bugs & suggestions.  
✔ Submit **Pull Requests** for improvements.  

---

## 📜 **Reference Paper**  
This work is based on:  
📄 **"Driving Style Profiling Using Deep Autoencoders for Safety Applications in Urban and Highway Scenarios"**  

🔗 **Read the Paper**: [Vehicle Profiling Paper](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://www.researchgate.net/publication/382924724_Driving_Style_Profiling_Using_Deep_Autoencoders_for_Safety_Applications_in_Urban_and_Highway_Scenarios&ved=2ahUKEwjYsuKkwNuLAxWpLVkFHR4qME0QFnoECBMQAQ&usg=AOvVaw2hdZGnT__hYW81XeV_lTTT)  

---

## 📧 **Contact**
For queries, reach out at **dhanyakrishnan4502@gmail.com**  

---
