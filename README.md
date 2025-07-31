# ThreatHunting
hreat Hunting - Proactive threat detection framework leveraging advanced threat intelligence, IOCs, and MITRE ATT&amp;CK methodologies

By Ramyar Daneshgar 

---

### **Introduction: Proactive vs. Reactive Security**

The distinction between **threat hunting** and **incident response (IR)** is in the methodology and approach to cybersecurity:

- **Incident Response (IR):**
  - **Reactive** process triggered by alerts or notifications from security tools like **SIEM** or **EDR**.
  - Begins with **triaging**, analyzing alerts to verify malicious activity.
  - Focuses on mitigating damage and remediating incidents.

- **Threat Hunting:**
  - **Proactive** process guided by **threat intelligence (TI)** and a deliberate search for undetected adversarial activities.
  - Aims to uncover **indicators of compromise (IOCs)** and **tactics, techniques, and procedures (TTPs)** of threat actors before incidents occur.

#### Synergy Between IR and Threat Hunting
While both processes aim to protect the organization, threat hunting identifies threats missed by automated tools, feeding findings into IR workflows. Conversely, insights from IR inform future threat hunts, creating a feedback loop that continuously improves threat detection.

---

### **Core Concepts of Threat Hunting**

1. **Threat Intelligence as a Foundation:**
   - High-quality **threat intelligence** provides direction and context for hunts, including:
     - **IOCs:** Concrete artifacts of adversary activity, such as malicious IPs, file hashes, or domain names.
     - **Threat Intelligence Feeds:** Platforms like **MISP**, **Recorded Future**, and **ReliaQuest** deliver actionable intelligence.

2. **Detection Gaps:**
   - Advanced **persistent threats (APTs)** often bypass standard detection mechanisms.
   - Threat hunting identifies and addresses these gaps, closing vulnerabilities in the organization's security framework.

3. **Improving Security Posture:**
   - By identifying undetected threats, threat hunters ensure that future adversarial activities are detected earlier and mitigated faster.

---

### **The Threat Hunting Mindset**

Successful threat hunting requires a structured approach and a clear understanding of the organization's environment and adversary approaches:

1. **Starting with Leads:**
   - Begin with reliable leads, such as:
     - Known malware characteristics from repositories like **theZoo**.
     - Historical **IOCs** from previous incidents.
   - These leads guide the hunt, reducing noise and focusing efforts on high-value targets.

2. **Leveraging Unique Threat Intelligence:**
   - Organizations can develop proprietary intelligence, such as:
     - **Custom IOCs** derived from internal intrusion data.
     - Adversary TTPs specific to their industry.

3. **Environmental Awareness:**
   - Distinguishing normal system behavior from malicious activity is essential to identifying **attack residues**.

---

### **The Threat Hunting Process**

Threat hunting follows a structured methodology that addresses **what to hunt for** and **how to hunt effectively**.

#### **What to Hunt For**
1. **Known Malware:**
   - Identify malware commonly used by adversaries targeting your organization.
   - Example: Analyze malware from repositories like **theZoo** or reports from **Trend Micro’s Threat Encyclopedia**.

2. **Attack Residues:**
   - Look for traces of adversarial activity, such as unusual file modifications or registry changes.
   - Challenge: Attack residues often blend with environmental noise, requiring in-depth knowledge of the system to detect anomalies.

3. **Vulnerable Assets:**
   - Scan for **zero-day vulnerabilities** or unpatched systems.
   - Example: Monitor for exploitation of **CVE** vulnerabilities and ensure assets are updated.

#### **How to Hunt**
1. **Attack Signatures and IOCs:**
   - Characterize threats with specific, actionable identifiers, such as:
     - File hashes
     - Malicious URLs
     - Indicators of Attack (IOAs)

2. **Patterns of Activity:**
   - Use frameworks like **MITRE ATT&CK** to identify adversary TTPs and map their behavior.

3. **Logical Queries:**
   - Formulate queries targeting specific identifiers (e.g., application versions, IP ranges) to filter data and pinpoint vulnerabilities.

---

### **Practical Application: MITRE ATT&CK Navigator**

The **MITRE ATT&CK Navigator** is an essential tool for visualizing adversary techniques and prioritizing defenses. Here’s how I used it:

#### **Step-by-Step Analysis**
1. **Mapping Threats:**
   - Mapped **WannaCry**, **Stuxnet**, and **Conficker** within the **Enterprise ATT&CK Matrix**, assigning scores based on relevance:
     - WannaCry: Score = 1
     - Stuxnet: Score = 2
     - Conficker: Score = 4

2. **Layer Aggregation:**
   - Combined layers to identify overlapping techniques across threats. For instance:
     - Common technique: **Exploitation of Remote Services**
     - Shared technique (WannaCry & Conficker): **Inhibit System Recovery**

3. **Visualizing Impact:**
   - Used color coding to highlight shared TTPs, with deeper colors indicating higher relevance or frequency.



---

### **Threat Hunting Goals**

The primary goals of threat hunting are as follows:

1. **Minimizing Dwell Time:**
   - The longer an adversary remains undetected, the greater the potential damage. By identifying threats early, threat hunting reduces the attacker’s ability to persist.

2. **Discovering Pre-existing Threats:**
   - Threat hunting uncovers activities that have bypassed detection mechanisms, triggering immediate **incident response** actions.

3. **Developing Detection Mechanisms:**
   - Findings from hunts are translated into detection rules, such as **YARA** signatures or **SIEM** alerts, ensuring similar threats are detected automatically in the future.

4. **Proactive Defense:**
   - By continuously hunting for threats, organizations stay ahead of adversaries, addressing vulnerabilities before they are exploited.
