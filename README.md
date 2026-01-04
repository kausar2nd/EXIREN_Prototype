# EXIREN – Multi-Modal Fire Detection System (Research Prototype)

EXIREN is a **research-oriented proof-of-concept (PoC)** for a multi-modal fire detection system that combines IoT sensors, AI-powered computer vision, and a real-time web dashboard. This repository contains the **technical implementation** of the system described in an **accepted (forthcoming) research paper**.

> **Status**: Paper accepted, publication pending. This repository reflects the experimental / prototype implementation used during the study.

---

## System Overview

EXIREN follows a three-stage detection pipeline designed to reduce false fire alarms:

1. **Primary Detection** – Continuous smoke monitoring via ESP32-based sensors
2. **AI Verification** – Vision-based fire confirmation using a lightweight YOLOv11n model when smoke thresholds are exceeded
3. **Safety Fallback** – Temperature-based emergency triggering for redundancy

The system emphasizes *verification before escalation*, rather than single-signal triggering.

---

## Key Features

- **AI-assisted Fire Detection** using a custom-trained YOLOv11n (nano) model
- **IoT-based Smoke & Temperature Monitoring** via ESP32
- **False-alarm Mitigation** through multi-modal verification
- **Live Video Streaming** with detection overlays
- **Real-time Web Dashboard** for monitoring and control
- **Configurable Thresholds** for experimental evaluation
- **Modular Backend–Frontend Architecture** (Flask + Web UI)

---

## Research Context

This codebase serves as the **proof-of-concept implementation** of a research study focused on **reducing false alarms in fire detection systems through multi-modal verification**.

- The **core idea and system design** are presented in an academic paper that has been **accepted and is awaiting publication**.
- No DOI or public citation is available at this time.
- Once published, bibliographic information will be added here.

> **Note**: This repository is not a production-ready system. It is intended for **research, experimentation, and reproducibility**.

---

## File Structure

```bash
├── app.py                    # backend
├── templates/
│   └── index.html            # dashboard
├── static/
│   ├── style.css             
│   └── script.js            
├── YOLOv11n_custom_fire.pt   # Custom-trained YOLO model
├── requirements.txt          
├── README.md               
```

---

## 📋 Requirements

### Hardware (optional for full system)

- ESP32 microcontroller (WiFi-enabled)
- MQ-2 smoke sensor
- LM35 temperature sensor
- USB camera / webcam
- Host machine (PC or edge device)

### Software

- Python 3.8+
- Modern web browser
- Local network (for ESP32 communication)

---

## Running the Prototype

### 1. Clone the Repository

```bash
git clone https://github.com/kausar2nd/EXIREN_Prototype.git
cd EXIREN_Prototype
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Hardware Setup (Optional)

If using physical sensors:

- Flash the ESP32 with the provided Arduino sketch
- MQ-2 → GPIO 35
- LM35 → GPIO 34
- Configure WiFi credentials in the ESP32 firmware

### 4. Model Setup

Ensure `YOLOv11n_custom_fire.pt` is present in the root directory.

### 5. Start the Application

```bash
python app.py
```

### 6. Access Dashboard

Open a browser and navigate to:

``` bash
http://localhost:5000
```

The system can also be run in **demo mode** without hardware.

---

## Limitations

- Threshold values are **experimental** and not calibrated for real deployments
- The system is **not certified** for safety-critical or commercial use
- Model performance depends heavily on camera placement and environment

---

## License

This project is licensed under the **Apache License 2.0**. See [`LICENSE`](LICENSE).

You are free to use, modify, and distribute the code in accordance with the license terms. The license also provides explicit patent protection.

---

## Citation (Coming Soon)

Once the paper is published, citation details will be provided here.

---

## Disclaimer

This repository represents a **research prototype**. The authors are not responsible for misuse, incorrect deployment, or safety-critical decisions made using this code.
