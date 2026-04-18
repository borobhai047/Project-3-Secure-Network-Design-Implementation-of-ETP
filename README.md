# 🔐 Secure Network Design & Implementation  
### Endpoint Technologies PLC (ETP)

---

## 📌 Project Overview  

This project demonstrates the **design, implementation, and validation of a secure enterprise network**, built using CCNA-level configurations and aligned with **ISO/IEC 27001:2022** and the **NIST Cybersecurity Framework**.

The network was developed in a simulated environment using Cisco Packet Tracer and represents a real-world implementation for a mid-sized organisation (**Endpoint Technologies PLC, Dhaka**).

---

## 🎯 Objectives  

- Design a segmented enterprise network using VLAN architecture  
- Enforce strict access control using Extended ACLs  
- Implement a secure **DMZ architecture** for public-facing services  
- Apply **device hardening and secure management practices**  
- Map all technical implementations to:
  - ISO/IEC 27001 Annex A Controls  
  - NIST Cybersecurity Framework  

---

## 🏢 Organisation Context  

| Attribute | Details |
|----------|--------|
| Organisation | Endpoint Technologies PLC |
| Location | Dhaka, Bangladesh |
| Size | 50–100 Employees |
| Business | Software Development, API Solutions, SaaS |
| Security Context | Handles sensitive client data, source code, credentials |

---

## 🌐 Network Architecture  

### VLAN Segmentation  

| VLAN | Department | Network | Gateway |
|------|-----------|--------|---------|
| 10 | IT | 192.168.10.0/24 | 192.168.10.1 |
| 20 | HR | 192.168.20.0/24 | 192.168.20.1 |
| 30 | DEV | 192.168.30.0/24 | 192.168.30.1 |
| 40 | Guest | 192.168.40.0/24 | 192.168.40.1 |
| 50 | DMZ | 192.168.50.0/24 | 192.168.50.1 |

---

## 🧱 Key Security Implementations  

### 🔹 Network Segmentation (VLANs)
- Eliminates lateral movement between departments  
- Maps to **ISO 27001 A.13.1.3**

---

### 🔹 Inter-VLAN Routing (Router-on-a-Stick)
- Controlled communication via router subinterfaces  
- ACL enforcement at gateway level  

---

### 🔹 Access Control Lists (ACLs)
- HR restricted from DEV  
- Guest fully isolated  
- DMZ blocked from initiating internal communication  

---

### 🔹 DMZ Architecture
- Isolated network for:
  - Web Server (Apache)  
  - Database Server (MySQL)  
- Prevents pivoting into internal network  

---

### 🔹 Secure Remote Management
- SSH v2 only (Telnet disabled)  
- RSA 2048-bit encryption  
- Local authentication configured  

---

### 🔹 Port Security
- MAC address locking (sticky)  
- Violation mode: restrict  
- Prevents:
  - MAC flooding  
  - Unauthorized device access  

---

### 🔹 Device Hardening
- Password encryption enabled  
- Secure console access  
- Legal login banner  
- Unused ports shutdown  

---

### 🔹 DHCP Automation
- Centralised DHCP on router  
- IP conflict prevention via exclusions  

---

## 🧪 Testing & Verification  

| Test Case | Expected | Result |
|----------|---------|--------|
| IT → All VLANs | Allow | ✅ PASS |
| HR → DEV | Deny | ✅ PASS |
| Guest → Internal | Deny | ✅ PASS |
| IT → DMZ | Allow | ✅ PASS |
| SSH Access | Secure | ✅ PASS |
| DHCP Allocation | Working | ✅ PASS |

✔ **All 13 test cases passed successfully**  
✔ No unauthorized traffic observed  

---

## 📊 ISO 27001 Control Mapping  

| Control | Annex A | Risk Mitigated |
|--------|--------|---------------|
| VLAN Segmentation | A.13.1.3 | Lateral Movement |
| ACLs | A.9.4 | Unauthorized Access |
| DMZ | A.13.1.3 | Server Exposure |
| SSH | A.10.1 | Weak Credentials |
| Port Security | A.11.2 | MAC Flooding |
| Hardening | A.9.4.2 | Unauthorized Access |

---

## 🧠 NIST Cybersecurity Framework Mapping  

| Function | Category | Implementation |
|----------|---------|---------------|
| Identify | Asset Mgmt | Asset inventory |
| Protect | Access Control | VLAN + ACL |
| Protect | Data Security | SSH Encryption |
| Detect | Monitoring | Port Security |
| Respond | Mitigation | Segmentation |
| Recover | Recovery | BCDR Plan |

---

## ⚠️ Known Limitations  

| Limitation | Description | Recommendation |
|-----------|------------|---------------|
| No Stateful Firewall | Packet Tracer limitation | Deploy Cisco ASA / NGFW |
| No Syslog | No log collection | Implement SIEM |
| Single Router | Single point of failure | Use HSRP |
| No IDS/IPS | No traffic inspection | Deploy Snort / IDS |

---

## 🚀 Key Outcomes  

- Secure segmented enterprise network  
- Risk-based implementation aligned with ISO 27001  
- Real-world application of CCNA networking concepts  
- Integration of **GRC + Technical Security Controls**  

---


## 👤 Author  

**Asfi Ahmed**  
Cybersecurity & Networking Enthusiast  

🔗 GitHub: https://github.com/borobhai047  

---

## ⚠️ Disclaimer  

This project was conducted in a simulated environment for educational purposes only.  
No real enterprise systems were affected.
