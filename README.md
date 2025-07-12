# 🔐 Log Analyzer Bot

A Linux-based automated security tool to monitor and block suspicious SSH login attempts using log parsing, firewall integration, and optional GUI support.

## 📌 Project Overview

The **Log Analyzer Bot** is a shell script that analyzes `/var/log/auth.log` to detect failed SSH login attempts. It identifies patterns like repeated failures from specific IP addresses and automatically blocks malicious IPs using **UFW (Uncomplicated Firewall)**. The bot runs periodically using **cron jobs** and can optionally send alerts or generate reports.

## 🚀 Features

- 🔍 Monitors failed SSH login attempts from `/var/log/auth.log`
- 🛡️ Automatically blocks IPs exceeding a failed login threshold
- 🕒 Scheduled execution using `cron` (24/7 monitoring)
- 📁 Logs malicious IPs and blocked events
- 📧 Optional email alerts and notifications
- 💻 Optional GUI built using `Tkinter` for user-friendly interaction

## 📂 Folder Structure

```
📁 log-analyzer-bot/
├── log_analyzer.sh       # Main bash script for analysis and blocking
├── gui.py                # Optional Tkinter-based GUI interface
├── blocked_ips.log       # Log of blocked IPs
├── README.md             # This file
└── requirements.txt      # (Optional) Python GUI requirements
```

## ⚙️ Requirements

### CLI Version:
- Linux (Debian-based, e.g. Kali)
- `bash`
- `grep`, `awk`
- `ufw` (Uncomplicated Firewall)
- `cron`
- `mail` or `logger` (optional for alerts)

### GUI Version :
https://darling-pothos-55e480.netlify.app/
- Python 3.x
- `Tkinter`
- `collections`, `re`, `os`
- (Optional) `csv` for report export

## 🛠️ Setup & Usage

### 1. Enable UFW

```bash
sudo apt install ufw
sudo ufw enable
```

### 2. Create and Run the Script

```bash
chmod +x log_analyzer.sh
sudo ./log_analyzer.sh
```

### 3. Schedule via Cron

```bash
sudo crontab -e
# Add this line to run every 5 minutes
*/5 * * * * /path/to/log_analyzer.sh
```

### 4. Run GUI (Optional)

```bash
python3 gui.py
```

## 🧪 Example Output

```
===== Failed SSH Login Report =====
192.168.1.15 - 6 failed attempts - Blocked
10.0.0.2 - 2 failed attempts - Skipped (Below Threshold)
```

## 📈 Future Enhancements

- Email/SMS alerts on detected intrusions
- HTML/CSV reporting
- SIEM integration
- Real-time dashboards
- AI/ML pattern detection
- Support for other services (FTP, HTTP, SMTP)

## 👨‍💻 Contributors

- **Surya Ajay Kumar** – Developer (Cyber Security, TEKS Academy)
- **Shashidhar** – Mentor / Trainer

## 📜 License

This project is for academic and educational purposes.
