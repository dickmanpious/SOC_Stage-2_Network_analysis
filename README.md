# Wireshark Network Traffic Analysis

## Project Overview  
This project demonstrates how to capture and analyze packets using Wireshark and explains what each protocol shows in real traffic.  

---

## Objectives  
| **Objective** | **Meaning** |
|----------------|----------------|
| Capture Packets | Collect live traffic from network |
| TCP Handshake | Study how client and server connect |
| HTTPS Traffic | Observe TLS handshake and encryption |
| DNS Queries | See how domains resolve to IP |
| Stream Analysis | Follow TCP and TLS streams |

---

## Tool Used  
| **Tool** | **Purpose** |
|-------------|----------------|
| Wireshark | Packet capture and protocol analysis |

---

## Analysis Performed  

### 1. TCP Analysis  
**Smart Note:** TCP is like a polite handshake before talking. Client says hello (SYN), server replies (SYN‑ACK), and client confirms (ACK).  
| **Step** | **Observation** |
|---------|----------------|
| SYN | Client starts connection |
| SYN‑ACK | Server replies |
| ACK | Client confirms |
| Port | 443 used for HTTPS |

---

### 2. TLS Traffic  
**Smart Note:** TLS is like locking the conversation with a secret key. Only client and server can read it.  
| **Step** | **Observation** |
|---------|----------------|
| Client Hello | Browser sends supported ciphers |
| Server Hello | Server chooses cipher and sends certificate |
| Key Exchange | Secure session created |
| Encrypted Data | Content hidden from capture |

---

### 3. DNS Analysis  
**Smart Note:** DNS is like a phonebook. You ask for a name and it gives you the number.  
| **Step** | **Observation** |
|---------|----------------|
| Query | Client asked for google.com |
| Response | Server gave IP address |

---

### 4. TCP Stream Analysis  
**Smart Note:** Following TCP stream is like reading the full chat between client and server.  
| **Stream** | **Observation** |
|---------|----------------|
| HTTP | Request and response visible |
| HTTPS | Encrypted and unreadable |

---

### 5. TLS Stream Analysis  
**Smart Note:** TLS stream shows the handshake but hides the actual talk.  
| **Stream** | **Observation** |
|---------|----------------|
| Client Hello | Visible |
| Server Hello | Visible |
| Application Data | Encrypted and hidden |

---

## Conclusion  
The analysis shows how TCP handshake sets up connection, DNS resolves domains, HTTP sends plain text, and HTTPS secures traffic with TLS. SOC analysts use Wireshark to monitor these flows and confirm if communication is safe.  

---

## Screenshots  

---

This format uses **different words, smart analogies, and tables** so your README looks professional and easy to understand.  

Do you want me to now extend this into **Stage 3 – Security Basics (malware, phishing, brute force, MITRE)** in the same smart table style so your repo feels complete?
