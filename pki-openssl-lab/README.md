# PKI Certificate Extraction & Analysis using OpenSSL

## 📌 Project Overview
This project demonstrates how to extract, analyze, and inspect SSL/TLS certificates from a live HTTPS website using OpenSSL on Linux (Kali).

The objective is to understand Public Key Infrastructure (PKI), certificate chain validation, and TLS security structure.

---

## 🛠️ Tools Used
- OpenSSL
- Kali Linux
- Terminal (Bash)

---

## 🌐 Target
www.example.com (HTTPS port 443)

---

## ⚙️ Methodology

### 1. Extract SSL Certificate
Used OpenSSL to connect to a secure server and extract its certificate:

```bash
openssl s_client -connect www.example.com:443 -showcerts </dev/null 2>/dev/null | openssl x509 -outform PEM > example_cert.pem