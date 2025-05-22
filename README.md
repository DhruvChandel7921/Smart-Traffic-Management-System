# 🚦 Smart Traffic Management System

An AI-powered adaptive traffic signal system that actually *gets* the jam! Say goodbye to the old-school fixed timers — this system dynamically adjusts traffic lights based on real-time vehicle density using computer vision. Built with YOLO, OpenCV, and Python magic. 💡🚗

---

## 📌 Project Overview

Modern cities deserve modern traffic solutions. This project is designed to:
- Detect real-time traffic density using CCTV footage and object detection.
- Adapt traffic signal timers based on vehicle load at each lane.
- Simulate intersection scenarios to compare this adaptive system with traditional static systems.

---

## 🧠 How It Works

### 1. 🚘 Vehicle Detection Module
- **Model**: YOLO (You Only Look Once)
- **Classes Detected**: Car, Bike, Bus/Truck, Rickshaw
- **Training**:
  - Images scraped from Google
  - Labeled with LabelIMG
  - Trained using pre-trained YOLO weights with custom class configuration
- **Detection Output**: JSON format with labels, confidence scores, and coordinates

### 2. 🔁 Signal Switching Algorithm
- Adjusts **green light duration** based on:
  - Number and type of vehicles detected
  - Average vehicle speeds and startup delays
  - Number of lanes and intersection-specific data
- Switches signals **cyclically** (not just based on the heaviest lane) to keep things fair
- Built-in logic to avoid starvation and optimize flow 🚦

### 3. 🎮 Simulation Module
- Created using **Pygame**
- Visualizes:
  - Real-time vehicle flow
  - Signal transitions
  - Vehicle counts per lane
  - Time-based performance comparison (static vs adaptive)
- Vehicles even turn at intersections for extra realism 👏

---

## 🛠 Tech Stack

| Tool | Use |
|------|-----|
| Python | Main programming language |
| YOLOv4/v5 | Object detection model |
| OpenCV | Image processing and drawing detections |
| LabelIMG | Manual dataset labeling |
| Pygame | Traffic simulation engine |

---

## 📊 Results

- Green signal durations auto-adjust based on vehicle count — e.g., from 10s to 33s
- Real-time processing enables pre-calculation during yellow phase ⏱️
- Major reduction in idle green time = less congestion + fuel savings

---

## 📁 Project Structure

Smart-Traffic-Management-System/
├── vehicle_detection/     # YOLO training + inference code
├── signal_algorithm/      # Timer and switching logic
├── simulation/            # Pygame-based UI & traffic sim
├── data/                  # Training images, labels
├── models/                # Trained YOLO weights
└── README.md              # You're here :)

🚀 Future Upgrades
• Integrate with live CCTV feeds

• Add weather or time-based signal optimization

• Hook up to city traffic APIs for macro-level control

👥 Authors
🚀 Project Team: Anadi Kantode,Dhruv Chandel,Abhishek Kushwaha,Aman Bhimte,Adarsh Mishra

💡 Inspired by the chaos of Indian traffic 😅

📜 License
MIT — use it, build on it, make traffic suck less.

🤝 Contributions
PRs welcome! If you’ve got ideas to make this even smarter, let’s collab!
