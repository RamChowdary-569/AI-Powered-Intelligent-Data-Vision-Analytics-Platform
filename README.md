# 🪖 Real-Time Soldier Health & Location Monitoring System

> **An end-to-end, production-grade IoT data engineering project** that ingests, processes, aggregates, and visualizes real-time soldier health and location telemetry from wearable devices — presented as a single, cohesive pipeline.

This project demonstrates **enterprise-level data engineering skills**, including real-time ingestion, micro-batch streaming, time-window aggregation, analytical storage, and dashboard visualization.

---

## 📌 Project Summary

Modern defense, rescue, and emergency-response operations require **continuous awareness of personnel health and movement**.  
This system simulates wearable devices attached to soldiers and processes telemetry data in near real time.

### 📊 Metrics Monitored
- ❤️ Heart Rate
- 🌡 Body Temperature
- 📍 GPS Location (Latitude & Longitude)

---

## 🏗 End-to-End Architecture

Wearable Devices (Simulated)
↓
FastAPI Ingestion Service
↓
MySQL (Raw Telemetry Tables)
↓
Streaming Processor (Micro-Batch)
↓
Aggregation Engine (5-Min Rolling Windows)
↓
MySQL (Analytics Tables)
↓
Streamlit Dashboard



---

## 🧠 Core Capabilities

- 📡 Real-time ingestion of IoT telemetry  
- 🔄 Dual analytics modes: **Live (Raw)** and **Aggregated (5-Min)**  
- ⏱ Time-windowed aggregation for scalable analytics  
- 📊 Interactive dashboard with KPIs and filters  
- 🗺 Live GPS-based soldier tracking  
- 🚨 Alert-ready architecture for health threshold breaches  
- 🧩 Modular, scalable, production-oriented pipeline  

---

## 🛠 Technology Stack

### Languages
- Python
- SQL (MySQL)

### Backend & Data Engineering
- FastAPI – High-performance ingestion API  
- MySQL 8.0 – Raw and aggregated telemetry storage  
- Custom Streaming Processor – Micro-batch processing  
- Time-window Aggregation Engine – 5-minute rolling windows  

### Visualization
- Streamlit – Interactive analytics dashboard  

### Pipeline & DevOps
- Python Virtual Environment (`venv`)  
- Modular ETL architecture  
- Scheduler-ready (Cron / Airflow compatible)

---

## 📂 Project Structure

iot-health-data-engineering/
│
├── ingestion/
│ └── api.py # FastAPI ingestion service
│
├── data/
│ ├── raw/ # Raw IoT telemetry (JSON)
│ ├── processed/ # Processed stream outputs
│ └── realtime_generator.py # Wearable device simulator
│
├── spark/
│ ├── stream_processor.py # Streaming processor
│ ├── aggregate_job.py # 5-minute aggregation job
│ └── data_quality.py # Data validation rules
│
├── sql/
│ └── analytics.sql # Table schemas & queries
│
├── dashboard/
│ └── app.py # Streamlit dashboard
│
├── venv/ # Python virtual environment
├── requirements.txt
└── README.md

yaml
Copy code

---

## ⚙️ Setup & Execution (Step-by-Step)

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/your-username/iot-health-data-engineering.git
cd iot-health-data-engineering
2️⃣ Create & Activate Virtual Environment
bash
Copy code
python -m venv venv
Windows

bash
Copy code
venv\Scripts\activate
Mac / Linux

bash
Copy code
source venv/bin/activate
3️⃣ Install Dependencies
bash
Copy code
pip install -r requirements.txt
4️⃣ Configure MySQL Database
sql
Copy code
CREATE DATABASE iot_health;
USE iot_health;
Run the schema and analytics scripts:

bash
Copy code
sql/analytics.sql
🚀 Running the System
5️⃣ Start Ingestion API
bash
Copy code
uvicorn ingestion.api:app --reload
API available at:

cpp
Copy code
http://127.0.0.1:8000
6️⃣ Start Real-Time Data Generator
bash
Copy code
python data/realtime_generator.py
Simulates wearable devices sending telemetry every few seconds.

7️⃣ Start Streaming Processor
bash
Copy code
python spark/stream_processor.py
Validates incoming telemetry and stores raw data.

8️⃣ Run Aggregation Job
bash
Copy code
python spark/aggregate_job.py
Generates 5-minute rolling analytics.

9️⃣ Launch Analytics Dashboard
bash
Copy code
streamlit run dashboard/app.py
Dashboard available at:

arduino
Copy code
http://localhost:8501
📊 Dashboard Capabilities
Toggle between Live (Raw) and Aggregated (5-Min) views

Soldier-wise and time-range filtering

Heart rate trend analysis

Body temperature distribution

Live GPS position tracking

Operational KPIs