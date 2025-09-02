
# **Context-Aware CAN Bus Anomaly Detection with LSTM & LSTM-VAE**

![CAN Bus](https://img.shields.io/badge/CAN%20Bus-Security-blue) ![Python](https://img.shields.io/badge/Python-3.8%2B-green) ![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange) ![License](https://img.shields.io/badge/License-MIT-purple)

## **📌 Overview**

This repository showcases the **research and implementation** of **context-aware anomaly detection** in automotive Controller Area Network (CAN) systems without requiring signal decoding (DBC files).  
The project introduces **LSTM Autoencoder** and **LSTM Variational Autoencoder (VAE)** models for identifying context-aware anomalies such as replay attacks, fuzzing, and timing deviations.

---

## **🚀 Key Features**

- **No-Decoding Paradigm** – Analyze CAN traffic as raw time-series data without proprietary decoding.  
- **Sequence-Aware Models** – LSTM and LSTM-VAE provide deep contextual understanding of CAN bus data.  
- **Replay & Fuzz Detection** – Accurately detects replayed or fuzzed CAN messages with minimal tuning.  
- **Visualization** – Generates anomaly scores, entropy heatmaps, and ID frequency spikes.  
- **Colab-Optimized** – Run the entire pipeline with GPU acceleration for rapid experimentation.

---

## **📊 Usage**

### **1️⃣ Prepare Logs**
Collect CAN logs for training and testing:
```bash
candump vcan0 -l > normal.log
candump vcan0 -l > attack.log
```

---

### **2️⃣ Run on Google Colab**
- Open `LSTM_VAE.ipynb` or `LSTM_Final.ipynb` in [Google Colab](https://colab.research.google.com/).  
- Upload your `normal.log` and `attack.log` files when prompted.  
- Execute each cell to preprocess data, train the model, and analyze anomalies.

---

### **3️⃣ Replay Attack Simulation**
Use `Replay.ipynb` to simulate replay attacks and validate detection performance.

---

## **📈 Outputs**

- **Top Anomalous CAN IDs** – Ranked by anomaly scores  
- **Entropy Heatmaps** – Payload randomness visualization  
- **Timing Deviations** – Highlights sequence and delta timing anomalies  
- **Score Plots** – Time-series graphs for anomaly scores over time  

---

## **🎤 DEF CON 33 Presentation**

This work was **presented live at DEF CON 33 on the Creator Stage** as part of the Car Hacking Village.  

🔗 [DEF CON Official Page](https://defcon.org/html/defcon-33/dc-33-creator-talks.html#content_60261)  
🔗 [Hacker Tracker Event Page](https://hackertracker.app/event/?conf=DEFCON33&event=61539)  
🔗 [Car Hacking Village DEF CON 33 Talks](https://www.carhackingvillage.com/defcon-33-talks)

---

## **🔬 Technical Details**

- **Model Architectures**: LSTM Autoencoder, LSTM Variational Autoencoder  
- **Loss Functions**:  
  - LSTM AE → Mean Squared Error (MSE)  
  - LSTM VAE → MSE + KL Divergence  
- **Input Features**:  
  - CAN ID  
  - Payload bytes (0-7)  
  - Delta timestamps (`delta_t`)  
  - Payload entropy  
- **Data Windowing**:  
  - Sliding window approach for sequence context  
  - Normalization for stable training  

---

## **🖥 Deployment Possibilities**

- **Telematics Gateways** – Lightweight, real-time model deployment  
- **Vehicle SOC (VSOC)** – Centralized analysis for fleets  
- **ECU Integration** – Embedded on-board anomaly alerts  

---

## **🤝 Contributing**

Pull requests are welcome. Please fork this repository, create a feature branch, and submit your changes via a PR.

---

## **📜 License**

This project is licensed under the **MIT License**.  

---

## **🙌 Acknowledgements**

Developed by **Ravi Rajput**, Principal Architect – NeoTech Global Pvt Ltd  
Presented exclusively at **DEF CON 33 Creator Stage** – Car Hacking Village.  
