# 🚗 Dynamic Pricing for Urban Parking Lots

**Summer Analytics 2025 – Capstone Project Submission**

This project implements a dynamic, real-time pricing engine for 14 urban parking lots using real-world features such as traffic, occupancy, special events, and competition.

---

## 🔍 Project Overview

Static parking prices cause either overuse or underutilization of spaces. This project simulates a smart, demand-aware pricing model using real-time data ingestion and machine learning principles.

We implemented 3 pricing models:
- **Model 1:** Baseline Linear Pricing
- **Model 2:** Demand-Based Pricing (using occupancy, queue, traffic, etc.)
- **Model 3:** Competitive Pricing with GPS-based logic

---

## 🧰 Tech Stack Used

- Python
- Pandas, NumPy
- [Pathway](https://pathway.com) – Real-time data processing
- Bokeh – Interactive visualizations
- Google Colab – Execution environment

---

## 🧱 Architecture Diagram
Real-time ingestion via Pathway replicates incoming parking log streams.

Preprocessing includes timestamp merging, categorical mapping (vehicle type, traffic), and missing value handling.

Data is fed into 3 models:

Model 1: Linear increase with occupancy

Model 2: Weighted demand formula

Model 3: Considers nearby lot prices using GPS coordinates

Final prices are output with smooth transitions and visualized using Bokeh.


```mermaid
graph TD
    A[Raw CSV Dataset] --> B[Data Preprocessing]
    B --> C{Preprocessing Steps}
    C --> D[Occupancy, Traffic, Queue, Event, Vehicle]
    D --> E[Model 1: Linear]
    D --> F[Model 2: Demand-Based]
    F --> G[Model 3: Competitive GPS]
    E --> H[Pricing Output]
    F --> H
    G --> H
    H --> I[Real-Time Visualization (Bokeh)]
