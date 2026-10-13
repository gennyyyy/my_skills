---
name: compliance
description: Guides security professionals in implementing defense-in-depth security architectures, achieving compliance with industry frameworks (SOC2, ISO27001, GDPR, HIPAA), conducting threat modeling and risk assessments, managing security operations and incident response, and embedding security throughout the SDLC. Data privacy and regulatory compliance specialist for GDPR, CCPA, HIPAA, and international data protection laws. Use when implementing privacy controls, conducting data protection impact assessments, ensuring regulatory compliance, or managing data subject rights. Expert in consent management, data minimization, and privacy-by-design principles. Senior Information Security Manager specializing in ISO 27001 and ISO 27002 implementation for HealthTech and MedTech companies. Provides ISMS implementation, cybersecurity risk assessment, security controls management, and compliance oversight. Use for ISMS design, security risk assessments, control implementation, and ISO 27001 certification activities.
---


# Security & Compliance Expert

## Core Principles

### 1. Defense in Depth
Apply multiple layers of security controls so that if one fails, others provide protection. Never rely on a single security mechanism.

### 2. Zero Trust Architecture
Never trust, always verify. Assume breach and verify every access request regardless of location or network.

### 3. Least Privilege
Grant the minimum access necessary for users and systems to perform their functions. Regularly review and revoke unused permissions.

### 4. Security by Design
Integrate security requirements from the earliest stages of system design, not as an afterthought.

### 5. Continuous Monitoring
Implement ongoing monitoring and alerting to detect anomalies and security events in real-time.

### 6. Risk-Based Approach
Prioritize security efforts based on risk assessment, focusing resources on the most critical assets and likely threats.

### 7. Compliance as Foundation
Use compliance frameworks as a baseline, but go beyond minimum requirements to achieve actual security.

### 8. Incident Readiness
Prepare for security incidents through planning, testing, and regular tabletop exercises. Assume compromise will occur.

---

## Security & Compliance Lifecycle

### Phase 1: Assess & Plan
**Objective**: Understand current security posture and compliance requirements

**Activities**:
- Conduct security assessments and gap analysis
- Identify compliance requirements (SOC2, ISO27001, GDPR, HIPAA, PCI-DSS)
- Perform risk assessments and threat modeling
- Define security policies and standards
- Establish security governance structure
- Create security roadmap with prioritized initiatives

**Deliverables**:
- Risk register with prioritized risks
- Compliance gap analysis report
- Security architecture documentation
- Security policies and procedures
- Security roadmap and budget

### Phase 2: Design & Architect
**Objective**: Design secure systems and architectures

**Activities**:
- Design defense-in-depth architectures
- Implement Zero Trust network architecture
- Design identity and access management (IAM) systems
- Architect data protection and encryption solutions
- Design secure CI/CD pipelines
- Create threat models for applications and systems
- Define security controls and compensating controls

**Deliverables**:
- Security architecture diagrams
- Threat models (STRIDE, PASTA, or attack trees)
- Data flow diagrams with security boundaries
- Encryption and key management design
- IAM design with RBAC/ABAC models
- Security control matrix

### Phase 3: Implement & Harden
**Objective**: Deploy security controls and harden systems

**Activities**:
- Implement security controls (preventive, detective, corrective)
- Configure security tools (SIEM, EDR, CASB, WAF, IDS/IPS)
- Harden operating systems and applications
- Implement encryption at rest and in transit
- Deploy multi-factor authentication (MFA)
- Configure logging and monitoring
- Implement data loss prevention (DLP)
- Set up vulnerability management program

**Deliverables**:
- Hardening baselines and configuration standards
- Deployed security tools and controls
- Encryption implementation
- MFA deployment
- Security monitoring dashboards
- Vulnerability management procedures

### Phase 4: Monitor & Detect
**Objective**: Continuously monitor for threats and anomalies

**Activities**:
- Monitor security logs and events (SIEM)
- Analyze security alerts and anomalies
- Conduct threat hunting
- Perform vulnerability scanning and penetration testing
- Monitor compliance controls
- Track security metrics and KPIs
- Review access logs and privileged account activity
- Analyze threat intelligence feeds

**Deliverables**:
- Security operations center (SOC) runbooks
- Alert triage and escalation procedures
- Threat hunting playbooks
- Vulnerability scan reports
- Penetration test reports
- Security metrics dashboard
- Compliance monitoring reports

### Phase 5: Respond & Recover
**Objective**: Respond to security incidents and recover operations

**Activities**:
- Execute incident response plan
- Contain and eradicate threats
- Perform forensic analysis
- Recover affected systems
- Conduct post-incident reviews
- Update security controls based on lessons learned
- Report incidents to stakeholders and regulators
- Improve detection rules and response procedures

**Deliverables**:
- Incident response reports
- Forensic analysis findings
- Root cause analysis
- Remediation plans
- Updated incident response playbooks
- Regulatory breach notifications (if required)
- Post-incident review and recommendations

### Phase 6: Audit & Improve
**Objective**: Validate compliance and continuously improve security

**Activities**:
- Conduct internal audits
- Prepare for external audits (SOC2, ISO27001)
- Perform compliance assessments
- Review and update security policies
- Conduct security training and awareness programs
- Perform tabletop exercises and disaster recovery drills
- Update risk assessments
- Implement security improvements

**Deliverables**:
- Audit reports (internal and external)
- SOC2 Type II report
- ISO27001 certification
- Compliance attestations
- Updated policies and procedures
- Training completion metrics
- Tabletop exercise results
- Continuous improvement plan

---

## Decision Frameworks

### 1. Risk Assessment Framework

**When to use**: Evaluating security risks and prioritizing mitigation efforts

**Process**:

```
1. Identify Assets
   - What systems, data, and services need protection?
   - What is the business value of each asset?
   - Who are the asset owners?

2. Identify Threats
   - What threat actors might target these assets? (nation-state, cybercriminals, insiders)
   - What are their motivations? (financial gain, espionage, disruption)
   - What are current threat trends?

3. Identify Vulnerabilities
   - What weaknesses exist in systems or processes?
   - What security controls are missing or ineffective?
   - What are known CVEs affecting your systems?

4. Calculate Risk
   Risk = Likelihood × Impact

   Likelihood scale (1-5):
   1 = Rare (< 5% chance in 1 year)
   2 = Unlikely (5-25%)
   3 = Possible (25-50%)
   4 = Likely (50-75%)
   5 = Almost Certain (> 75%)

   Impact scale (1-5):
   1 = Minimal (< $10K loss, no data breach)
   2 = Minor ($10K-$100K, limited data exposure)
   3 = Moderate ($100K-$1M, significant data breach)
   4 = Major ($1M-$10M, extensive data breach, regulatory fines)
   5 = Catastrophic (> $10M, business-threatening)

   Risk Score = Likelihood × Impact (max 25)

5. Prioritize Risks
   - Critical: Risk score 15-25 (immediate action)
   - High: Risk score 10-14 (action within 30 days)
   - Medium: Risk score 5-9 (action within 90 days)
   - Low: Risk score 1-4 (monitor and accept)

6. Determine Risk Response
   - Mitigate: Implement controls to reduce risk
   - Accept: Document acceptance if risk is within tolerance
   - Transfer: Use insurance or third-party services
   - Avoid: Eliminate the activity that creates risk
```

**Output**: Risk register with prioritized risks and mitigation plans

### 2. Security Control Selection

**When to use**: Choosing appropriate security controls for identified risks

**Framework**: Use NIST CSF categories or CIS Controls

```
NIST CSF Functions:
1. Identify (ID)
   - Asset Management
   - Risk Assessment
   - Governance

2. Protect (PR)
   - Access Control
   - Data Security
   - Protective Technology

3. Detect (DE)
   - Anomalies and Events
   - Security Monitoring
   - Detection Processes

4. Respond (RS)
   - Response Planning
   - Communications
   - Analysis and Mitigation

5. Recover (RC)
   - Recovery Planning
   - Improvements
   - Communications

Control Types:
- Preventive: Stop incidents before they occur (MFA, firewalls, encryption)
- Detective: Identify incidents when they occur (SIEM, IDS, log monitoring)
- Corrective: Fix issues after detection (patching, incident response)
- Deterrent: Discourage attackers (security policies, warnings)
- Compensating: Alternative controls when primary controls aren't feasible

Selection Criteria:
1. Does it address the identified risk?
2. Is it cost-effective? (Control cost < Risk value)
3. Is it technically feasible?
4. Does it meet compliance requirements?
5. Can we maintain and monitor it?
```

### 3. Compliance Framework Selection

**When to use**: Determining which compliance frameworks to implement

**Decision Tree**:

```
What type of organization are you?

├─ SaaS/Cloud Service Provider
│  ├─ Selling to enterprises? → SOC2 Type II (required)
│  ├─ International customers? → ISO27001 (strongly recommended)
│  ├─ Handling health data? → HIPAA + HITRUST
│  └─ Handling payment cards? → PCI-DSS

├─ Healthcare Provider/Payer
│  ├─ U.S.-based → HIPAA (required)
│  ├─ International → HIPAA + GDPR
│  └─ Plus: HITRUST for comprehensive framework

├─ Financial Services
│  ├─ U.S. banks → GLBA, SOX (if public)
│  ├─ Payment processing → PCI-DSS (required)
│  ├─ International → ISO27001, local regulations
│  └─ Plus: NIST CSF for framework

├─ E-commerce/Retail
│  ├─ Accept credit cards → PCI-DSS (required)
│  ├─ EU customers → GDPR (required)
│  ├─ California customers → CCPA
│  └─ B2B sales → SOC2 Type II

└─ General Enterprise
   ├─ Selling to enterprises → SOC2 Type II
   ├─ Want broad recognition → ISO27001
   ├─ Government contracts → FedRAMP, NIST 800-53
   └─ Industry-specific → Check sector regulations

Multi-Framework Strategy:
- Start with: SOC2 or ISO27001 (choose one as foundation)
- Add: Data privacy regulations (GDPR, CCPA) as needed
- Layer on: Industry-specific requirements
```

### 4. Incident Severity Classification

**When to use**: Triaging and responding to security incidents

**Severity Levels**:

```
P0 - Critical (Immediate Response)
- Active breach with data exfiltration occurring
- Ransomware encryption in progress
- Complete system outage of critical services
- Unauthorized access to production databases
- Response: Engage CIRT immediately, executive notification, 24/7 effort

P1 - High (Response within 1 hour)
- Confirmed malware on critical systems
- Attempted unauthorized access to sensitive data
- DDoS attack affecting availability
- Significant vulnerability with active exploits
- Response: Engage CIRT, manager notification, work until contained

P2 - Medium (Response within 4 hours)
- Malware on non-critical systems
- Suspicious account activity
- Policy violations with security impact
- Vulnerability requiring patching
- Response: Security team investigation, business hours

P3 - Low (Response within 24 hours)
- Failed login attempts (below threshold)
- Minor policy violations
- Informational security events
- Response: Standard queue, document findings

Classification Factors:
1. Data confidentiality impact (PHI, PII, financial, IP)
2. System availability impact (revenue, operations)
3. Data integrity impact (corruption, unauthorized changes)
4. Number of affected systems/users
5. Regulatory reporting requirements
```

### 5. Vulnerability Prioritization

**When to use**: Prioritizing vulnerability remediation

**Framework**: Enhanced CVSS with business context

```
Base CVSS Score × Business Context Multiplier = Priority Score

CVSS Severity Ranges:
- Critical: 9.0-10.0
- High: 7.0-8.9
- Medium: 4.0-6.9
- Low: 0.1-3.9

Business Context Multipliers:
- Internet-facing production system: 2.0×
- Internal production system: 1.5×
- Systems with sensitive data: 1.5×
- Development/test environment: 0.5×
- Active exploit in the wild: 2.0×
- Compensating controls in place: 0.7×

Priority Levels:
- P0 (Critical): Score ≥ 14 → Patch within 24-48 hours
- P1 (High): Score 10-13.9 → Patch within 7 days
- P2 (Medium): Score 6-9.9 → Patch within 30 days
- P3 (Low): Score < 6 → Patch within 90 days or accept risk

Additional Considerations:
- Can the system be isolated/segmented?
- Are there effective detective controls?
- What is the patching complexity/risk?
- Is there a vendor patch available?
```

### 6. Third-Party Risk Assessment

**When to use**: Evaluating security risks of vendors and partners

**Assessment Framework**:

```
1. Categorize Vendor Risk Level

Low Risk (Minimal assessment):
- No access to systems or data
- Limited integration
- Non-critical service
→ Simple questionnaire

Medium Risk (Standard assessment):
- Limited system access
- Non-sensitive data access
- Important but not critical service
→ Security questionnaire + evidence review

High Risk (Comprehensive assessment):
- Production system access
- Sensitive data processing
- Critical service dependency
→ Full assessment + audit reports + pen test

Critical Risk (Extensive assessment):
- Full production access
- PHI/PII processing
- Business-critical dependency
→ On-site audit + continuous monitoring + SLA

2. Assessment Components

For Medium/High/Critical vendors:
□ Security questionnaire (SIG, CAIQ, or custom)
□ Compliance certifications (SOC2, ISO27001)
□ Insurance certificates (cyber liability)
□ Security policies and procedures
□ Incident response plan
□ Disaster recovery/business continuity plan
□ Data processing agreement (DPA)
□ Penetration test results (for high/critical)
□ Right to audit clause in contract

3. Ongoing Monitoring

- Annual reassessment
- Monitor for breaches/incidents
- Review security updates and patches
- Track compliance certification renewals
- Conduct periodic audits (for critical vendors)

4. Vendor Risk Score

Calculate score (0-100):
- Security maturity: 40 points
- Compliance certifications: 20 points
- Incident history: 15 points
- Financial stability: 15 points
- References and reputation: 10 points

Action based on score:
- 80-100: Approved
- 60-79: Approved with conditions
- 40-59: Requires remediation plan
- < 40: Do not engage
```

---

## Key Security Frameworks & Standards

### NIST Cybersecurity Framework (CSF)
- **Purpose**: Risk-based framework for improving cybersecurity
- **Structure**: 5 Functions, 23 Categories, 108 Subcategories
- **Best for**: General organizations, government contractors
- **Maturity model**: Tier 1 (Partial) to Tier 4 (Adaptive)

### CIS Critical Security Controls
- **Purpose**: Prioritized set of actions for cyber defense
- **Structure**: 18 Controls with Implementation Groups (IG1, IG2, IG3)
- **Best for**: Practical implementation guidance
- **Focus**: Defense against common attack patterns

### ISO/IEC 27001
- **Purpose**: International standard for information security management
- **Structure**: 14 domains, 114 controls (Annex A)
- **Best for**: International recognition, formal certification
- **Requirements**: ISMS (Information Security Management System)

### SOC 2 Type II
- **Purpose**: Service organization controls for security and availability
- **Structure**: Trust Service Criteria (Security, Availability, Confidentiality, Processing Integrity, Privacy)
- **Best for**: SaaS companies, cloud service providers
- **Audit**: 3-12 month observation period

### NIST 800-53
- **Purpose**: Security controls for federal systems
- **Structure**: 20 families, 1000+ controls
- **Best for**: Government contractors, FedRAMP
- **Baselines**: Low, Moderate, High impact systems

### GDPR (General Data Protection Regulation)
- **Purpose**: EU data privacy regulation
- **Scope**: Any organization processing EU residents' data
- **Requirements**: Lawful basis, consent, data subject rights, breach notification
- **Penalties**: Up to 4% of global revenue or €20M

### HIPAA (Health Insurance Portability and Accountability Act)
- **Purpose**: Protect health information (PHI)
- **Scope**: Healthcare providers, payers, business associates
- **Requirements**: Administrative, Physical, Technical safeguards
- **Penalties**: $100-$50,000 per violation, criminal charges possible

### PCI-DSS (Payment Card Industry Data Security Standard)
- **Purpose**: Protect cardholder data
- **Structure**: 12 requirements, 6 control objectives
- **Scope**: Any organization storing, processing, or transmitting card data
- **Levels**: Based on transaction volume (Level 1-4)

---

## Core Security Domains

### 1. Identity & Access Management (IAM)
- Authentication mechanisms (MFA, SSO, passwordless)
- Authorization models (RBAC, ABAC, ReBAC)
- Privileged access management (PAM)
- Identity governance and administration (IGA)
- Directory services (Active Directory, LDAP, Okta, Auth0)

### 2. Network Security
- Network segmentation and micro-segmentation
- Firewalls (next-gen, WAF, application-layer)
- Intrusion detection/prevention (IDS/IPS)
- VPN and secure remote access
- Zero Trust network architecture (ZTNA)
- DDoS protection

### 3. Data Security
- Encryption at rest and in transit (AES-256, TLS 1.3)
- Key management (KMS, HSM)
- Data classification and labeling
- Data loss prevention (DLP)
- Database security (encryption, masking, tokenization)
- Secrets management (Vault, AWS Secrets Manager)

### 4. Application Security
- Secure SDLC and DevSecOps
- SAST (Static Application Security Testing)
- DAST (Dynamic Application Security Testing)
- SCA (Software Composition Analysis)
- Secure code review
- OWASP Top 10 mitigation

### 5. Cloud Security
- Cloud security posture management (CSPM)
- Cloud access security broker (CASB)
- Container security (image scanning, runtime protection)
- Serverless security
- Infrastructure as Code (IaC) security scanning
- Multi-cloud security architecture

### 6. Endpoint Security
- Endpoint detection and response (EDR)
- Antivirus and anti-malware
- Host-based firewalls
- Device encryption (BitLocker, FileVault)
- Mobile device management (MDM)
- Patch management

### 7. Security Operations
- Security Information and Event Management (SIEM)
- Security Orchestration, Automation, and Response (SOAR)
- Threat intelligence platforms (TIP)
- Threat hunting
- Vulnerability management
- Penetration testing and red teaming

### 8. Incident Response
- Incident response plan and playbooks
- Computer forensics and investigation
- Malware analysis
- Threat containment and eradication
- Post-incident review and lessons learned
- Regulatory breach notification

### 9. Governance, Risk & Compliance (GRC)
- Security policies and procedures
- Risk assessment and management
- Compliance management and auditing
- Security awareness training
- Vendor risk management
- Business continuity and disaster recovery

---

## Security Metrics & KPIs

### Risk & Compliance Metrics
- Number of critical/high risks open
- Risk remediation time (mean time to remediate)
- Compliance audit findings (open/closed)
- Compliance control effectiveness rate
- Policy acknowledgment completion rate
- Training completion rate

### Vulnerability Management Metrics
- Mean time to detect (MTTD) vulnerabilities
- Mean time to patch (MTTP)
- Vulnerability backlog (total open, by severity)
- Patch compliance rate (% systems patched within SLA)
- Vulnerability recurrence rate

### Incident Response Metrics
- Mean time to detect (MTTD) incidents
- Mean time to respond (MTTR)
- Mean time to contain (MTTC)
- Mean time to recover (MTTR)
- Number of incidents by severity
- Incident recurrence rate
- False positive rate

### Security Operations Metrics
- SIEM alert volume (total, by severity)
- Alert triage time
- Alert false positive rate
- Security tool coverage (% assets monitored)
- Threat hunting coverage (% environment reviewed)
- Penetration test findings

### Access Management Metrics
- MFA adoption rate
- Privileged account review completion rate
- Access certification completion rate
- Orphaned account count
- Password policy compliance rate
- Failed login attempt rate

### Awareness & Culture Metrics
- Phishing simulation click rate
- Security training completion rate
- Security awareness quiz scores
- Security policy violations
- Security-related helpdesk tickets

---

## Security Tools Ecosystem

### SIEM (Security Information & Event Management)
- Splunk Enterprise Security
- IBM QRadar
- Microsoft Sentinel
- Elastic Security
- Sumo Logic

### EDR/XDR (Endpoint/Extended Detection & Response)
- CrowdStrike Falcon
- SentinelOne
- Microsoft Defender for Endpoint
- Palo Alto Cortex XDR
- Carbon Black

### Vulnerability Management
- Tenable Nessus/Tenable.io
- Qualys VMDR
- Rapid7 InsightVM
- Greenbone OpenVAS (open source)

### Cloud Security
- Wiz
- Prisma Cloud (Palo Alto)
- Lacework
- Orca Security
- AWS Security Hub / Azure Security Center / GCP Security Command Center

### SAST/DAST
- Snyk
- Veracode
- Checkmarx
- SonarQube
- OWASP ZAP (open source)

### Container Security
- Aqua Security
- Sysdig Secure
- Prisma Cloud Compute
- Trivy (open source)

### Secrets Management
- HashiCorp Vault
- AWS Secrets Manager
- Azure Key Vault
- CyberArk

### Identity & Access
- Okta
- Auth0
- Azure AD / Entra ID
- Ping Identity
- CyberArk (PAM)

---

## Common Security Workflows

### 1. Security Incident Response Workflow

```
1. Detection & Alert
   ↓
2. Triage & Classification
   - Determine severity (P0-P3)
   - Assign to responder
   ↓
3. Investigation
   - Gather evidence
   - Analyze logs (SIEM)
   - Determine scope
   ↓
4. Containment
   - Isolate affected systems
   - Block malicious IPs/domains
   - Disable compromised accounts
   ↓
5. Eradication
   - Remove malware
   - Close vulnerabilities
   - Patch systems
   ↓
6. Recovery
   - Restore from backups
   - Verify system integrity
   - Return to production
   ↓
7. Post-Incident Review
   - Document timeline
   - Root cause analysis
   - Update playbooks
   - Implement improvements
   ↓
8. Reporting
   - Executive summary
   - Regulatory notification (if required)
   - Stakeholder communication
```

### 2. Vulnerability Management Workflow

```
1. Asset Discovery
   - Scan network for assets
   - Maintain asset inventory
   ↓
2. Vulnerability Scanning
   - Authenticated scans
   - Unauthenticated scans
   - Agent-based monitoring
   ↓
3. Assessment & Validation
   - Validate findings
   - Remove false positives
   - Add business context
   ↓
4. Prioritization
   - Apply CVSS + context
   - Assign severity (P0-P3)
   - Create remediation tickets
   ↓
5. Remediation
   - Patch systems
   - Apply compensating controls
   - Update configurations
   ↓
6. Verification
   - Rescan to confirm fix
   - Update vulnerability status
   ↓
7. Reporting
   - Metrics dashboard
   - Executive reports
   - Trend analysis
```

### 3. Access Review Workflow

```
1. Schedule Review (Quarterly)
   ↓
2. Generate Access Reports
   - User access by role
   - Privileged accounts
   - Service accounts
   - Orphaned accounts
   ↓
3. Distribute to Managers
   - Each manager reviews their team
   - Certify appropriate access
   ↓
4. Review & Certify
   - Approve legitimate access
   - Flag inappropriate access
   - Identify orphaned accounts
   ↓
5. Remediation
   - Revoke unapproved access
   - Disable orphaned accounts
   - Update RBAC assignments
   ↓
6. Document & Report
   - Certification completion rate
   - Access changes made
   - Compliance evidence
```

### 4. SOC2 Audit Preparation Workflow

```
1. Scoping (3-4 months before)
   - Define in-scope systems
   - Select Trust Service Criteria
   - Engage auditor
   ↓
2. Gap Assessment (2-3 months before)
   - Map controls to requirements
   - Identify control gaps
   - Create remediation plan
   ↓
3. Readiness (1-2 months before)
   - Implement missing controls
   - Document policies/procedures
   - Conduct mock audit
   ↓
4. Evidence Collection (Ongoing)
   - Automate evidence gathering
   - Organize evidence repository
   - Prepare control narratives
   ↓
5. Audit Kickoff
   - Provide evidence to auditor
   - Respond to requests
   - Schedule interviews
   ↓
6. Fieldwork (4-6 weeks)
   - Auditor tests controls
   - Provide additional evidence
   - Address findings
   ↓
7. Report Issuance
   - Review draft report
   - Address any exceptions
   - Receive final SOC2 report
   ↓
8. Continuous Monitoring
   - Monitor control effectiveness
   - Prepare for next audit cycle
```

---

## Best Practices

### Security Architecture
- Design with security in mind from the start (shift-left)
- Apply defense in depth with multiple security layers
- Implement Zero Trust: verify explicitly, use least privilege, assume breach
- Segment networks and limit lateral movement
- Encrypt data at rest and in transit
- Use secure defaults and fail securely

### Access Control
- Enforce multi-factor authentication (MFA) everywhere
- Implement least privilege access
- Use just-in-time (JIT) privileged access
- Regularly review and certify access
- Disable accounts promptly on termination
- Avoid shared accounts and service account abuse

### Security Operations
- Centralize logging with SIEM
- Automate detection and response where possible
- Maintain an incident response plan and test it
- Conduct regular threat hunting exercises
- Keep vulnerability remediation SLAs aggressive
- Practice incident response through tabletop exercises

### Application Security
- Integrate security into CI/CD (DevSecOps)
- Scan code for vulnerabilities (SAST, DAST, SCA)
- Follow OWASP Top 10 guidelines
- Conduct security code reviews for critical changes
- Implement secure API design (authentication, rate limiting, input validation)
- Use security headers (CSP, HSTS, X-Frame-Options)

### Cloud Security
- Use infrastructure as code (IaC) with security scanning
- Enable cloud-native security services (GuardDuty, Security Hub)
- Implement CSPM to monitor misconfigurations
- Use cloud-native encryption and key management
- Apply least privilege IAM policies
- Monitor for shadow IT and unauthorized resources

### Compliance
- Treat compliance as a continuous process, not one-time
- Map controls to multiple frameworks for efficiency
- Automate evidence collection where possible
- Maintain a compliance calendar for deadlines
- Document everything (if it's not documented, it doesn't exist)
- Conduct internal audits before external audits

### Security Culture
- Make security everyone's responsibility
- Conduct regular security awareness training
- Run phishing simulations to test awareness
- Reward security-conscious behavior
- Create clear, accessible security policies
- Foster a culture where reporting security concerns is encouraged

---

## Integration with Other Disciplines

### With DevOps/Platform Engineering
- Integrate security scanning into CI/CD pipelines
- Automate security testing and compliance checks
- Implement Infrastructure as Code (IaC) security
- Use container scanning and runtime protection
- Coordinate on incident response for production issues

### With Enterprise Architecture
- Align security architecture with enterprise architecture
- Participate in architecture review boards
- Ensure security requirements in architecture standards
- Design secure integration patterns
- Define security reference architectures

### With IT Operations
- Coordinate on patch management and change control
- Collaborate on monitoring and alerting
- Joint incident response for security and operational incidents
- Align on backup and disaster recovery procedures
- Coordinate access management and privileged access

### With Product Management
- Provide security requirements for new features
- Participate in threat modeling for new products
- Balance security with user experience
- Advise on privacy and compliance implications
- Support security as a product differentiator

### With Legal/Privacy
- Coordinate on data privacy regulations (GDPR, CCPA)
- Collaborate on breach notification requirements
- Review vendor contracts for security terms
- Support privacy impact assessments
- Align on data retention and deletion policies

---

## When to Engage Security & Compliance

### Required Engagement
- New system or application design
- Architecture changes affecting security boundaries
- Regulatory compliance initiatives
- Security incidents
- Vendor risk assessments
- Pre-production security reviews
- Audit preparation
- Data breach or suspected breach

### Recommended Engagement
- Major feature releases
- Cloud migrations
- M&A due diligence
- Infrastructure changes
- New third-party integrations
- Significant process changes
- Security tool selection
- Policy updates

### Continuous Collaboration
- Security review of pull requests (for critical systems)
- Vulnerability remediation prioritization
- Security awareness and training
- Threat intelligence sharing
- Risk assessment updates
- Compliance monitoring


---

<!-- merged-in: enterprise-communication/data-privacy-compliance, enterprise-communication/information-security-manager-iso27001 -->


# Merged section: data-privacy-compliance (from enterprise-communication/data-privacy-compliance)
Supporting files from this skill live in `references/data-privacy-compliance/`, `scripts/data-privacy-compliance/`, `data/data-privacy-compliance/` (whichever exist).

# Data Privacy Compliance

Comprehensive guidance for implementing data privacy compliance across GDPR, CCPA, HIPAA, and other global data protection regulations.

## When to Use This Skill

Use this skill when:
- Implementing GDPR, CCPA, or HIPAA compliance
- Conducting Data Protection Impact Assessments (DPIA)
- Managing data subject rights (access, deletion, portability)
- Implementing consent management systems
- Drafting privacy policies and notices
- Handling data breaches and incident response
- Designing privacy-by-design systems
- Conducting privacy audits and assessments

## Key Regulations Overview

### GDPR (General Data Protection Regulation)
**Scope:** EU residents' data, regardless of where company is located
**Key Requirements:**
- Lawful basis for processing (consent, contract, legitimate interest, etc.)
- Data subject rights (access, deletion, portability, objection)
- Data Protection Impact Assessments for high-risk processing
- 72-hour breach notification requirement
- Records of processing activities
- Privacy by design and by default

**Penalties:** Up to €20M or 4% of global annual revenue

### CCPA/CPRA (California Consumer Privacy Act)
**Scope:** California residents' data
**Key Requirements:**
- Right to know what data is collected
- Right to delete personal information
- Right to opt-out of sale/sharing
- Right to correct inaccurate information
- Right to limit use of sensitive personal information

**Penalties:** Up to $7,500 per intentional violation

### HIPAA (Health Insurance Portability and Accountability Act)
**Scope:** Protected Health Information (PHI) in the US
**Key Requirements:**
- Privacy Rule (patient rights and information uses)
- Security Rule (safeguards for ePHI)
- Breach Notification Rule (60-day notification)
- Business Associate Agreements (BAAs)

**Penalties:** Up to $1.5M per violation category per year

## Data Subject Rights Implementation

### 1. Right to Access (GDPR Art. 15 / CCPA § 1798.100)

**Request Handler:**
```javascript
async function handleAccessRequest(userId, email) {
  // Verify identity
  const verified = await verifyIdentity(email);
  if (!verified) throw new Error('Identity verification failed');

  // Collect all personal data
  const userData = await collectUserData(userId);

  // Format for readability
  const report = {
    personalInfo: userData.profile,
    activityLogs: userData.activities,
    preferences: userData.settings,
    thirdPartySharing: userData.dataSharing,
    retentionPeriod: '2 years from last activity',
    dataProtectionOfficer: 'dpo@company.com'
  };

  // Generate downloadable report
  const pdf = await generatePDFReport(report);

  // Log request for compliance
  await logAccessRequest(userId, 'completed');

  return pdf;
}
```

**Response Timeline:**
- GDPR: 1 month (extendable to 3 months)
- CCPA: 45 days (extendable to 90 days)

### 2. Right to Deletion (GDPR Art. 17 / CCPA § 1798.105)

**Deletion Handler:**
```javascript
async function handleDeletionRequest(userId, email) {
  // Verify identity
  const verified = await verifyIdentity(email);
  if (!verified) throw new Error('Identity verification failed');

  // Check for legal obligations to retain
  const mustRetain = await checkRetentionRequirements(userId);
  if (mustRetain.required) {
    return {
      status: 'partial_deletion',
      retained: mustRetain.data,
      reason: mustRetain.legalBasis,
      retentionPeriod: mustRetain.period
    };
  }

  // Delete from all systems
  await Promise.all([
    deleteFromDatabase(userId),
    deleteFromBackups(userId), // Mark for deletion in next backup cycle
    deleteFromAnalytics(userId),
    deleteFromThirdPartyServices(userId),
    revokeAPIKeys(userId),
    anonymizeHistoricalRecords(userId)
  ]);

  // Confirm deletion
  await sendDeletionConfirmation(email);
  await logDeletionRequest(userId, 'completed');

  return { status: 'deleted', timestamp: new Date() };
}
```

**Exceptions (when deletion can be refused):**
- Legal obligations (tax records, contracts)
- Public interest/scientific research
- Defense of legal claims
- Exercise of freedom of expression

### 3. Right to Data Portability (GDPR Art. 20)

**Export Handler:**
```javascript
async function handlePortabilityRequest(userId, format = 'json') {
  const userData = await collectUserData(userId);

  // Structure in machine-readable format
  const portableData = {
    exportDate: new Date().toISOString(),
    userId: userId,
    data: {
      profile: userData.profile,
      content: userData.userGeneratedContent,
      settings: userData.preferences,
      history: userData.activityHistory
    }
  };

  // Support multiple formats
  if (format === 'csv') {
    return convertToCSV(portableData);
  } else if (format === 'xml') {
    return convertToXML(portableData);
  }

  return portableData; // JSON by default
}
```

**Requirements:**
- Structured, commonly used, machine-readable format
- Ability to transmit directly to another controller
- Only applies to data provided by data subject
- Only for automated processing based on consent or contract

### 4. Right to Object (GDPR Art. 21)

**Objection Handler:**
```javascript
async function handleObjectionRequest(userId, processingType) {
  switch (processingType) {
    case 'direct_marketing':
      // Must stop immediately
      await disableMarketing(userId);
      await updateConsent(userId, 'marketing', false);
      break;

    case 'legitimate_interest':
      // Assess if we have compelling grounds
      const assessment = await assessLegitimateInterest(userId);
      if (!assessment.compelling) {
        await stopProcessing(userId, processingType);
      }
      return assessment;

    case 'profiling':
      await disableProfiling(userId);
      await updateConsent(userId, 'profiling', false);
      break;

    default:
      throw new Error('Invalid processing type');
  }

  await logObjectionRequest(userId, processingType, 'granted');
}
```

## Consent Management

### Consent Requirements (GDPR)

**Valid Consent Must Be:**
1. Freely given (no coercion)
2. Specific (for each purpose)
3. Informed (clear language)
4. Unambiguous (clear affirmative action)
5. Withdrawable (as easy to withdraw as to give)

**Consent Implementation:**
```html
<!-- Good: Granular consent -->
<form>
  <h3>Privacy Preferences</h3>

  <label>
    <input type="checkbox" name="essential" checked disabled>
    <strong>Essential cookies (Required)</strong>
    <p>Necessary for website functionality</p>
  </label>

  <label>
    <input type="checkbox" name="analytics" value="analytics">
    <strong>Analytics cookies</strong>
    <p>Help us improve our website by collecting usage data</p>
  </label>

  <label>
    <input type="checkbox" name="marketing" value="marketing">
    <strong>Marketing cookies</strong>
    <p>Show you personalized ads based on your interests</p>
  </label>

  <button type="submit">Save Preferences</button>
  <a href="/privacy-policy">Learn More</a>
</form>
```

**Consent Record Storage:**
```javascript
const consentRecord = {
  userId: 'user123',
  timestamp: new Date().toISOString(),
  consentVersion: '2.0',
  purposes: {
    essential: { granted: true, required: true },
    analytics: { granted: true, purpose: 'Website improvement' },
    marketing: { granted: false, purpose: 'Personalized advertising' }
  },
  ipAddress: '192.168.1.1', // For proof
  userAgent: 'Mozilla/5.0...', // For context
  method: 'explicit_opt_in' // or 'implicit', 'presumed'
};

await saveConsentRecord(consentRecord);
```

### Cookie Banner (GDPR Compliant)

```html
<div id="cookie-banner" role="dialog" aria-labelledby="cookie-title">
  <h2 id="cookie-title">Cookie Preferences</h2>
  <p>
    We use cookies to enhance your experience. Choose which cookies you
    allow us to use. You can change your preferences at any time.
  </p>

  <button onclick="acceptAll()">Accept All</button>
  <button onclick="rejectNonEssential()">Reject Non-Essential</button>
  <button onclick="showPreferences()">Manage Preferences</button>
</div>

<script>
// Must not load non-essential cookies until consent given
function acceptAll() {
  setConsent({ analytics: true, marketing: true });
  loadAnalyticsCookies();
  loadMarketingCookies();
  hideBanner();
}

function rejectNonEssential() {
  setConsent({ analytics: false, marketing: false });
  hideBanner();
}
</script>
```

## Privacy by Design Principles

### 1. Data Minimization

**Principle:** Collect only data necessary for specified purpose

**Implementation:**
```javascript
// ❌ Bad: Collecting unnecessary data
const userRegistration = {
  email: req.body.email,
  password: req.body.password,
  fullName: req.body.fullName,
  phoneNumber: req.body.phoneNumber, // Not needed
  dateOfBirth: req.body.dateOfBirth, // Not needed
  address: req.body.address, // Not needed
  socialSecurityNumber: req.body.ssn // Definitely not needed!
};

// ✅ Good: Only essential data
const userRegistration = {
  email: req.body.email,
  password: hashPassword(req.body.password),
  displayName: req.body.displayName // Optional
};
```

### 2. Purpose Limitation

**Principle:** Use data only for specified, explicit purposes

**Implementation:**
```javascript
// Document and enforce purpose
const dataProcessingPurpose = {
  email: [
    'account_authentication',
    'order_confirmations',
    'password_reset'
  ],
  phoneNumber: [
    'order_delivery_notifications'
    // NOT: 'marketing_calls' (requires separate consent)
  ],
  purchaseHistory: [
    'order_fulfillment',
    'customer_support'
    // NOT: 'targeted_advertising' (requires separate consent)
  ]
};

async function processData(data, purpose) {
  if (!isAllowedPurpose(data.type, purpose)) {
    throw new Error('Purpose not authorized for this data');
  }
  // Proceed with processing
}
```

### 3. Storage Limitation

**Principle:** Retain data only as long as necessary

**Implementation:**
```javascript
const retentionPolicy = {
  userAccounts: {
    active: 'indefinite',
    inactive: '2 years',
    deleted: '30 days grace period'
  },
  orderRecords: '7 years', // Legal requirement
  supportTickets: '3 years',
  analytics: '26 months',
  marketingData: '1 year or until consent withdrawn'
};

// Automated data deletion
async function enforceRetentionPolicy() {
  const now = new Date();

  // Delete inactive accounts
  await User.deleteMany({
    lastActive: { $lt: subYears(now, 2) },
    status: 'inactive'
  });

  // Anonymize old analytics
  await Analytics.updateMany(
    { createdAt: { $lt: subMonths(now, 26) } },
    { $unset: { userId: 1, ipAddress: 1 } }
  );

  // Delete expired marketing consent
  await MarketingConsent.deleteMany({
    $or: [
      { expiresAt: { $lt: now } },
      { withdrawnAt: { $lt: subDays(now, 30) } }
    ]
  });
}

// Schedule daily
cron.schedule('0 2 * * *', enforceRetentionPolicy);
```

## Data Protection Impact Assessment (DPIA)

**When Required (GDPR Art. 35):**
- Systematic and extensive profiling
- Large-scale processing of sensitive data
- Systematic monitoring of publicly accessible areas
- New technologies with high privacy risks

**DPIA Template:**
```markdown
# Data Protection Impact Assessment

## Processing Overview
- **Purpose**: [Describe the processing activity]
- **Data Types**: [Personal data categories]
- **Data Subjects**: [Who is affected]
- **Recipients**: [Who receives the data]

## Necessity Assessment
- [ ] Is processing necessary for the stated purpose?
- [ ] Could the purpose be achieved with less data?
- [ ] Is the retention period justified?

## Risk Assessment
| Risk | Likelihood | Severity | Mitigation |
|------|------------|----------|------------|
| Data breach | Medium | High | Encryption, access controls |
| Unauthorized access | Low | High | 2FA, audit logs |
| Purpose creep | Medium | Medium | Purpose documentation, training |

## Safeguards
- [ ] Encryption at rest and in transit
- [ ] Access controls and authentication
- [ ] Regular security audits
- [ ] Data minimization applied
- [ ] Retention policies enforced
- [ ] DPO consulted
- [ ] Data subject rights mechanism in place

## Conclusion
Processing is/is not acceptable with proposed safeguards.

Signed: [Data Protection Officer]
Date: [Assessment Date]
```

## Privacy Policy Requirements

**Essential Elements:**
```markdown
# Privacy Policy

## 1. Identity of Controller
Company Name, Address, Contact Information
Data Protection Officer: dpo@company.com

## 2. Data We Collect
- Account data: email, name
- Usage data: pages visited, features used
- Technical data: IP address, browser type

## 3. Legal Basis for Processing
- **Consent**: Marketing communications
- **Contract**: Order fulfillment
- **Legitimate Interest**: Fraud prevention
- **Legal Obligation**: Tax records

## 4. How We Use Your Data
- Provide services you requested
- Improve our products
- Send important updates
- [Be specific, avoid vague statements]

## 5. Data Sharing
- Payment processors (Stripe, PayPal)
- Shipping providers (FedEx, UPS)
- Analytics (Google Analytics)

We do NOT sell your personal data.

## 6. Your Rights
- Right to access your data
- Right to correct inaccuracies
- Right to delete your data
- Right to object to processing
- Right to data portability
- Right to withdraw consent

Contact: privacy@company.com

## 7. Data Retention
- Account data: Until account deletion + 30 days
- Order history: 7 years (legal requirement)
- Marketing data: 1 year or until opt-out

## 8. Security
We use industry-standard security measures including
encryption, secure servers, and regular security audits.

## 9. International Transfers
Data may be transferred to US servers. We use Standard
Contractual Clauses approved by the EU Commission.

## 10. Changes to Policy
Last updated: [Date]
We will notify you of material changes via email.

## 11. Contact
Questions? Contact our Data Protection Officer at dpo@company.com
```

## Incident Response

### Data Breach Response Plan

**Within 72 Hours (GDPR):**
```markdown
1. **Detect & Contain** (0-4 hours)
   - Identify scope of breach
   - Isolate affected systems
   - Prevent further data loss

2. **Assess** (4-24 hours)
   - Determine data types affected
   - Identify number of individuals
   - Assess risk to rights and freedoms
   - Document everything

3. **Notify Authority** (24-72 hours)
   - Report to supervisory authority
   - Include: nature, categories, approximate numbers,
     likely consequences, measures taken

4. **Notify Data Subjects** (ASAP if high risk)
   - Direct communication required
   - Describe breach in clear language
   - Provide recommendations for protection
```

**Breach Notification Template:**
```
Subject: Important Security Notice

Dear [Name],

We are writing to inform you of a data security incident that may
have affected your personal information.

WHAT HAPPENED:
On [date], we discovered that [brief description].

WHAT INFORMATION WAS INVOLVED:
[List specific data types: name, email, etc.]
[List what was NOT involved]

WHAT WE ARE DOING:
- [Immediate actions taken]
- [Ongoing security enhancements]
- [Resources provided to affected individuals]

WHAT YOU CAN DO:
- Change your password immediately
- Monitor your accounts for suspicious activity
- [Specific recommendations]

FOR MORE INFORMATION:
Contact our dedicated hotline: [phone]
Email: security@company.com

We sincerely apologize for this incident and the inconvenience
it may cause.

Sincerely,
[Name, Title]
```

## Compliance Checklist

### GDPR Compliance
- [ ] Lawful basis documented for all processing
- [ ] Privacy policy published and accessible
- [ ] Consent mechanism implements granular controls
- [ ] Data subject rights request process established
- [ ] Records of processing activities maintained
- [ ] Data Protection Officer appointed (if required)
- [ ] DPIA conducted for high-risk processing
- [ ] Data breach notification procedure in place
- [ ] Vendor contracts include data processing agreements
- [ ] International data transfer safeguards implemented
- [ ] Staff training on data protection completed

### CCPA Compliance
- [ ] "Do Not Sell My Personal Information" link on homepage
- [ ] Privacy policy discloses data collection and sales
- [ ] Mechanisms for verifiable consumer requests
- [ ] Process for opt-out requests (48-hour response)
- [ ] Annual report on requests and compliance
- [ ] Service provider agreements updated
- [ ] Notice at collection provided

### HIPAA Compliance
- [ ] Risk assessment completed
- [ ] Security policies and procedures documented
- [ ] Workforce trained on HIPAA requirements
- [ ] Business Associate Agreements signed
- [ ] Access controls and audit trails implemented
- [ ] Encryption for ePHI
- [ ] Breach notification procedures established
- [ ] Contingency plan and disaster recovery

Privacy compliance is an ongoing process, not a one-time checklist. Regularly review and update practices as regulations evolve and your data processing changes.


# Merged section: information-security-manager-iso27001 (from enterprise-communication/information-security-manager-iso27001)
Supporting files from this skill live in `references/information-security-manager-iso27001/`, `scripts/information-security-manager-iso27001/`, `data/information-security-manager-iso27001/` (whichever exist).

# Senior Information Security Manager - ISO 27001/27002 Specialist

Expert-level Information Security Management System (ISMS) implementation and cybersecurity governance with comprehensive knowledge of ISO 27001, ISO 27002, and healthcare-specific security requirements.

## Core ISMS Competencies

### 1. ISO 27001 ISMS Implementation
Design and implement comprehensive Information Security Management Systems aligned with ISO 27001:2022 and healthcare regulatory requirements.

**ISMS Implementation Framework:**
```
ISO 27001 ISMS IMPLEMENTATION
├── ISMS Planning and Design
│   ├── Information security policy development
│   ├── Scope and boundaries definition
│   ├── Risk assessment methodology
│   └── Security objectives establishment
├── Security Risk Management
│   ├── Asset identification and classification
│   ├── Threat and vulnerability assessment
│   ├── Risk analysis and evaluation
│   └── Risk treatment planning
├── Security Controls Implementation
│   ├── ISO 27002 controls selection
│   ├── Technical controls deployment
│   ├── Administrative controls establishment
│   └── Physical controls implementation
└── ISMS Operation and Monitoring
    ├── Security incident management
    ├── Performance monitoring
    ├── Management review
    └── Continuous improvement
```

### 2. Information Security Risk Assessment (ISO 27001 Clause 6.1.2)
Conduct systematic information security risk assessments ensuring comprehensive threat identification and risk treatment.

**Risk Assessment Methodology:**
1. **Asset Identification and Classification**
   - Information assets inventory and valuation
   - System and infrastructure asset mapping
   - Data classification and handling requirements
   - **Decision Point**: Determine asset criticality and protection requirements

2. **Threat and Vulnerability Analysis**
   - **For Healthcare Data**: Follow references/healthcare-threat-modeling.md
   - **For Medical Devices**: Follow references/device-security-assessment.md
   - **For Cloud Services**: Follow references/cloud-security-evaluation.md
   - Threat landscape analysis and modeling

3. **Risk Analysis and Evaluation**
   - Risk likelihood and impact assessment
   - Risk level determination and prioritization
   - Risk acceptability evaluation
   - Risk treatment option analysis

### 3. ISO 27002 Security Controls Implementation
Implement comprehensive security controls framework ensuring systematic information security protection.

**Security Controls Categories:**
```
ISO 27002:2022 CONTROLS FRAMEWORK
├── Organizational Controls (5.1-5.37)
│   ├── Information security policies
│   ├── Organization of information security
│   ├── Human resource security
│   └── Supplier relationship security
├── People Controls (6.1-6.8)
│   ├── Screening and terms of employment
│   ├── Information security awareness
│   ├── Disciplinary processes
│   └── Remote working guidelines
├── Physical Controls (7.1-7.14)
│   ├── Physical security perimeters
│   ├── Equipment protection
│   ├── Secure disposal and reuse
│   └── Clear desk and screen policies
└── Technological Controls (8.1-8.34)
    ├── Access control management
    ├── Cryptography and key management
    ├── Systems security
    ├── Network security controls
    ├── Application security
    ├── Secure development
    └── Supplier relationship security
```

### 4. Healthcare-Specific Security Requirements
Implement security measures addressing unique healthcare and medical device requirements.

**Healthcare Security Framework:**
- **HIPAA Technical Safeguards**: Access control, audit controls, integrity, transmission security
- **Medical Device Cybersecurity**: FDA cybersecurity guidance and IEC 62304 integration
- **Clinical Data Protection**: Clinical trial data security and patient privacy
- **Interoperability Security**: HL7 FHIR and healthcare standard security

## Advanced Information Security Applications

### Medical Device Cybersecurity Management
Implement comprehensive cybersecurity measures for connected medical devices and IoT healthcare systems.

**Device Cybersecurity Framework:**
1. **Device Security Assessment**
   - Security architecture review and validation
   - Vulnerability assessment and penetration testing
   - Threat modeling and attack surface analysis
   - **Decision Point**: Determine device security classification and controls

2. **Security Controls Implementation**
   - **Device Authentication**: Multi-factor authentication and device identity
   - **Data Protection**: Encryption at rest and in transit
   - **Network Security**: Segmentation and monitoring
   - **Update Management**: Secure software update mechanisms

3. **Security Monitoring and Response**
   - Security event monitoring and SIEM integration
   - Incident response and forensic capabilities
   - Threat intelligence and vulnerability management
   - Security awareness and training programs

### Cloud Security Management
Ensure comprehensive security for cloud-based healthcare systems and SaaS applications.

**Cloud Security Strategy:**
- **Cloud Security Assessment**: Cloud service provider evaluation and due diligence
- **Data Residency and Sovereignty**: Regulatory compliance and data location requirements
- **Shared Responsibility Model**: Cloud provider and customer security responsibilities
- **Cloud Access Security**: Identity and access management for cloud services

### Privacy and Data Protection Integration
Integrate information security with privacy and data protection requirements ensuring comprehensive data governance.

**Privacy-Security Integration:**
- **Privacy by Design**: Security controls supporting privacy requirements
- **Data Minimization**: Security measures for data collection and retention limits
- **Data Subject Rights**: Technical measures supporting privacy rights exercise
- **Cross-Border Data Transfer**: Security controls for international data transfers

## ISMS Governance and Operations

### Information Security Policy Framework
Establish comprehensive information security policies ensuring organizational security governance.

**Policy Framework Structure:**
- **Information Security Policy**: Top-level security commitment and direction
- **Acceptable Use Policy**: System and data usage guidelines
- **Access Control Policy**: User access and privilege management
- **Incident Response Policy**: Security incident handling procedures
- **Business Continuity Policy**: Security aspects of continuity planning

### Security Awareness and Training Program
Develop and maintain comprehensive security awareness programs ensuring organizational security culture.

**Training Program Components:**
- **General Security Awareness**: All-staff security training and awareness
- **Role-Based Security Training**: Specialized training for specific roles
- **Incident Response Training**: Security incident handling and escalation
- **Regular Security Updates**: Ongoing security communication and updates

### Security Incident Management (ISO 27001 Clause 8.2.3)
Implement robust security incident management processes ensuring effective incident response and recovery.

**Incident Management Process:**
1. **Incident Detection and Reporting**
2. **Incident Classification and Prioritization**
3. **Incident Investigation and Analysis**
4. **Incident Response and Containment**
5. **Recovery and Post-Incident Activities**
6. **Lessons Learned and Improvement**

## ISMS Performance and Compliance

### Security Metrics and KPIs
Monitor comprehensive security performance indicators ensuring ISMS effectiveness and continuous improvement.

**Security Performance Dashboard:**
- **Security Control Effectiveness**: Control implementation and performance metrics
- **Incident Management Performance**: Response times, resolution rates, impact assessment
- **Compliance Status**: Regulatory and standard compliance verification
- **Risk Management Effectiveness**: Risk treatment success and residual risk levels
- **Security Awareness Metrics**: Training completion, phishing simulation results

### Internal Security Auditing
Conduct systematic internal security audits ensuring ISMS compliance and effectiveness.

**Security Audit Program:**
- **Risk-Based Audit Planning**: Audit scope and frequency based on risk assessment
- **Technical Security Testing**: Vulnerability assessments and penetration testing
- **Compliance Auditing**: ISO 27001 and regulatory requirement verification
- **Process Auditing**: ISMS process effectiveness evaluation

### Management Review and Continuous Improvement
Lead management review processes ensuring systematic ISMS evaluation and strategic security planning.

**Management Review Framework:**
- **Security Performance Review**: Metrics analysis and trend identification
- **Risk Assessment Updates**: Risk landscape changes and impact evaluation
- **Compliance Status Review**: Regulatory and certification compliance assessment
- **Security Investment Planning**: Security technology and resource allocation
- **Strategic Security Planning**: Security strategy alignment with business objectives

## Regulatory and Certification Management

### ISO 27001 Certification Management
Oversee ISO 27001 certification processes ensuring successful certification and maintenance.

**Certification Management:**
- **Pre-certification Readiness**: Gap analysis and remediation planning
- **Certification Audit Management**: Stage 1 and Stage 2 audit coordination
- **Surveillance Audit Preparation**: Ongoing compliance and improvement demonstration
- **Certification Maintenance**: Certificate renewal and scope management

### Regulatory Security Compliance
Ensure comprehensive compliance with healthcare security regulations and standards.

**Regulatory Compliance Framework:**
- **HIPAA Security Rule**: Technical, administrative, and physical safeguards
- **GDPR Security Requirements**: Technical and organizational measures
- **FDA Cybersecurity Guidance**: Medical device cybersecurity compliance
- **NIST Cybersecurity Framework**: Cybersecurity risk management integration

## Resources

### scripts/
- `isms-performance-dashboard.py`: Comprehensive ISMS metrics monitoring and reporting
- `security-risk-assessment.py`: Automated security risk assessment and documentation
- `compliance-monitoring.py`: Regulatory and standard compliance tracking
- `incident-response-automation.py`: Security incident workflow automation

### references/
- `iso27001-implementation-guide.md`: Complete ISO 27001 ISMS implementation framework
- `iso27002-controls-library.md`: Comprehensive security controls implementation guidance
- `healthcare-threat-modeling.md`: Healthcare-specific threat assessment methodologies
- `device-security-assessment.md`: Medical device cybersecurity evaluation frameworks
- `cloud-security-evaluation.md`: Cloud service security assessment criteria

### assets/
- `isms-templates/`: Information security policy, procedure, and documentation templates
- `risk-assessment-tools/`: Security risk assessment worksheets and calculation tools
- `audit-checklists/`: ISO 27001 and security compliance audit checklists
- `training-materials/`: Information security awareness and training programs
