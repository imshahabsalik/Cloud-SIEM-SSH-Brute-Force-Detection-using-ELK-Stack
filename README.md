# Cloud SIEM Lab: SSH Brute Force Detection using ELK Stack

## 📌 Overview

This project demonstrates a cloud-based Security Information and Event Management (SIEM) lab built using the ELK Stack (Elasticsearch, Kibana) and Winlogbeat.

The lab simulates SSH authentication attacks and implements detection logic to identify brute-force login attempts.

---

## 🧱 Architecture

Kali Linux (Attacker) → Windows (SSH Server) → Winlogbeat → Elasticsearch → Kibana

---

## ⚙️ Technologies Used

* ELK Stack (Elasticsearch, Kibana)
* Winlogbeat
* OpenSSH Server (Windows)
* Kali Linux (client simulation)

---

## 🔥 Attack Simulation

A controlled simulation of SSH login failures was performed by generating multiple incorrect login attempts from a remote system.

This produced Windows Security Event Logs:

* Event ID **4625** → Failed Logon

---

## 🔍 Detection Logic

Brute-force attacks were detected using:

* Event Code: `4625`
* Threshold: Multiple failed logins within a short time window
* SSH-specific filtering:

  ```
  event.code:4625 and (process.name:sshd or winlog.event_data.LogonProcessName:ssh)
  ```

---

## 📊 Dashboard Features

* Failed logins over time
* Top targeted usernames
* SSH-specific login failures
* Log table with detailed event data

---

## 🚨 Detection Rule

Alert triggers when:

* ≥ 10 failed login attempts
* Within 1 minute


---

## 🧠 Key Learnings

* Built a full SIEM pipeline from scratch
* Simulated credential attack patterns
* Developed detection rules for brute-force attacks
* Visualized security events using Kibana dashboards

---

## 🚀 Future Improvements

* Detect password spraying attacks
* Add geo-location based anomaly detection
* Integrate alert notifications (email/Slack)

---

## 📬 Author

Your Name
