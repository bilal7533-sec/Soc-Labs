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
```bash
openssl s_client -connect www.example.com:443 -showcerts </dev/null 2>/dev/null | openssl x509 -outform PEM > example_cert.pem
```

### Step 2: Analyze Certificate Details
```bash
openssl x509 -in example_cert.pem -text -noout
```
```bash
md id="kf1a2b"
```


## 🔍 Key Findings
Certificate Information
Certificate Type: X.509 v3
Issuer: Cloudflare TLS Issuing ECC CA 1
Subject: example.com

##Cryptographic Details
Public Key Algorithm: ECDSA (256-bit)
Signature Algorithm: SHA256 with ECDSA
Curve: P-256 (Elliptic Curve Cryptography)

##Security Observations
Uses modern elliptic curve cryptography (strong security standard)
Issued by a trusted Certificate Authority (Cloudflare)
Subject Alternative Names (SAN) support wildcard domains (*.example.com)
Strong key usage restrictions applied for TLS authentication

# 🧠 What I Learned
-How HTTPS encryption works using TLS certificates
-How Certificate Authorities establish trust in PKI
-How to extract and analyze SSL certificates using OpenSSL
-How cryptographic algorithms are used in real-world web security

# 📊 Security Insight (SOC Perspective)

This lab demonstrates how SOC analysts and security engineers inspect SSL certificates to:

-Detect misconfigured TLS setups
-Identify weak cryptographic algorithms
-Validate certificate trust chains
-Monitor secure communication between clients and servers
