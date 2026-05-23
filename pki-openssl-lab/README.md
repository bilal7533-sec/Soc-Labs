# PKI Certificate Extraction & Analysis using OpenSSL

## 📌 Project Overview
This project demonstrates real-world SSL/TLS certificate extraction and analysis using OpenSSL on Kali Linux.

The objective is to understand how HTTPS security works under Public Key Infrastructure (PKI), including certificate validation, issuer trust chains, and cryptographic signatures.

---

## 🛠️ Tools Used
- OpenSSL
- Kali Linux
- Linux Terminal (Bash)

---

## 🌐 Target System
- Domain: www.example.com
- Port: 443 (HTTPS)

---

## ⚙️ Methodology

### Step 1: Extract SSL Certificate
bash
openssl s_client -connect www.example.com:443 -showcerts </dev/null 2>/dev/null | openssl x509 -outform PEM > example_cert.pem

🔍 Key Findings
Certificate Type: X.509 v3
Issuer: Cloudflare TLS Issuing ECC CA 1
Subject: example.com
Public Key Algorithm: ECDSA (256-bit)
Signature Algorithm: SHA256 with ECDSA
Security Observations:
Uses modern elliptic curve cryptography (P-256)
Certificate is issued by trusted Certificate Authority (Cloudflare)
Subject Alternative Names (SAN) support wildcard domains (*.example.com)
Strong key usage restrictions applied for TLS authentication
🧠 What I Learned
How HTTPS encryption is implemented using TLS certificates
How Certificate Authorities establish trust
How to extract and analyze certificates using OpenSSL
Basics of Public Key Infrastructure (PKI)
📊 Security Insight

This lab demonstrates how attackers and security engineers can inspect SSL certificates to detect misconfigurations, weak cryptography, or trust chain issues in real-world systems.
