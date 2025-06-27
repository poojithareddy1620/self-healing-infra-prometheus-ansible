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
