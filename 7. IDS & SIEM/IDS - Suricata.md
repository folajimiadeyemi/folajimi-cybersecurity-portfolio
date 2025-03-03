# Intrusion Detection Systems (IDS) - Suricata

Suricata is an open-source Intrusion Detection System (IDS), Intrusion Prevention System (IPS), and Network Security Monitoring (NSM) tool. It helps organizations detect and respond to malicious activity by analyzing network traffic and generating alerts.

## Suricata’s Core Functions

1. **Intrusion Detection System (IDS)** – Monitors network traffic and alerts on suspicious activity.  
2. **Intrusion Prevention System (IPS)** – Detects and blocks malicious traffic with additional configuration.  
3. **Network Security Monitoring (NSM)** – Captures and logs network traffic for analysis, aiding in forensics and incident response.  

### Signature-Based Detection

Suricata uses **signatures** to detect threats. Each signature consists of:  

- **Action** – Defines what happens when a rule matches (e.g., alert, drop, reject).  
- **Header** – Specifies traffic attributes like source/destination IPs and ports.  
- **Rule Options** – Provides additional customization for fine-tuned detection.  

---

## Hands-on with Suricata

### Scenario

As a security analyst, your task is to monitor and analyze network traffic. You will:  

1. **Create and test custom rules**  
2. **Analyze captured network traffic using Suricata**  
3. **Examine logs to identify alerts and security events**  

### Key Files

| File            | Description  |
|----------------|-------------|
| `sample.pcap`  | Packet capture file containing network traffic for analysis. |
| `custom.rules` | Custom rule file to define detection signatures. |
| `fast.log`     | A simple log containing triggered alerts (deprecated format). |
| `eve.json`     | A detailed log file storing events in JSON format. |

---

## Step-by-Step Guide

### 1. Creating a Custom Suricata Rule  

#### Example Rule  

```plaintext
alert http $HOME_NET any -> $EXTERNAL_NET any (msg:"GET on wire"; flow:established,to_server; content:"GET"; http_method; sid:12345; rev:3;)
```  

#### Breakdown  

- **Action (`alert`)** – Triggers an alert when conditions match.  
- **Protocol (`http`)** – Applies to HTTP traffic.  
- **Direction (`->`)** – Traffic flows from `$HOME_NET` to `$EXTERNAL_NET`.  
- **Rule Options**:  
  - `msg:"GET on wire"` – Custom alert message.  
  - `flow:established, to_server` – Matches only established client-to-server traffic.  
  - `content:"GET"; http_method` – Looks for HTTP GET requests.  
  - `sid:12345` – Unique rule identifier.  
  - `rev:3` – Rule revision number.  

---

### 2. Running Suricata with Custom Rules  

#### Steps  

1. **List log directory contents:**  
   ```bash
   ls -l /var/log/suricata
   ```
   Initially, no logs should exist.  

2. **Run Suricata against the sample traffic:**  
   ```bash
   sudo suricata -r sample.pcap -S custom.rules -k none
   ```
   - `-r sample.pcap` – Reads packets from the capture file.  
   - `-S custom.rules` – Uses custom detection rules.  
   - `-k none` – Disables checksum validation.  

3. **Check logs after running Suricata:**  
   ```bash
   ls -l /var/log/suricata
   ```  

4. **View alerts in `fast.log`:**  
   ```bash
   cat /var/log/suricata/fast.log
   ```
   - Each line represents an alert.  
   - Provides a quick overview of matched rules.  

---

### 3. Analyzing `eve.json` Logs  

#### Viewing JSON Logs  

1. **Display full log output:**  
   ```bash
   cat /var/log/suricata/eve.json
   ```  

2. **Format JSON output for readability:**  
   ```bash
   jq . /var/log/suricata/eve.json | less
   ```  

3. **Extract key event details:**  
   ```bash
   jq -c "[.timestamp, .flow_id, .alert.signature, .proto, .dest_ip]" /var/log/suricata/eve.json
   ```  

#### Insights from `eve.json`  

- **Alert severity for the first event** – `3`  
- **Destination IP of the last event** – `142.250.1.102`  
- **First alert signature** – `"GET on WIRE"`  

---

## Key Takeaways  

- **Suricata can detect suspicious network activity using signature-based rules.**  
- **Custom rules help tailor IDS behavior to specific threats.**  
- **Logs (`fast.log` and `eve.json`) provide critical insights into detected events.**  
- **JSON-formatted logs offer structured data for threat hunting and analysis.**  
