# Harmony Health Threat Investigation
### Threat Intelligence & SOC Analyst Capstone Project
SOC Threat Intelligence Capstone | Phishing &amp; BEC investigation, email header analysis, SPF/DKIM/DMARC, IOC extraction, threat intelligence enrichment and static attachment analysis.


**10Alytics | Cybersecurity Capstone Project | 2026**

**Project by:** Faith Ejele  
**Role:** SOC Analyst  
**Specialisation:** Threat Intelligence | Security Monitoring | Incident Investigation | Malware Detection

---

##  Project Overview

The **Harmony Health Threat Investigation** is a practical cybersecurity capstone project designed to demonstrate Security Operations Centre (SOC) investigation, threat intelligence analysis, security monitoring, and incident response.

The project simulates security incidents affecting **Harmony Health**, a healthcare organisation operating a hybrid IT infrastructure.

The investigation focuses on identifying suspicious activities, analysing security alerts, investigating phishing attempts, detecting unauthorised system modifications, and evaluating potential exploitation attempts.

The project combines **desk-based threat intelligence investigations (Part A)** with **hands-on Wazuh security monitoring and detection exercises (Part B)**.

### Project Highlights

| Metric | Outcome |
|---|---|
| Phishing emails investigated | 4 |
| Wazuh detection scenarios tested | 3 |
| Evidence screenshots documented | 157 |
| Investigation cases assessed | 7 |
| SOC monitoring platform | Wazuh |
| Detection technologies | YARA, FIM, Rootcheck |
| Security framework | MITRE ATT&CK |

---

##  Company Background — Harmony Health

Harmony Health operates a hybrid IT infrastructure supporting clinical and administrative operations.

### Ubuntu-Based Server Infrastructure
- Electronic Health Record (EHR/EMR) systems
- Internal databases containing sensitive patient information
- Backend services supporting healthcare operations

### Windows-Based Endpoints
- Administrative workstations
- Clinical staff systems
- Billing and scheduling operations
- Remote access for IT support

The organisation requires strong security monitoring to protect sensitive information, maintain system integrity, and ensure uninterrupted healthcare services.

---

##  Project Objectives

The primary objective was to demonstrate practical SOC investigation and threat detection capabilities.

Specific objectives included:

1. Investigate suspicious emails and identify phishing indicators.
2. Analyse email headers, attachments, URLs, and authentication results.
3. Perform threat intelligence enrichment using security investigation platforms.
4. Configure and monitor security events using Wazuh.
5. Investigate suspicious file activity using File Integrity Monitoring (FIM).
6. Identify unauthorised system modifications using Rootcheck.
7. Analyse potential exploitation attempts through web server logs.
8. Evaluate YARA integration for malware detection.
9. Map suspicious activities to MITRE ATT&CK techniques.
10. Document findings, assess risks, and recommend incident response actions.

---

##  Tools and Technologies

| Tool | Purpose |
|---|---|
| Wazuh SIEM/XDR | Security monitoring, alert detection, and investigation |
| Ubuntu Linux | Monitored endpoint and server environment |
| Kali Linux | Security testing and investigation |
| YARA | Signature-based malware identification |
| File Integrity Monitoring | Detecting file creation and modification |
| Wazuh Rootcheck | Identifying suspicious system modifications |
| VirusTotal | Threat intelligence enrichment |
| AbuseIPDB | IP reputation investigation |
| MalwareBazaar | Malware intelligence research |
| Wireshark | Network traffic analysis where applicable |
| MITRE ATT&CK | Threat classification and behavioural mapping |
| Apache Web Server | Web security monitoring and log investigation |

---

#  PART A — Threat Intelligence & Phishing Investigation

## Overview

Part A involved a desk-based investigation of four suspicious emails targeting users within a simulated healthcare environment.

The objective was to identify potential phishing and fraud attempts, evaluate indicators of compromise, assess the associated risks, and recommend appropriate response actions.

### Investigation Methodology

**Identification → Evidence Collection → Header Analysis → IOC Enrichment → Risk Assessment → Verdict → Escalation**

###  Case 1: Microsoft Credential Phishing

**Threat Category:** Credential Harvesting  
**Priority:** HIGH  
**Verdict:** Likely phishing attempt

#### Investigation Activities
- Analysed sender information and email headers.
- Reviewed SPF, DKIM, and DMARC authentication results.
- Investigated suspicious account verification requests.
- Identified inconsistencies between sender identity and destination links.
- Evaluated potential credential theft risks.

#### Findings
The email used account suspension warnings and urgency to encourage recipients to disclose their login credentials.

#### Recommended Response
- Block confirmed malicious destinations.
- Review relevant authentication logs.
- Investigate potential account exposure.
- Escalate confirmed credential compromise.

---

###  Case 2: Business Email Compromise (BEC)

**Threat Category:** Financial Fraud  
**Priority:** CRITICAL  
**Verdict:** Likely business email compromise / invoice fraud attempt

#### Investigation Activities
- Examined supplier identity and payment instructions.
- Analysed sender and reply-to inconsistencies.
- Investigated unexpected banking changes.
- Evaluated impersonation and social engineering indicators.
- Assessed potential financial exposure.

#### Findings
The email attempted to redirect a business payment through suspicious supplier payment instructions.

#### Recommended Response
- Verify payment changes through trusted communication channels.
- Contact the finance team.
- Confirm whether any payment occurred.
- Escalate suspected fraud to appropriate stakeholders.

---

###  Case 3: DHL Shipping Phishing

**Threat Category:** Delivery-Themed Phishing  
**Priority:** MEDIUM-HIGH  
**Verdict:** Likely phishing attempt

#### Investigation Activities
- Analysed the sender's identity.
- Reviewed suspicious delivery notifications.
- Investigated payment requests and links.
- Examined attachment characteristics.
- Assessed potential financial and endpoint risks.

#### Findings
The email used a delivery problem and small payment request to encourage recipient interaction.

#### Recommended Response
- Avoid interacting with suspicious links.
- Verify delivery information through official channels.
- Investigate any attachment interaction.
- Escalate potential payment card exposure.

---

###  Case 4: Bank of America Credential Phishing

**Threat Category:** Banking Credential Harvesting  
**Priority:** HIGH  
**Verdict:** Likely phishing attempt

#### Investigation Activities
- Examined email authentication indicators.
- Investigated suspicious banking notifications.
- Analysed sender identity inconsistencies.
- Evaluated social engineering techniques.
- Assessed possible credential exposure.

#### Findings
The email used an account security warning to encourage recipients to visit an imitation banking website.

#### Recommended Response
- Verify account activity using official banking channels.
- Investigate any recipient interaction.
- Escalate suspected credential compromise.
- Block confirmed phishing destinations.

---

## Part A Investigation Summary

| Case | Threat Type | Risk Level | Verdict |
|---|---|---|---|
| 01 | Microsoft Credential Phishing | High | Likely phishing |
| 02 | Business Email Compromise | Critical | Likely financial fraud |
| 03 | DHL Shipping Phishing | Medium-High | Likely phishing |
| 04 | Banking Credential Phishing | High | Likely phishing |

### Key Learning Outcomes

- Email header analysis
- Phishing identification
- Social engineering investigation
- Threat intelligence enrichment
- IOC correlation
- Risk-based prioritisation
- Incident escalation
- Evidence-based security reporting

---

# PART B — Wazuh Threat Detection & Investigation

## Overview

Part B focused on practical security monitoring within an isolated cybersecurity laboratory.

Three detection scenarios were investigated to evaluate how Wazuh identifies suspicious endpoint activity, unauthorised system changes, and potential web exploitation attempts.

### Laboratory Environment

| Component | Technology |
|---|---|
| Security monitoring | Wazuh |
| Monitored endpoint | Ubuntu Linux |
| Security testing machine | Kali Linux |
| File monitoring | Wazuh FIM |
| System integrity monitoring | Wazuh Rootcheck |
| Signature detection | YARA |
| Web server | Apache |
| Investigation interface | Wazuh Dashboard |

---

##  Investigation 1 — Malware Indicator Detection

**Objective:** Investigate suspicious file activity and evaluate malware detection capabilities.

### Activities
- Prepared YARA detection capabilities.
- Configured Wazuh File Integrity Monitoring.
- Monitored file creation and modification events.
- Reviewed security alerts generated by Wazuh.
- Examined file integrity changes.
- Evaluated detection rules and alert correlation.

### Findings

Wazuh successfully generated File Integrity Monitoring alerts for monitored file activity.

YARA installation and integration configuration were documented, but a successful YARA signature match was not demonstrated in the available evidence.

**Outcome:** FIM detection verified; YARA detection requires further validation.

---

##  Investigation 2 — System Integrity Monitoring

**Objective:** Detect unauthorised modifications to system utilities.

### Activities
- Configured Wazuh Rootcheck monitoring.
- Simulated an unauthorised system modification.
- Investigated the resulting security alerts.
- Reviewed alert severity and detection rules.
- Evaluated potential impacts on system integrity.
- Documented recommended remediation actions.

### Findings

Wazuh Rootcheck successfully identified suspicious system modification activity.

The investigation demonstrated the importance of monitoring critical system components for unexpected changes.

**Outcome:** System integrity detection verified.

---

## Investigation 3 — Web Exploitation Attempt Detection

**Objective:** Investigate suspicious HTTP requests associated with Shellshock exploitation patterns.

### Activities
- Configured Apache web server monitoring.
- Generated a controlled security test.
- Investigated suspicious web server requests.
- Reviewed Wazuh alerts and associated logs.
- Analysed the detection severity.
- Evaluated evidence of attempted exploitation.

### Findings

Wazuh detected a Shellshock-related attack pattern and generated a high-severity security alert.

However, the available evidence did not demonstrate successful exploitation or unauthorised command execution.

**Outcome:** Exploitation attempt pattern detected; successful compromise not confirmed.

---

##  Part B Detection Summary

| Investigation | Detection Method | Outcome |
|---|---|---|
| Malware Indicator Investigation | FIM / YARA | FIM verified; YARA match not demonstrated |
| System Integrity Monitoring | Rootcheck | Suspicious modification detected |
| Web Exploitation Investigation | Wazuh / Apache Logs | Shellshock pattern detected; exploitation unconfirmed |

---

#  MITRE ATT&CK Framework

The investigation used MITRE ATT&CK to classify relevant adversary behaviours and understand how suspicious activities relate to recognised attack techniques.

| Technique | Description | Investigation |
|---|---|---|
| T1566.001 | Spearphishing Attachment | Email attachment analysis |
| T1566.002 | Spearphishing Link | Credential phishing |
| T1204 | User Execution | Potential user interaction, not confirmed |
| T1190 | Exploit Public-Facing Application | Shellshock-related detection |
| T1105 | Ingress Tool Transfer | Inferred from laboratory file transfer activity |

**Note:** MITRE mappings describe relevant or potential adversary techniques and do not necessarily indicate confirmed execution.

---

#  Incident Response & Escalation

The investigation followed a structured SOC incident response methodology.

### SOC Investigation Workflow

**Detection → Triage → Investigation → Analysis → Containment Recommendation → Escalation → Documentation**

### Recommended Security Actions

1. Prioritise high-risk phishing and financial fraud cases.
2. Verify suspected credential exposure.
3. Investigate suspicious authentication activity.
4. Review endpoint integrity alerts.
5. Validate malware detection rules.
6. Strengthen email authentication controls.
7. Review web server security configurations.
8. Maintain accurate incident records.
9. Escalate confirmed security incidents.
10. Improve monitoring and detection coverage.

---

#  Project Results & Achievements

### Investigation Outcomes

- Investigated **4 suspicious phishing and fraud emails**.
- Tested **3 Wazuh security detection scenarios**.
- Assessed **7 security investigation cases**.
- Documented **157 evidence screenshots**.
- Verified Wazuh File Integrity Monitoring detection.
- Verified Rootcheck system integrity alerts.
- Detected a Shellshock-related exploitation pattern.
- Configured YARA integration for further validation.
- Applied threat intelligence techniques to support security assessments.
- Produced investigation findings and response recommendations.

### Important Evidence Limitations

The investigation did not confirm:

- Successful phishing credential theft.
- Financial loss from the attempted invoice fraud.
- Successful Shellshock exploitation.
- A successful YARA signature match.
- Completion of all recommended restoration activities.

These limitations were documented to ensure accurate and evidence-based reporting.

---

#  Skills Demonstrated

### Security Operations
- SOC Alert Monitoring
- Security Event Analysis
- Alert Triage and Investigation
- Incident Response
- Security Incident Escalation
- Evidence Collection and Documentation

### Threat Intelligence
- Phishing Investigation
- IOC Identification and Enrichment
- Email Header Analysis
- Threat Classification
- MITRE ATT&CK Mapping
- Risk Assessment

### Technical Security
- Wazuh SIEM
- Linux Security Monitoring
- File Integrity Monitoring
- Rootcheck Investigation
- YARA Integration
- Web Server Log Analysis
- Security Detection Validation

### Professional Skills
- Analytical Thinking
- Technical Documentation
- Problem Solving
- Risk-Based Decision Making
- Security Reporting
- Investigation Communication

---

#  Lessons Learned

This capstone project reinforced several important cybersecurity principles:

**1. Detection does not always mean compromise.**

A security alert indicates suspicious activity requiring investigation, but additional evidence is necessary to confirm successful exploitation.

**2. Threat intelligence strengthens investigation quality.**

Reputation analysis, contextual information, and behavioural indicators help analysts make informed security decisions.

**3. Evidence-based reporting is essential.**

SOC analysts must distinguish verified findings from assumptions and unconfirmed activities.

**4. Security monitoring requires multiple detection methods.**

File integrity monitoring, system checks, and web server logs provide complementary visibility.

**5. Incident prioritisation supports effective response.**

Security incidents should be assessed according to potential business impact, likelihood, and available evidence.

---

# Future Improvements

Future development opportunities include:

- Completing end-to-end YARA detection validation.
- Integrating additional threat intelligence feeds.
- Developing improved Wazuh detection rules.
- Automating security alert enrichment.
- Expanding incident response playbooks.
- Improving alert correlation and prioritisation.
- Validating remediation and restoration procedures.
- Developing SOC reporting dashboards.

---

#  GitHub Repository Structure

```text
harmony-health-threat-intelligence-soc-investigation/
│
├── README.md
│
├── docs/
│   ├── executive-summary/
│   ├── phishing-investigations/
│   ├── wazuh-investigations/
│   └── incident-response/
│
├── screenshots/
│   ├── project-overview/
│   ├── phishing-analysis/
│   ├── fim-detection/
│   ├── rootcheck/
│   └── shellshock/
│
├── detection-rules/
│   └── README.md
│
└── lessons-learned/
    └── README.md
```

*The structure above is a recommended layout. Add supporting files only where available and safe to publish.*

---

#  Security and Ethical Considerations

This project was conducted for educational and cybersecurity training purposes in a controlled laboratory environment.

All investigation activities were intended to demonstrate defensive security monitoring, threat detection, analysis, and incident response.

Sensitive information, operational credentials, and harmful executable content are excluded from this public repository.

---

#  About the Author

**Faith Ejele**  
**Cybersecurity | SOC Analyst | Threat Intelligence**

Cybersecurity professional with a background in Computer Science, Data Analytics, and Cybersecurity.

Passionate about security monitoring, threat detection, incident investigation, and protecting organisations from evolving cyber threats.

My cybersecurity projects focus on practical investigation, technical problem-solving, evidence-based decision-making, and continuous improvement.

---

##  Connect With Me

**GitHub:** Explore my cybersecurity projects and practical SOC investigations.

**LinkedIn:** Connect with me to follow my cybersecurity learning journey, projects, and professional development.

---

###  Final Project Reflection

> Effective cybersecurity is not simply about generating alerts. It is about understanding the evidence, identifying genuine threats, assessing business impact, and making informed security decisions.

**Project:** Harmony Health Threat Investigation  
**Programme:** 10Alytics Cybersecurity Capstone  
**Author:** Faith Ejele  
**Year:** 2026

---

⭐ If you find this project useful, feel free to star the repository.
