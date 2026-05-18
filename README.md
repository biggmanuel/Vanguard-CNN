# Vanguard CNN Engine 🛡️

**Developer:** Emmanuel Etim Udo  
**Institution:** University of Calabar (UNICAL), Department of Computer Science  

## Project Overview
The Vanguard CNN Engine is an autonomous, context-aware deep learning application designed to intercept and neutralize social engineering attacks (phishing and smishing) in real-time. 

Unlike legacy security systems that rely on static, rule-based keyword filters and suffer from high false-positive rates, this engine utilizes a **1D-Convolutional Neural Network (CNN)** paired with Word2Vec embeddings. This allows the system to understand the spatial and semantic relationships of words, effectively catching zero-day threats and deliberate typographical evasions.

## Decoupled Cloud Architecture
This project implements an Agile, strictly decoupled microservice architecture to ensure enterprise-grade availability and resilience:
* **The Brain (AI Backend):** A Python-based FastAPI server running the TensorFlow/Keras 1D-CNN model.
* **The Router (Middleware):** A Firebase Realtime Database that acts as an autonomous routing manager, solving the dynamic IP problem of cloud computing.
* **The Body (Frontend):** A lightweight, static HTML/JS enterprise dashboard hosted on Netlify.

## Performance Metrics
The model was rigorously evaluated against a heavily class-imbalanced dataset of 5,500+ records, adopting standard multi-metric evaluation frameworks:
* **Accuracy (ACC):** 98.57%
* **Precision (PR):** 98.55%
* **False Positive Rate (FPR):** 0.0021 *(Virtually eliminates alert fatigue)*
* **Recall (RR):** 90.67%
* **F1-Score:** 94.44%
* **Validation Loss:** 0.0715

---

## 🚀 System Execution Guide

**IMPORTANT NOTE FOR EVALUATORS:** While the source code is available in this repository, the Vanguard CNN Engine utilizes a dynamic cloud architecture. To avoid local hardware constraints, bypass dependency issues, and perfectly replicate the autonomous Firebase routing described in the thesis, **please execute the backend via the provided Google Colab environment.**

### Phase 1: Booting the AI Backend
1. Open the interactive cloud notebook: **[INSERT YOUR GOOGLE COLAB LINK HERE]**
2. Ensure you are connected to a cloud runtime (`Runtime > Run all`).
3. *Note: The first cell will automatically fetch the `spam.csv` dataset directly from this GitHub repository. No manual uploads are required.*
4. The final cell will boot the FastAPI server and output a public Localtunnel URL. The Python script will autonomously push this new URL to the Firebase Realtime Database. The AI backend is now live.

### Phase 2: Accessing the User Interface
1. With the Colab backend actively running, open the live enterprise dashboard: **[https://socialengineeringcnn.netlify.app/cnnengine]**
2. *Note: No manual configuration is needed. The frontend will dynamically query Firebase, locate the active AI endpoint, and establish a secure connection.*

### Phase 3: Testing Threat Detection
1. **Benign Test:** Type a standard message (e.g., *"Are we still having the departmental meeting tomorrow?"*) and click Scan. The system will return a **SECURE** status.
2. **Zero-Day Test:** Type a manipulative payload (e.g., *"URGENT: Your UNICAL portal has been compromised. Click this link immediately to secure your account."*) and click Scan. The engine will intercept the spatial anomalies and trigger a **CRITICAL THREAT** block.

---
*Built as a B.Sc. Computer Science Thesis Project — 2026*
