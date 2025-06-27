**Self-Healing Infrastructure with Prometheus, Alertmanager & Ansible**
Project Overview
This project demonstrates a self-healing infrastructure system that automatically detects failures in services using Prometheus monitoring and Alertmanager alerts, and then triggers automated recovery actions using Ansible playbooks. The system continuously monitors target services, sends alerts on failures, and runs remediation scripts to maintain service availability.

**Architecture**
Prometheus: Monitors metrics from services and nodes.

Alertmanager: Receives alerts from Prometheus and forwards them.

Alertmanager Webhook (Flask app): Receives Alertmanager alerts and triggers Ansible playbooks.

Ansible: Executes recovery tasks to fix failed services automatically.

Tools Used
Prometheus

Alertmanager

Flask (for webhook server)

Ansible

Python3

Amazon Linux 2 EC2

Setup Instructions
Clone the repository:

bash
Copy
Edit
git clone https://github.com/poojithareddy1620/self-healing-infra-prometheus-ansible.git
cd self-healing-infra-prometheus-ansible
Install Python dependencies for webhook server:

bash
Copy
Edit
pip3 install -r alertmanager-webhook/requirements.txt
Start the Flask webhook server:

bash
Copy
Edit
cd alertmanager-webhook
python3 webhook_server.py
Configure and start Prometheus and Alertmanager services:
Prometheus and Alertmanager configs are in the prometheus and alertmanager folders respectively.
Use systemctl or run binaries manually.

Run Ansible playbook to recover failed services when webhook triggers it.

How to Test
Simulate service failure to trigger Prometheus alerts.

Confirm Alertmanager sends alert to webhook.

Verify Ansible playbook executes and recovers the service.

Folder Structure
app.py — Flask app for exposing metrics (example service)

prometheus/ — Prometheus configuration files

alertmanager/ — Alertmanager configuration and binaries

alertmanager-webhook/ — Flask webhook server and related files

ansible/ — Ansible playbooks for self-healing automation
