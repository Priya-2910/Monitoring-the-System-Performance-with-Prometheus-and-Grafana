# 📊 Monitoring System Performance with Prometheus & Grafana

## 🚀 Overview

This project demonstrates how to monitor system performance on **macOS (Apple M4 Chip)** using **Prometheus** and **Grafana**. It enables real-time collection and visualization of system metrics such as CPU usage, memory consumption, and disk activity.

---

## 🖥️ System Configuration

* **Operating System:** macOS (Apple Silicon - M4 Chip)
* **Architecture:** ARM64
* **Package Manager:** Homebrew

---

## 🧰 Tools & Technologies

* **Prometheus** – Monitoring and alerting toolkit
* **Node Exporter** – System metrics collector
* **Grafana** – Data visualization and dashboarding

---

## ⚙️ Project Architecture

```
Node Exporter → Prometheus → Grafana Dashboard
```

* Node Exporter collects system metrics
* Prometheus scrapes and stores metrics
* Grafana visualizes data using dashboards

---

## 📡 Prometheus Configuration

Prometheus is configured to scrape metrics from Node Exporter at regular intervals.

### Sample `prometheus.yml`:

```yaml
global:
  scrape_interval: 15s

scrape_configs:
  - job_name: "node_exporter"
    static_configs:
      - targets: ["localhost:9100"]
```

---

## 📈 Node Exporter Setup

Node Exporter runs as a service and exposes system metrics at:

```
http://localhost:9100/metrics
```

### Metrics collected:

* CPU usage
* Memory usage
* Disk I/O
* System load

---

## 📊 Grafana Dashboard

Grafana is used to visualize the metrics collected by Prometheus.

### Steps:

1. Open Grafana (http://localhost:3000)
2. Go to **Connections → Data Sources**
3. Add **Prometheus**
4. Set URL:

   ```
   http://localhost:9090
   ```
5. Import dashboard:

   * Use **Node Exporter Full Dashboard**

---

## 🔄 Workflow

```
System Metrics → Node Exporter → Prometheus → Grafana → User Dashboard
```

---

## ▶️ Running the Project

### Start Prometheus

```bash
/opt/homebrew/bin/prometheus --config.file=prometheus.yml
```

### Start Node Exporter

```bash
./node_exporter
```

---

## ⚠️ Troubleshooting

### ❌ Issue: "No Data" in Grafana

✔ Fix:

* Go to **Dashboard Settings → Variables**
* Ensure `DS_PROMETHEUS` is set correctly (e.g., `prometheus-1`)
* Save and refresh dashboard

---

## 📌 Features

* Real-time system monitoring
* Lightweight setup
* Visual dashboards
* Easy integration with macOS

---

## 📈 Results

* Live CPU, memory, and disk monitoring
* Clear graphical representation of system performance
* Efficient system analysis

---

## 🔮 Future Enhancements

* Add alerting system (email/Slack)
* Monitor network performance
* Deploy using Docker
* Add multiple node monitoring

---

## 👩‍💻 Author

**Lakshmi Priya**

---

## 📄 License

This project is for educational purposes.

---

## 🙌 Acknowledgement

Inspired by modern DevOps monitoring tools and system performance analysis techniques.

---
