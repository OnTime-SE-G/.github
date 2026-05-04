# Real-Time Public Transport Tracking System

We are an engineering team developing a **Real-Time Public Transport Tracking and ETA Prediction System** for Sri Lanka’s expressway bus network. The system is designed to improve visibility, reliability, and decision-making in public transportation through real-time data processing and predictive analytics.

---

## Project Overview

This platform delivers live bus tracking, estimated arrival times, and operational insights for multiple stakeholders including commuters, drivers, and transport schedulers.

The current implementation focuses on the **Moratuwa–Kadawatha expressway corridor**, serving as a model for scalable deployment across wider transport networks.

---

## Core Features

### Commuter Application

* Real-time bus location tracking on an interactive map
* Accurate ETA predictions using hybrid modeling techniques
* Bus occupancy visibility to assist boarding decisions
* Route and stop search functionality

### Driver Application

* Minimal-interaction mobile interface optimized for safety
* Status updates (departure, arrival, completion)
* Incident reporting (e.g., breakdowns, traffic conditions)

### Scheduler Dashboard

* Live fleet monitoring across active routes
* Manual dispatch and assignment capabilities
* Real-time anomaly and disruption alerts

---

## System Architecture

The system is built using a distributed, event-driven microservices architecture:

* **Edge Layer (G1)**
  Embedded devices (ESP32 with GPS) stream real-time vehicle data via MQTT

* **Intelligence Layer (G2)**
  Stream processing using Apache Kafka and Apache Flink
  ETA prediction using machine learning and deterministic models

* **Application Layer (G3)**
  Web and mobile applications built with Next.js and Flutter
  Real-time updates delivered via WebSocket connections

* **Platform Layer (G4)**
  Infrastructure managed with Kubernetes
  API Gateway (Kong) and Identity Management (Keycloak)
  Monitoring via Prometheus and Grafana

---

## Real-Time Data Pipeline

1. GPS data is collected from edge devices at a 1 Hz frequency
2. Data is transmitted via MQTT and ingested into Kafka
3. Stream processing pipelines compute ETAs and detect anomalies
4. Processed data is delivered to client applications via WebSockets
5. User interfaces update dynamically with minimal latency

Target end-to-end latency: under 2 seconds 

---

## Intelligence and Analytics

* **Dual-Model ETA Prediction**
  Urban traffic-aware machine learning model
  Expressway model based on speed and distance calculations 

* **Geo-Fencing**
  Automatic detection of highway entry and exit conditions

* **Anomaly Detection**
  Identification of disruptions such as potential breakdowns

---

## Technology Stack

* **Streaming and Messaging:** Apache Kafka, MQTT
* **Processing:** Apache Flink
* **Frontend:** Next.js, Flutter
* **Backend:** Node.js, Python (gRPC services)
* **Databases:** PostgreSQL with PostGIS, InfluxDB
* **Infrastructure:** Kubernetes, Istio

---

## Security and Reliability

* OAuth 2.0 with PKCE for authentication (Keycloak)
* Role-based access control for different user types
* Secure service-to-service communication (mTLS)
* Target system availability of 99.5% 

---

## Performance Targets

* ETA computation latency below 500 ms
* End-to-end GPS update latency below 2 seconds
* Support for 10,000+ concurrent users
* Fault-tolerant streaming with high data durability

---

## Team Structure

* **G1 – Edge Systems**: Embedded systems and data acquisition
* **G2 – Intelligence**: Stream processing and predictive models
* **G3 – Applications**: Web and mobile interfaces
* **G4 – Platform**: Infrastructure, security, and DevOps

---

## Vision

To develop a reliable and scalable public transport intelligence platform that enhances commuter experience and supports data-driven transport operations.

---

## Status

Active development as part of an academic project (2026/2027)

---

## License

Internal and academic use only
