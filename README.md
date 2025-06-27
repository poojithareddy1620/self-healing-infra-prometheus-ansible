# self-healing-infra-prometheus-ansible
DevOps project for auto-healing services using Prometheus, Alertmanager, and Ansible
# Self-Healing Infrastructure with Prometheus, Alertmanager & Ansible

## 📌 Introduction
This project demonstrates a self-healing infrastructure setup using Prometheus for monitoring, Alertmanager for alerting, and a webhook with Ansible automation to auto-recover failed services.

## 📄 Abstract
In modern infrastructure, minimizing downtime is critical. This project automatically detects service failures through Prometheus, sends alerts via Alertmanager, and triggers automated Ansible scripts through a custom Flask webhook server to restart failed services — achieving self-healing capability.

## 🧰 Tools & Technologies
- **Prometheus** – Monitoring system to scrape metrics
- **Alertmanager** – Sends alerts based on rules
- **Flask (Python)** – Webhook server to trigger scripts
- **Ansible** – Performs automated recovery actions
- **EC2 (Amazon Linux 2)** – Host environment

## ⚙️ Project Str
.
├── app.py # Sample monitored Flask app
├── prometheus/
│ └── prometheus.yml # Scrape config & alert rules
├── alertmanager/
│ └── alertmanager.yml # Alertmanager config
├── alertmanager-webhook/
│ ├── webhook_server.py # Flask webhook server
│ └── requirements.txt # Python dependencies

## 🚀 How It Works
1. **Prometheus** scrapes metrics from `app.py` on port `8080`.
2. When the app goes down, **alert rule** fires.
3. **Alertmanager** sends a POST request to the **Flask webhook server**.
4. Webhook server runs an **Ansible playbook** to restart the app.
5. App recovers and Prometheus marks it healthy again.

## ✅ To Run
```bash
# Start Flask app
python3 app.py

# Start Alertmanager
./alertmanager --config.file=alertmanager.yml

# Start Webhook
cd alertmanager-webhook
python3 webhook_server.py

# Start Prometheus
./prometheus --config.file=prometheus.yml
📌 Conclusion
This project showcases the power of combining monitoring, alerting, and automation to build a resilient, self-healing infrastructure — reducing the need for manual intervention during failures.
