---

# Network Traffic Analysis – Stage 2

## HTTP – TCP GET
**Definition:** HTTP is protocol for web communication. It runs on TCP and uses GET request to fetch data.  

**Analysis:**  
In Wireshark I saw TCP handshake first then HTTP GET request going to server. Data was in plain text.  

| **Step** | **Observation** |
|---------|----------------|
| TCP Handshake | SYN → SYN‑ACK → ACK |
| HTTP GET | Client asked for page |
| Response | Server sent data in clear text |

---

## HTTPS – TLS Handshake
**Definition:** HTTPS is secure HTTP. It uses TLS to encrypt communication.  

**Analysis:**  
In Wireshark I saw Client Hello and Server Hello messages. After that encryption started so content was not readable.  

| **Step** | **Observation** |
|---------|----------------|
| Client Hello | Browser sent supported ciphers |
| Server Hello | Server selected cipher and sent certificate |
| Key Exchange | Secure session created |
| Encrypted Data | Traffic unreadable in capture |

---

## DNS
**Definition:** DNS resolves domain name to IP address.  

**Analysis:**  
I checked DNS queries in Wireshark. Client asked for google.com and server replied with IP.  

| **Step** | **Observation** |
|---------|----------------|
| Query | Client asked DNS server |
| Response | Server gave IP address |

---

## Follow TCP Stream
**Definition:** Wireshark can follow TCP stream to see communication between client and server.  

**Analysis:**  
I followed TCP stream and saw request and response. In HTTP it was readable but in HTTPS it was encrypted.  

| **Stream** | **Observation** |
|---------|----------------|
| HTTP | Request and response visible |
| HTTPS | Encrypted and not readable |

---

## Follow TLS Stream
**Definition:** Wireshark can follow TLS stream but data is encrypted.  

**Analysis:**  
I followed TLS stream and saw only encrypted packets. Without server keys it cannot be decrypted.  

| **Stream** | **Observation** |
|---------|----------------|
| Client Hello | Visible |
| Server Hello | Visible |
| Application Data | Encrypted and unreadable |

---

# Final Comparison Table – Protocol Analysis

| **Protocol** | **Definition** | **Observation in Wireshark** |
|--------------|----------------|------------------------------|
| HTTP | Web protocol using TCP | GET request visible and data in plain text |
| HTTPS | Secure HTTP with TLS | Client Hello and Server Hello visible and rest encrypted |
| DNS | Resolves domain to IP | Query and response packets visible |
| TCP Stream | Shows client server communication | HTTP readable and HTTPS encrypted |
| TLS Stream | Shows TLS handshake | Only hello messages visible and data encrypted |

---
