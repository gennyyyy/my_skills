---
name: security
description: Comprehensive security engineering skill for application security, penetration testing, security architecture, and compliance auditing. Includes security assessment tools, threat modeling, crypto implementation, and security automation. Use when designing security architecture, conducting penetration tests, implementing cryptography, or performing security audits. Comprehensive SecOps skill for application security, vulnerability management, compliance, and secure development practices. Includes security scanning, vulnerability assessment, compliance checking, and security automation. Use when implementing security controls, conducting security audits, responding to vulnerabilities, or ensuring compliance requirements. Comprehensive security auditing workflow covering web application testing, API security, penetration testing, vulnerability scanning, and security hardening. Advanced vulnerability analysis principles. OWASP 2025, Supply Chain Security, attack surface mapping, risk prioritization. Perform language and framework specific security best-practice reviews and suggest improvements. Trigger only when the user explicitly requests security best practices guidance, a security
---


# Senior Security

Complete toolkit for senior security with modern tools and best practices.

## Quick Start

### Main Capabilities

This skill provides three core capabilities through automated scripts:

```bash
# Script 1: Threat Modeler
python scripts/threat_modeler.py [options]

# Script 2: Security Auditor
python scripts/security_auditor.py [options]

# Script 3: Pentest Automator
python scripts/pentest_automator.py [options]
```

## Core Capabilities

### 1. Threat Modeler

Automated tool for threat modeler tasks.

**Features:**
- Automated scaffolding
- Best practices built-in
- Configurable templates
- Quality checks

**Usage:**
```bash
python scripts/threat_modeler.py <project-path> [options]
```

### 2. Security Auditor

Comprehensive analysis and optimization tool.

**Features:**
- Deep analysis
- Performance metrics
- Recommendations
- Automated fixes

**Usage:**
```bash
python scripts/security_auditor.py <target-path> [--verbose]
```

### 3. Pentest Automator

Advanced tooling for specialized tasks.

**Features:**
- Expert-level automation
- Custom configurations
- Integration ready
- Production-grade output

**Usage:**
```bash
python scripts/pentest_automator.py [arguments] [options]
```

## Reference Documentation

### Security Architecture Patterns

Comprehensive guide available in `references/security_architecture_patterns.md`:

- Detailed patterns and practices
- Code examples
- Best practices
- Anti-patterns to avoid
- Real-world scenarios

### Penetration Testing Guide

Complete workflow documentation in `references/penetration_testing_guide.md`:

- Step-by-step processes
- Optimization strategies
- Tool integrations
- Performance tuning
- Troubleshooting guide

### Cryptography Implementation

Technical reference guide in `references/cryptography_implementation.md`:

- Technology stack details
- Configuration examples
- Integration patterns
- Security considerations
- Scalability guidelines

## Tech Stack

**Languages:** TypeScript, JavaScript, Python, Go, Swift, Kotlin
**Frontend:** React, Next.js, React Native, Flutter
**Backend:** Node.js, Express, GraphQL, REST APIs
**Database:** PostgreSQL, Prisma, NeonDB, Supabase
**DevOps:** Docker, Kubernetes, Terraform, GitHub Actions, CircleCI
**Cloud:** AWS, GCP, Azure

## Development Workflow

### 1. Setup and Configuration

```bash
# Install dependencies
npm install
# or
pip install -r requirements.txt

# Configure environment
cp .env.example .env
```

### 2. Run Quality Checks

```bash
# Use the analyzer script
python scripts/security_auditor.py .

# Review recommendations
# Apply fixes
```

### 3. Implement Best Practices

Follow the patterns and practices documented in:
- `references/security_architecture_patterns.md`
- `references/penetration_testing_guide.md`
- `references/cryptography_implementation.md`

## Best Practices Summary

### Code Quality
- Follow established patterns
- Write comprehensive tests
- Document decisions
- Review regularly

### Performance
- Measure before optimizing
- Use appropriate caching
- Optimize critical paths
- Monitor in production

### Security
- Validate all inputs
- Use parameterized queries
- Implement proper authentication
- Keep dependencies updated

### Maintainability
- Write clear code
- Use consistent naming
- Add helpful comments
- Keep it simple

## Common Commands

```bash
# Development
npm run dev
npm run build
npm run test
npm run lint

# Analysis
python scripts/security_auditor.py .
python scripts/pentest_automator.py --analyze

# Deployment
docker build -t app:latest .
docker-compose up -d
kubectl apply -f k8s/
```

## Troubleshooting

### Common Issues

Check the comprehensive troubleshooting section in `references/cryptography_implementation.md`.

### Getting Help

- Review reference documentation
- Check script output messages
- Consult tech stack documentation
- Review error logs

## Resources

- Pattern Reference: `references/security_architecture_patterns.md`
- Workflow Guide: `references/penetration_testing_guide.md`
- Technical Guide: `references/cryptography_implementation.md`
- Tool Scripts: `scripts/` directory


---

<!-- merged-in: development/senior-secops, security/security-audit, security/vulnerability-scanner, security/security-best-practices, security/top-web-vulnerabilities, security/api-security-best-practices -->


# Merged section: senior-secops (from development/senior-secops)
Supporting files from this skill live in `references/senior-secops/`, `scripts/senior-secops/`, `data/senior-secops/` (whichever exist).

# Senior Secops

Complete toolkit for senior secops with modern tools and best practices.

## Quick Start

### Main Capabilities

This skill provides three core capabilities through automated scripts:

```bash
# Script 1: Security Scanner
python scripts/security_scanner.py [options]

# Script 2: Vulnerability Assessor
python scripts/vulnerability_assessor.py [options]

# Script 3: Compliance Checker
python scripts/compliance_checker.py [options]
```

## Core Capabilities

### 1. Security Scanner

Automated tool for security scanner tasks.

**Features:**
- Automated scaffolding
- Best practices built-in
- Configurable templates
- Quality checks

**Usage:**
```bash
python scripts/security_scanner.py <project-path> [options]
```

### 2. Vulnerability Assessor

Comprehensive analysis and optimization tool.

**Features:**
- Deep analysis
- Performance metrics
- Recommendations
- Automated fixes

**Usage:**
```bash
python scripts/vulnerability_assessor.py <target-path> [--verbose]
```

### 3. Compliance Checker

Advanced tooling for specialized tasks.

**Features:**
- Expert-level automation
- Custom configurations
- Integration ready
- Production-grade output

**Usage:**
```bash
python scripts/compliance_checker.py [arguments] [options]
```

## Reference Documentation

### Security Standards

Comprehensive guide available in `references/security_standards.md`:

- Detailed patterns and practices
- Code examples
- Best practices
- Anti-patterns to avoid
- Real-world scenarios

### Vulnerability Management Guide

Complete workflow documentation in `references/vulnerability_management_guide.md`:

- Step-by-step processes
- Optimization strategies
- Tool integrations
- Performance tuning
- Troubleshooting guide

### Compliance Requirements

Technical reference guide in `references/compliance_requirements.md`:

- Technology stack details
- Configuration examples
- Integration patterns
- Security considerations
- Scalability guidelines

## Tech Stack

**Languages:** TypeScript, JavaScript, Python, Go, Swift, Kotlin
**Frontend:** React, Next.js, React Native, Flutter
**Backend:** Node.js, Express, GraphQL, REST APIs
**Database:** PostgreSQL, Prisma, NeonDB, Supabase
**DevOps:** Docker, Kubernetes, Terraform, GitHub Actions, CircleCI
**Cloud:** AWS, GCP, Azure

## Development Workflow

### 1. Setup and Configuration

```bash
# Install dependencies
npm install
# or
pip install -r requirements.txt

# Configure environment
cp .env.example .env
```

### 2. Run Quality Checks

```bash
# Use the analyzer script
python scripts/vulnerability_assessor.py .

# Review recommendations
# Apply fixes
```

### 3. Implement Best Practices

Follow the patterns and practices documented in:
- `references/security_standards.md`
- `references/vulnerability_management_guide.md`
- `references/compliance_requirements.md`

## Best Practices Summary

### Code Quality
- Follow established patterns
- Write comprehensive tests
- Document decisions
- Review regularly

### Performance
- Measure before optimizing
- Use appropriate caching
- Optimize critical paths
- Monitor in production

### Security
- Validate all inputs
- Use parameterized queries
- Implement proper authentication
- Keep dependencies updated

### Maintainability
- Write clear code
- Use consistent naming
- Add helpful comments
- Keep it simple

## Common Commands

```bash
# Development
npm run dev
npm run build
npm run test
npm run lint

# Analysis
python scripts/vulnerability_assessor.py .
python scripts/compliance_checker.py --analyze

# Deployment
docker build -t app:latest .
docker-compose up -d
kubectl apply -f k8s/
```

## Troubleshooting

### Common Issues

Check the comprehensive troubleshooting section in `references/compliance_requirements.md`.

### Getting Help

- Review reference documentation
- Check script output messages
- Consult tech stack documentation
- Review error logs

## Resources

- Pattern Reference: `references/security_standards.md`
- Workflow Guide: `references/vulnerability_management_guide.md`
- Technical Guide: `references/compliance_requirements.md`
- Tool Scripts: `scripts/` directory


# Merged section: security-audit (from security/security-audit)
Supporting files from this skill live in `references/security-audit/`, `scripts/security-audit/`, `data/security-audit/` (whichever exist).

# Security Auditing Workflow Bundle

## Overview

Comprehensive security auditing workflow for web applications, APIs, and infrastructure. This bundle orchestrates skills for penetration testing, vulnerability assessment, security scanning, and remediation.

## When to Use This Workflow

Use this workflow when:
- Performing security audits on web applications
- Testing API security
- Conducting penetration tests
- Scanning for vulnerabilities
- Hardening application security
- Compliance security assessments

## Workflow Phases

### Phase 1: Reconnaissance

#### Skills to Invoke
- `scanning-tools` - Security scanning
- `shodan-reconnaissance` - Shodan searches
- `top-web-vulnerabilities` - OWASP Top 10

#### Actions
1. Identify target scope
2. Gather intelligence
3. Map attack surface
4. Identify technologies
5. Document findings

#### Copy-Paste Prompts
```
Use @scanning-tools to perform initial reconnaissance
```

```
Use @shodan-reconnaissance to find exposed services
```

### Phase 2: Vulnerability Scanning

#### Skills to Invoke
- `vulnerability-scanner` - Vulnerability analysis
- `security-scanning-security-sast` - Static analysis
- `security-scanning-security-dependencies` - Dependency scanning

#### Actions
1. Run automated scanners
2. Perform static analysis
3. Scan dependencies
4. Identify misconfigurations
5. Document vulnerabilities

#### Copy-Paste Prompts
```
Use @vulnerability-scanner to scan for OWASP Top 10 vulnerabilities
```

```
Use @security-scanning-security-dependencies to audit dependencies
```

### Phase 3: Web Application Testing

#### Skills to Invoke
- `top-web-vulnerabilities` - OWASP vulnerabilities
- `sql-injection-testing` - SQL injection
- `xss-html-injection` - XSS testing
- `broken-authentication` - Authentication testing
- `idor-testing` - IDOR testing
- `file-path-traversal` - Path traversal
- `burp-suite-testing` - Burp Suite testing

#### Actions
1. Test for injection flaws
2. Test authentication mechanisms
3. Test session management
4. Test access controls
5. Test input validation
6. Test security headers

#### Copy-Paste Prompts
```
Use @sql-injection-testing to test for SQL injection vulnerabilities
```

```
Use @xss-html-injection to test for cross-site scripting
```

```
Use @broken-authentication to test authentication security
```

### Phase 4: API Security Testing

#### Skills to Invoke
- `api-fuzzing-bug-bounty` - API fuzzing
- `api-security-best-practices` - API security

#### Actions
1. Enumerate API endpoints
2. Test authentication/authorization
3. Test rate limiting
4. Test input validation
5. Test error handling
6. Document API vulnerabilities

#### Copy-Paste Prompts
```
Use @api-fuzzing-bug-bounty to fuzz API endpoints
```

### Phase 5: Penetration Testing

#### Skills to Invoke
- `pentest-commands` - Penetration testing commands
- `pentest-checklist` - Pentest planning
- `ethical-hacking-methodology` - Ethical hacking
- `metasploit-framework` - Metasploit

#### Actions
1. Plan penetration test
2. Execute attack scenarios
3. Exploit vulnerabilities
4. Document proof of concept
5. Assess impact

#### Copy-Paste Prompts
```
Use @pentest-checklist to plan penetration test
```

```
Use @pentest-commands to execute penetration testing
```

### Phase 6: Security Hardening

#### Skills to Invoke
- `security-scanning-security-hardening` - Security hardening
- `auth-implementation-patterns` - Authentication
- `api-security-best-practices` - API security

#### Actions
1. Implement security controls
2. Configure security headers
3. Set up authentication
4. Implement authorization
5. Configure logging
6. Apply patches

#### Copy-Paste Prompts
```
Use @security-scanning-security-hardening to harden application security
```

### Phase 7: Reporting

#### Skills to Invoke
- `reporting-standards` - Security reporting

#### Actions
1. Document findings
2. Assess risk levels
3. Provide remediation steps
4. Create executive summary
5. Generate technical report

## Security Testing Checklist

### OWASP Top 10
- [ ] Injection (SQL, NoSQL, OS, LDAP)
- [ ] Broken Authentication
- [ ] Sensitive Data Exposure
- [ ] XML External Entities (XXE)
- [ ] Broken Access Control
- [ ] Security Misconfiguration
- [ ] Cross-Site Scripting (XSS)
- [ ] Insecure Deserialization
- [ ] Using Components with Known Vulnerabilities
- [ ] Insufficient Logging & Monitoring

### API Security
- [ ] Authentication mechanisms
- [ ] Authorization checks
- [ ] Rate limiting
- [ ] Input validation
- [ ] Error handling
- [ ] Security headers

## Quality Gates

- [ ] All planned tests executed
- [ ] Vulnerabilities documented
- [ ] Proof of concepts captured
- [ ] Risk assessments completed
- [ ] Remediation steps provided
- [ ] Report generated

## Related Workflow Bundles

- `development` - Secure development practices
- `wordpress` - WordPress security
- `cloud-devops` - Cloud security
- `testing-qa` - Security testing


# Merged section: vulnerability-scanner (from security/vulnerability-scanner)
Supporting files from this skill live in `references/vulnerability-scanner/`, `scripts/vulnerability-scanner/`, `data/vulnerability-scanner/` (whichever exist).

# Vulnerability Scanner

> Think like an attacker, defend like an expert. 2025 threat landscape awareness.

## 🔧 Runtime Scripts

**Execute for automated validation:**

| Script | Purpose | Usage |
|--------|---------|-------|
| `scripts/security_scan.py` | Validate security principles applied | `python scripts/security_scan.py <project_path>` |

## 📋 Reference Files

| File | Purpose |
|------|---------|
| [checklists.md](checklists.md) | OWASP Top 10, Auth, API, Data protection checklists |

---

## 1. Security Expert Mindset

### Core Principles

| Principle | Application |
|-----------|-------------|
| **Assume Breach** | Design as if attacker already inside |
| **Zero Trust** | Never trust, always verify |
| **Defense in Depth** | Multiple layers, no single point |
| **Least Privilege** | Minimum required access only |
| **Fail Secure** | On error, deny access |

### Threat Modeling Questions

Before scanning, ask:
1. What are we protecting? (Assets)
2. Who would attack? (Threat actors)
3. How would they attack? (Attack vectors)
4. What's the impact? (Business risk)

---

## 2. OWASP Top 10:2025

### Risk Categories

| Rank | Category | Think About |
|------|----------|-------------|
| **A01** | Broken Access Control | Who can access what? IDOR, SSRF |
| **A02** | Security Misconfiguration | Defaults, headers, exposed services |
| **A03** | Software Supply Chain 🆕 | Dependencies, CI/CD, build integrity |
| **A04** | Cryptographic Failures | Weak crypto, exposed secrets |
| **A05** | Injection | User input → system commands |
| **A06** | Insecure Design | Flawed architecture |
| **A07** | Authentication Failures | Session, credential management |
| **A08** | Integrity Failures | Unsigned updates, tampered data |
| **A09** | Logging & Alerting | Blind spots, no monitoring |
| **A10** | Exceptional Conditions 🆕 | Error handling, fail-open states |

### 2025 Key Changes

```
2021 → 2025 Shifts:
├── SSRF merged into A01 (Access Control)
├── A02 elevated (Cloud/Container configs)
├── A03 NEW: Supply Chain (major focus)
├── A10 NEW: Exceptional Conditions
└── Focus shift: Root causes > Symptoms
```

---

## 3. Supply Chain Security (A03)

### Attack Surface

| Vector | Risk | Question to Ask |
|--------|------|-----------------|
| **Dependencies** | Malicious packages | Do we audit new deps? |
| **Lock files** | Integrity attacks | Are they committed? |
| **Build pipeline** | CI/CD compromise | Who can modify? |
| **Registry** | Typosquatting | Verified sources? |

### Defense Principles

- Verify package integrity (checksums)
- Pin versions, audit updates
- Use private registries for critical deps
- Sign and verify artifacts

---

## 4. Attack Surface Mapping

### What to Map

| Category | Elements |
|----------|----------|
| **Entry Points** | APIs, forms, file uploads |
| **Data Flows** | Input → Process → Output |
| **Trust Boundaries** | Where auth/authz checked |
| **Assets** | Secrets, PII, business data |

### Prioritization Matrix

```
Risk = Likelihood × Impact

High Impact + High Likelihood → CRITICAL
High Impact + Low Likelihood  → HIGH
Low Impact + High Likelihood  → MEDIUM
Low Impact + Low Likelihood   → LOW
```

---

## 5. Risk Prioritization

### CVSS + Context

| Factor | Weight | Question |
|--------|--------|----------|
| **CVSS Score** | Base severity | How severe is the vuln? |
| **EPSS Score** | Exploit likelihood | Is it being exploited? |
| **Asset Value** | Business context | What's at risk? |
| **Exposure** | Attack surface | Internet-facing? |

### Prioritization Decision Tree

```
Is it actively exploited (EPSS >0.5)?
├── YES → CRITICAL: Immediate action
└── NO → Check CVSS
         ├── CVSS ≥9.0 → HIGH
         ├── CVSS 7.0-8.9 → Consider asset value
         └── CVSS <7.0 → Schedule for later
```

---

## 6. Exceptional Conditions (A10 - New)

### Fail-Open vs Fail-Closed

| Scenario | Fail-Open (BAD) | Fail-Closed (GOOD) |
|----------|-----------------|---------------------|
| Auth error | Allow access | Deny access |
| Parsing fails | Accept input | Reject input |
| Timeout | Retry forever | Limit + abort |

### What to Check

- Exception handlers that catch-all and ignore
- Missing error handling on security operations
- Race conditions in auth/authz
- Resource exhaustion scenarios

---

## 7. Scanning Methodology

### Phase-Based Approach

```
1. RECONNAISSANCE
   └── Understand the target
       ├── Technology stack
       ├── Entry points
       └── Data flows

2. DISCOVERY
   └── Identify potential issues
       ├── Configuration review
       ├── Dependency analysis
       └── Code pattern search

3. ANALYSIS
   └── Validate and prioritize
       ├── False positive elimination
       ├── Risk scoring
       └── Attack chain mapping

4. REPORTING
   └── Actionable findings
       ├── Clear reproduction steps
       ├── Business impact
       └── Remediation guidance
```

---

## 8. Code Pattern Analysis

### High-Risk Patterns

| Pattern | Risk | Look For |
|---------|------|----------|
| **String concat in queries** | Injection | `"SELECT * FROM " + user_input` |
| **Dynamic code execution** | RCE | `eval()`, `exec()`, `Function()` |
| **Unsafe deserialization** | RCE | `pickle.loads()`, `unserialize()` |
| **Path manipulation** | Traversal | User input in file paths |
| **Disabled security** | Various | `verify=False`, `--insecure` |

### Secret Patterns

| Type | Indicators |
|------|-----------|
| API Keys | `api_key`, `apikey`, high entropy |
| Tokens | `token`, `bearer`, `jwt` |
| Credentials | `password`, `secret`, `key` |
| Cloud | `AWS_`, `AZURE_`, `GCP_` prefixes |

---

## 9. Cloud Security Considerations

### Shared Responsibility

| Layer | You Own | Provider Owns |
|-------|---------|---------------|
| Data | ✅ | ❌ |
| Application | ✅ | ❌ |
| OS/Runtime | Depends | Depends |
| Infrastructure | ❌ | ✅ |

### Cloud-Specific Checks

- IAM: Least privilege applied?
- Storage: Public buckets?
- Network: Security groups tightened?
- Secrets: Using secrets manager?

---

## 10. Anti-Patterns

| ❌ Don't | ✅ Do |
|----------|-------|
| Scan without understanding | Map attack surface first |
| Alert on every CVE | Prioritize by exploitability + asset |
| Ignore false positives | Maintain verified baseline |
| Fix symptoms only | Address root causes |
| Scan once before deploy | Continuous scanning |
| Trust third-party deps blindly | Verify integrity, audit code |

---

## 11. Reporting Principles

### Finding Structure

Each finding should answer:
1. **What?** - Clear vulnerability description
2. **Where?** - Exact location (file, line, endpoint)
3. **Why?** - Root cause explanation
4. **Impact?** - Business consequence
5. **How to fix?** - Specific remediation

### Severity Classification

| Severity | Criteria |
|----------|----------|
| **Critical** | RCE, auth bypass, mass data exposure |
| **High** | Data exposure, privilege escalation |
| **Medium** | Limited scope, requires conditions |
| **Low** | Informational, best practice |

---

> **Remember:** Vulnerability scanning finds issues. Expert thinking prioritizes what matters. Always ask: "What would an attacker do with this?"


# Merged section: security-best-practices (from security/security-best-practices)
Supporting files from this skill live in `references/security-best-practices/`, `scripts/security-best-practices/`, `data/security-best-practices/` (whichever exist).

# Security Best Practices

## Overview

This skill provides a description of how to identify the language and frameworks used by the current context, and then to load information from this skill's references directory about the security best practices for this language and or frameworks.

This information, if present, can be used to write new secure by default code, or to passively detect major issues within existing code, or (if requested by the user) provide a vulnerability report and suggest fixes.

## Workflow

The initial step for this skill is to identify ALL languages and ALL frameworks which you are being asked to use or already exist in the scope of the project you are working in. Focus on the primary core frameworks. Often you will want to identify both frontend and backend languages and frameworks.

Then check this skill's references directory to see if there are any relevant documentation for the language and or frameworks. Make sure you read ALL reference files which relate to the specific framework or language. The format of the filenames is `<language>-<framework>-<stack>-security.md`. You should also check if there is a `<language>-general-<stack>-security.md` which is agnostic to the framework you may be using.

If working on a web application which includes a frontend and a backend, make sure you have checked for reference documents for BOTH the frontend and backend!

If you are asked to make a web app which will include both a frontend and backend, but the frontend framework is not specified, also check out `javascript-general-web-frontend-security.md`. It is important that you understand how to secure both the frontend and backend.

If no relevant information is available in the skill's references directory, think a little bit about what you know about the language, the framework, and all well known security best practices for it. If you are unsure you can try to search online for documentation on security best practices.

From there it can operate in a few ways.

1. The primary mode is to just use the information to write secure by default code from this point forward. This is useful for starting a new project or when writing new code.

2. The secondary mode is to passively detect vulnerabilities while working in the project and writing code for the user. Critical or very important vulnerabilities or major issues going against security guidance can be flagged and the user can be told about them. This passive mode should focus on the largest impact vulnerabilities and secure defaults.

3. The user can ask for a security report or to improve the security of the codebase. In this case a full report should be produced describe anyways the project fails to follow security best practices guidance. The report should be prioritized and have clear sections of severity and urgency. Then offer to start working on fixes for these issues. See #fixes below.

## Workflow Decision Tree

- If the language/framework is unclear, inspect the repo to determine it and list your evidence.
- If matching guidance exists in `references/`, load only the relevant files and follow their instructions.
- If no matching guidance exists, consider if you know any well known security best practices for the chosen language and or frameworks, but if asked to generate a report, let the user know that concrete guidance is not available (you can still generate the report or detect for sure critical vulnerabilities)

# Overrides

While these references contain the security best practices for languages and frameworks, customers may have cases where they need to bypass or override these practices. Pay attention to specific rules and instructions in the project's documentation and prompt files which may require you to override certain best practices. When overriding a best practice, you MAY report it to the user, but do not fight with them. If a security best practice needs to be bypassed / ignored for some project specific reason, you can also suggest to add documentation about this to the project so it is clear why the best practice is not being followed and to follow that bypass in the future.

# Report Format

When producing a report, you should write the report as a markdown file in `security_best_practices_report.md` or some other location if provided by the user. You can ask the user where they would like the report to be written to.

The report should have a short executive summary at the top.

The report should be clearly delineated into multiple sections based on severity of the vulnerability. The report should focus on the most critical findings as these have the highest impact for the user. All findings should be noted with an numeric ID to make them easier to reference.

For critical findings include a one sentence impact statement.

Once the report is written, also report it to the user directly, although you may be less verbose. You can offer to explain any of the findings or the reasons behind the security best practices guidance if the user wants more info on any findings.

Important: When referencing code in the report, make sure to find and include line numbers for the code you are referencing.

After you write the report file, summarize the findings to the user.

Also tell the user where the final report was written to

# Fixes

If you produced a report, let the user read the report and ask to begin performing fixes.

If you passively found a critical finding, notify the user and ask if they would like you to fix this finding.

When producing fixes, focus on fixing a single finding at a time. The fixes should have concise clear comments explaining that the new code is based on the specific security best practice, and perhaps a very short reason why it would be dangerous to not do it in this way.

Always consider if the changes you want to make will impact the functionality of the user's code. Consider if the changes may cause regressions with how the project works currently. It is often the case that insecure code is relied on for other reasons (and this is why insecure code lives on for so long). Avoid breaking the user's project as this may make them not want to apply security fixes in the future. It is better to write a well thought out, well informed by the rest of the project, fix, then a quick slapdash change.

Always follow any normal change or commit flow the user has configured. If making git commits, provide clear commit messages explaining this is to align with security best practices. Try to avoid bunching a number of unrelated findings into a single commit.

Always follow any normal testing flows the user has configured (if any) to confirm that your changes are not introducing regressions. Consider the second order impacts the changes may have and inform the user before making them if there are any.

# General Security Advice

Below is a few bits of secure coding advice that applies to almost any language or framework.

### Avoid Using Incrementing IDs for Public IDs of Resources

When assigning an ID for some resource, which will then be used by exposed to the internet, avoid using small auto-incrementing IDs. Use longer, random UUID4 or random hex string instead. This will prevent users from learning the quantity of a resource and being able to guess resource IDs.

### A note on TLS

While TLS is important for production deployments, most development work will be with TLS disabled or provided by some out-of-scope TLS proxy. Due to this, be very careful about not reporting lack of TLS as a security issue. Also be very careful around use of "secure" cookies. They should only be set if the application will actually be over TLS. If they are set on non-TLS applications (such as when deployed for local dev or testing), it will break the application. You can provide a env or other flag to override setting secure as a way to keep it off until on a TLS production deployment. Additionally avoid recommending HSTS. It is dangerous to use without full understanding of the lasting impacts (can cause major outages and user lockout) and it is not generally recommended for the scope of projects being reviewed by codex.


# Merged section: top-web-vulnerabilities (from security/top-web-vulnerabilities)
Supporting files from this skill live in `references/top-web-vulnerabilities/`, `scripts/top-web-vulnerabilities/`, `data/top-web-vulnerabilities/` (whichever exist).

# Top 100 Web Vulnerabilities Reference

## Purpose

Provide a comprehensive, structured reference for the 100 most critical web application vulnerabilities organized by category. This skill enables systematic vulnerability identification, impact assessment, and remediation guidance across the full spectrum of web security threats. Content organized into 15 major vulnerability categories aligned with industry standards and real-world attack patterns.

## Prerequisites

- Basic understanding of web application architecture (client-server model, HTTP protocol)
- Familiarity with common web technologies (HTML, JavaScript, SQL, XML, APIs)
- Understanding of authentication and authorization concepts
- Access to web application security testing tools (Burp Suite, OWASP ZAP)
- Knowledge of secure coding principles recommended

## Outputs and Deliverables

- Complete vulnerability catalog with definitions, root causes, impacts, and mitigations
- Category-based vulnerability groupings for systematic assessment
- Quick reference for security testing and remediation
- Foundation for vulnerability assessment checklists and security policies

---

## Core Workflow

### Phase 1: Injection Vulnerabilities Assessment

Evaluate injection attack vectors targeting data processing components:

**SQL Injection (1)**
- Definition: Malicious SQL code inserted into input fields to manipulate database queries
- Root Cause: Lack of input validation, improper use of parameterized queries
- Impact: Unauthorized data access, data manipulation, database compromise
- Mitigation: Use parameterized queries/prepared statements, input validation, least privilege database accounts

**Cross-Site Scripting - XSS (2)**
- Definition: Injection of malicious scripts into web pages viewed by other users
- Root Cause: Insufficient output encoding, lack of input sanitization
- Impact: Session hijacking, credential theft, website defacement
- Mitigation: Output encoding, Content Security Policy (CSP), input sanitization

**Command Injection (5, 11)**
- Definition: Execution of arbitrary system commands through vulnerable applications
- Root Cause: Unsanitized user input passed to system shells
- Impact: Full system compromise, data exfiltration, lateral movement
- Mitigation: Avoid shell execution, whitelist valid commands, strict input validation

**XML Injection (6), LDAP Injection (7), XPath Injection (8)**
- Definition: Manipulation of XML/LDAP/XPath queries through malicious input
- Root Cause: Improper input handling in query construction
- Impact: Data exposure, authentication bypass, information disclosure
- Mitigation: Input validation, parameterized queries, escape special characters

**Server-Side Template Injection - SSTI (13)**
- Definition: Injection of malicious code into template engines
- Root Cause: User input embedded directly in template expressions
- Impact: Remote code execution, server compromise
- Mitigation: Sandbox template engines, avoid user input in templates, strict input validation

### Phase 2: Authentication and Session Security

Assess authentication mechanism weaknesses:

**Session Fixation (14)**
- Definition: Attacker sets victim's session ID before authentication
- Root Cause: Session ID not regenerated after login
- Impact: Session hijacking, unauthorized account access
- Mitigation: Regenerate session ID on authentication, use secure session management

**Brute Force Attack (15)**
- Definition: Systematic password guessing using automated tools
- Root Cause: Lack of account lockout, rate limiting, or CAPTCHA
- Impact: Unauthorized access, credential compromise
- Mitigation: Account lockout policies, rate limiting, MFA, CAPTCHA

**Session Hijacking (16)**
- Definition: Attacker steals or predicts valid session tokens
- Root Cause: Weak session token generation, insecure transmission
- Impact: Account takeover, unauthorized access
- Mitigation: Secure random token generation, HTTPS, HttpOnly/Secure cookie flags

**Credential Stuffing and Reuse (22)**
- Definition: Using leaked credentials to access accounts across services
- Root Cause: Users reusing passwords, no breach detection
- Impact: Mass account compromise, data breaches
- Mitigation: MFA, breach password checks, unique credential requirements

**Insecure "Remember Me" Functionality (85)**
- Definition: Weak persistent authentication token implementation
- Root Cause: Predictable tokens, inadequate expiration controls
- Impact: Unauthorized persistent access, session compromise
- Mitigation: Strong token generation, proper expiration, secure storage

**CAPTCHA Bypass (86)**
- Definition: Circumventing bot detection mechanisms
- Root Cause: Weak CAPTCHA algorithms, improper validation
- Impact: Automated attacks, credential stuffing, spam
- Mitigation: reCAPTCHA v3, layered bot detection, rate limiting

### Phase 3: Sensitive Data Exposure

Identify data protection failures:

**IDOR - Insecure Direct Object References (23, 42)**
- Definition: Direct access to internal objects via user-supplied references
- Root Cause: Missing authorization checks on object access
- Impact: Unauthorized data access, privacy breaches
- Mitigation: Access control validation, indirect reference maps, authorization checks

**Data Leakage (24)**
- Definition: Inadvertent disclosure of sensitive information
- Root Cause: Inadequate data protection, weak access controls
- Impact: Privacy breaches, regulatory penalties, reputation damage
- Mitigation: DLP solutions, encryption, access controls, security training

**Unencrypted Data Storage (25)**
- Definition: Storing sensitive data without encryption
- Root Cause: Failure to implement encryption at rest
- Impact: Data breaches if storage compromised
- Mitigation: Full-disk encryption, database encryption, secure key management

**Information Disclosure (33)**
- Definition: Exposure of system details through error messages or responses
- Root Cause: Verbose error handling, debug information in production
- Impact: Reconnaissance for further attacks, credential exposure
- Mitigation: Generic error messages, disable debug mode, secure logging

### Phase 4: Security Misconfiguration

Assess configuration weaknesses:

**Missing Security Headers (26)**
- Definition: Absence of protective HTTP headers (CSP, X-Frame-Options, HSTS)
- Root Cause: Inadequate server configuration
- Impact: XSS attacks, clickjacking, protocol downgrade
- Mitigation: Implement CSP, X-Content-Type-Options, X-Frame-Options, HSTS

**Default Passwords (28)**
- Definition: Unchanged default credentials on systems/applications
- Root Cause: Failure to change vendor defaults
- Impact: Unauthorized access, system compromise
- Mitigation: Mandatory password changes, strong password policies

**Directory Listing (29)**
- Definition: Web server exposes directory contents
- Root Cause: Improper server configuration
- Impact: Information disclosure, sensitive file exposure
- Mitigation: Disable directory indexing, use default index files

**Unprotected API Endpoints (30)**
- Definition: APIs lacking authentication or authorization
- Root Cause: Missing security controls on API routes
- Impact: Unauthorized data access, API abuse
- Mitigation: OAuth/API keys, access controls, rate limiting

**Open Ports and Services (31)**
- Definition: Unnecessary network services exposed
- Root Cause: Failure to minimize attack surface
- Impact: Exploitation of vulnerable services
- Mitigation: Port scanning audits, firewall rules, service minimization

**Misconfigured CORS (35)**
- Definition: Overly permissive Cross-Origin Resource Sharing policies
- Root Cause: Wildcard origins, improper CORS configuration
- Impact: Cross-site request attacks, data theft
- Mitigation: Whitelist trusted origins, validate CORS headers

**Unpatched Software (34)**
- Definition: Systems running outdated vulnerable software
- Root Cause: Neglected patch management
- Impact: Exploitation of known vulnerabilities
- Mitigation: Patch management program, vulnerability scanning, automated updates

### Phase 5: XML-Related Vulnerabilities

Evaluate XML processing security:

**XXE - XML External Entity Injection (37)**
- Definition: Exploitation of XML parsers to access files or internal systems
- Root Cause: External entity processing enabled
- Impact: File disclosure, SSRF, denial of service
- Mitigation: Disable external entities, use safe XML parsers

**XEE - XML Entity Expansion (38)**
- Definition: Excessive entity expansion causing resource exhaustion
- Root Cause: Unlimited entity expansion allowed
- Impact: Denial of service, parser crashes
- Mitigation: Limit entity expansion, configure parser restrictions

**XML Bomb (Billion Laughs) (39)**
- Definition: Crafted XML with nested entities consuming resources
- Root Cause: Recursive entity definitions
- Impact: Memory exhaustion, denial of service
- Mitigation: Entity expansion limits, input size restrictions

**XML Denial of Service (65)**
- Definition: Specially crafted XML causing excessive processing
- Root Cause: Complex document structures without limits
- Impact: CPU/memory exhaustion, service unavailability
- Mitigation: Schema validation, size limits, processing timeouts

### Phase 6: Broken Access Control

Assess authorization enforcement:

**Inadequate Authorization (40)**
- Definition: Failure to properly enforce access controls
- Root Cause: Weak authorization policies, missing checks
- Impact: Unauthorized access to sensitive resources
- Mitigation: RBAC, centralized IAM, regular access reviews

**Privilege Escalation (41)**
- Definition: Gaining elevated access beyond intended permissions
- Root Cause: Misconfigured permissions, system vulnerabilities
- Impact: Full system compromise, data manipulation
- Mitigation: Least privilege, regular patching, privilege monitoring

**Forceful Browsing (43)**
- Definition: Direct URL manipulation to access restricted resources
- Root Cause: Weak access controls, predictable URLs
- Impact: Unauthorized file/directory access
- Mitigation: Server-side access controls, unpredictable resource paths

**Missing Function-Level Access Control (44)**
- Definition: Unprotected administrative or privileged functions
- Root Cause: Authorization only at UI level
- Impact: Unauthorized function execution
- Mitigation: Server-side authorization for all functions, RBAC

### Phase 7: Insecure Deserialization

Evaluate object serialization security:

**Remote Code Execution via Deserialization (45)**
- Definition: Arbitrary code execution through malicious serialized objects
- Root Cause: Untrusted data deserialized without validation
- Impact: Complete system compromise, code execution
- Mitigation: Avoid deserializing untrusted data, integrity checks, type validation

**Data Tampering (46)**
- Definition: Unauthorized modification of serialized data
- Root Cause: Missing integrity verification
- Impact: Data corruption, privilege manipulation
- Mitigation: Digital signatures, HMAC validation, encryption

**Object Injection (47)**
- Definition: Malicious object instantiation during deserialization
- Root Cause: Unsafe deserialization practices
- Impact: Code execution, unauthorized access
- Mitigation: Type restrictions, class whitelisting, secure libraries

### Phase 8: API Security Assessment

Evaluate API-specific vulnerabilities:

**Insecure API Endpoints (48)**
- Definition: APIs without proper security controls
- Root Cause: Poor API design, missing authentication
- Impact: Data breaches, unauthorized access
- Mitigation: OAuth/JWT, HTTPS, input validation, rate limiting

**API Key Exposure (49)**
- Definition: Leaked or exposed API credentials
- Root Cause: Hardcoded keys, insecure storage
- Impact: Unauthorized API access, abuse
- Mitigation: Secure key storage, rotation, environment variables

**Lack of Rate Limiting (50)**
- Definition: No controls on API request frequency
- Root Cause: Missing throttling mechanisms
- Impact: DoS, API abuse, resource exhaustion
- Mitigation: Rate limits per user/IP, throttling, DDoS protection

**Inadequate Input Validation (51)**
- Definition: APIs accepting unvalidated user input
- Root Cause: Missing server-side validation
- Impact: Injection attacks, data corruption
- Mitigation: Strict validation, parameterized queries, WAF

**API Abuse (75)**
- Definition: Exploiting API functionality for malicious purposes
- Root Cause: Excessive trust in client input
- Impact: Data theft, account takeover, service abuse
- Mitigation: Strong authentication, behavior analysis, anomaly detection

### Phase 9: Communication Security

Assess transport layer protections:

**Man-in-the-Middle Attack (52)**
- Definition: Interception of communication between parties
- Root Cause: Unencrypted channels, compromised networks
- Impact: Data theft, session hijacking, impersonation
- Mitigation: TLS/SSL, certificate pinning, mutual authentication

**Insufficient Transport Layer Security (53)**
- Definition: Weak or outdated encryption for data in transit
- Root Cause: Outdated protocols (SSLv2/3), weak ciphers
- Impact: Traffic interception, credential theft
- Mitigation: TLS 1.2+, strong cipher suites, HSTS

**Insecure SSL/TLS Configuration (54)**
- Definition: Improperly configured encryption settings
- Root Cause: Weak ciphers, missing forward secrecy
- Impact: Traffic decryption, MITM attacks
- Mitigation: Modern cipher suites, PFS, certificate validation

**Insecure Communication Protocols (55)**
- Definition: Use of unencrypted protocols (HTTP, Telnet, FTP)
- Root Cause: Legacy systems, security unawareness
- Impact: Traffic sniffing, credential exposure
- Mitigation: HTTPS, SSH, SFTP, VPN tunnels

### Phase 10: Client-Side Vulnerabilities

Evaluate browser-side security:

**DOM-based XSS (56)**
- Definition: XSS through client-side JavaScript manipulation
- Root Cause: Unsafe DOM manipulation with user input
- Impact: Session theft, credential harvesting
- Mitigation: Safe DOM APIs, CSP, input sanitization

**Insecure Cross-Origin Communication (57)**
- Definition: Improper handling of cross-origin requests
- Root Cause: Relaxed CORS/SOP policies
- Impact: Data leakage, CSRF attacks
- Mitigation: Strict CORS, CSRF tokens, origin validation

**Browser Cache Poisoning (58)**
- Definition: Manipulation of cached content
- Root Cause: Weak cache validation
- Impact: Malicious content delivery
- Mitigation: Cache-Control headers, HTTPS, integrity checks

**Clickjacking (59, 71)**
- Definition: UI redress attack tricking users into clicking hidden elements
- Root Cause: Missing frame protection
- Impact: Unintended actions, credential theft
- Mitigation: X-Frame-Options, CSP frame-ancestors, frame-busting

**HTML5 Security Issues (60)**
- Definition: Vulnerabilities in HTML5 APIs (WebSockets, Storage, Geolocation)
- Root Cause: Improper API usage, insufficient validation
- Impact: Data leakage, XSS, privacy violations
- Mitigation: Secure API usage, input validation, sandboxing

### Phase 11: Denial of Service Assessment

Evaluate availability threats:

**DDoS - Distributed Denial of Service (61)**
- Definition: Overwhelming systems with traffic from multiple sources
- Root Cause: Botnets, amplification attacks
- Impact: Service unavailability, revenue loss
- Mitigation: DDoS protection services, rate limiting, CDN

**Application Layer DoS (62)**
- Definition: Targeting application logic to exhaust resources
- Root Cause: Inefficient code, resource-intensive operations
- Impact: Application unavailability, degraded performance
- Mitigation: Rate limiting, caching, WAF, code optimization

**Resource Exhaustion (63)**
- Definition: Depleting CPU, memory, disk, or network resources
- Root Cause: Inefficient resource management
- Impact: System crashes, service degradation
- Mitigation: Resource quotas, monitoring, load balancing

**Slowloris Attack (64)**
- Definition: Keeping connections open with partial HTTP requests
- Root Cause: No connection timeouts
- Impact: Web server resource exhaustion
- Mitigation: Connection timeouts, request limits, reverse proxy

### Phase 12: Server-Side Request Forgery

Assess SSRF vulnerabilities:

**SSRF - Server-Side Request Forgery (66)**
- Definition: Manipulating server to make requests to internal resources
- Root Cause: Unvalidated user-controlled URLs
- Impact: Internal network access, data theft, cloud metadata access
- Mitigation: URL whitelisting, network segmentation, egress filtering

**Blind SSRF (87)**
- Definition: SSRF without direct response visibility
- Root Cause: Similar to SSRF, harder to detect
- Impact: Data exfiltration, internal reconnaissance
- Mitigation: Allowlists, WAF, network restrictions

**Time-Based Blind SSRF (88)**
- Definition: Inferring SSRF success through response timing
- Root Cause: Processing delays indicating request outcomes
- Impact: Prolonged exploitation, detection evasion
- Mitigation: Request timeouts, anomaly detection, timing monitoring

### Phase 13: Additional Web Vulnerabilities

| # | Vulnerability | Root Cause | Impact | Mitigation |
|---|--------------|-----------|--------|------------|
| 67 | HTTP Parameter Pollution | Inconsistent parsing | Injection, ACL bypass | Strict parsing, validation |
| 68 | Insecure Redirects | Unvalidated targets | Phishing, malware | Whitelist destinations |
| 69 | File Inclusion (LFI/RFI) | Unvalidated paths | Code exec, disclosure | Whitelist files, disable RFI |
| 70 | Security Header Bypass | Misconfigured headers | XSS, clickjacking | Proper headers, audits |
| 72 | Inadequate Session Timeout | Excessive timeouts | Session hijacking | Idle termination, timeouts |
| 73 | Insufficient Logging | Missing infrastructure | Detection gaps | SIEM, alerting |
| 74 | Business Logic Flaws | Insecure design | Fraud, unauthorized ops | Threat modeling, testing |

### Phase 14: Mobile and IoT Security

| # | Vulnerability | Root Cause | Impact | Mitigation |
|---|--------------|-----------|--------|------------|
| 76 | Insecure Mobile Storage | Plain text, weak crypto | Data theft | Keychain/Keystore, encrypt |
| 77 | Insecure Mobile Transmission | HTTP, cert failures | Traffic interception | TLS, cert pinning |
| 78 | Insecure Mobile APIs | Missing auth/validation | Data exposure | OAuth/JWT, validation |
| 79 | App Reverse Engineering | Hardcoded creds | Credential theft | Obfuscation, RASP |
| 80 | IoT Management Issues | Weak auth, no TLS | Device takeover | Strong auth, TLS |
| 81 | Weak IoT Authentication | Default passwords | Unauthorized access | Unique creds, MFA |
| 82 | IoT Vulnerabilities | Design flaws, old firmware | Botnet recruitment | Updates, segmentation |
| 83 | Smart Home Access | Insecure defaults | Privacy invasion | MFA, segmentation |
| 84 | IoT Privacy Issues | Excessive collection | Surveillance | Data minimization |

### Phase 15: Advanced and Zero-Day Threats

| # | Vulnerability | Root Cause | Impact | Mitigation |
|---|--------------|-----------|--------|------------|
| 89 | MIME Sniffing | Missing headers | XSS, spoofing | X-Content-Type-Options |
| 91 | CSP Bypass | Weak config | XSS despite CSP | Strict CSP, nonces |
| 92 | Inconsistent Validation | Decentralized logic | Control bypass | Centralized validation |
| 93 | Race Conditions | Missing sync | Privilege escalation | Proper locking |
| 94-95 | Business Logic Flaws | Missing validation | Financial fraud | Server-side validation |
| 96 | Account Enumeration | Different responses | Targeted attacks | Uniform responses |
| 98-99 | Unpatched Vulnerabilities | Patch delays | Zero-day exploitation | Patch management |
| 100 | Zero-Day Exploits | Unknown vulns | Unmitigated attacks | Defense in depth |

---

## Quick Reference

### Vulnerability Categories Summary

| Category | Vulnerability Numbers | Key Controls |
|----------|----------------------|--------------|
| Injection | 1-13 | Parameterized queries, input validation, output encoding |
| Authentication | 14-23, 85-86 | MFA, session management, account lockout |
| Data Exposure | 24-27 | Encryption at rest/transit, access controls, DLP |
| Misconfiguration | 28-36 | Secure defaults, hardening, patching |
| XML | 37-39, 65 | Disable external entities, limit expansion |
| Access Control | 40-44 | RBAC, least privilege, authorization checks |
| Deserialization | 45-47 | Avoid untrusted data, integrity validation |
| API Security | 48-51, 75 | OAuth, rate limiting, input validation |
| Communication | 52-55 | TLS 1.2+, certificate validation, HTTPS |
| Client-Side | 56-60 | CSP, X-Frame-Options, safe DOM |
| DoS | 61-65 | Rate limiting, DDoS protection, resource limits |
| SSRF | 66, 87-88 | URL whitelisting, egress filtering |
| Mobile/IoT | 76-84 | Encryption, authentication, secure storage |
| Business Logic | 74, 92-97 | Threat modeling, logic testing |
| Zero-Day | 98-100 | Defense in depth, threat intelligence |

### Critical Security Headers

```
Content-Security-Policy: default-src 'self'; script-src 'self'
X-Content-Type-Options: nosniff
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block
Strict-Transport-Security: max-age=31536000; includeSubDomains
Referrer-Policy: strict-origin-when-cross-origin
Permissions-Policy: geolocation=(), microphone=()
```

### OWASP Top 10 Mapping

| OWASP 2021 | Related Vulnerabilities |
|------------|------------------------|
| A01: Broken Access Control | 40-44, 23, 74 |
| A02: Cryptographic Failures | 24-25, 53-55 |
| A03: Injection | 1-13, 37-39 |
| A04: Insecure Design | 74, 92-97 |
| A05: Security Misconfiguration | 26-36 |
| A06: Vulnerable Components | 34, 98-100 |
| A07: Auth Failures | 14-23, 85-86 |
| A08: Data Integrity | 45-47 |
| A09: Logging Failures | 73 |
| A10: SSRF | 66, 87-88 |

---

## Constraints and Limitations

- Vulnerability definitions represent common patterns; specific implementations vary
- Mitigations must be adapted to technology stack and architecture
- New vulnerabilities emerge continuously; reference should be updated
- Some vulnerabilities overlap across categories (e.g., IDOR appears in multiple contexts)
- Effectiveness of mitigations depends on proper implementation
- Automated scanners cannot detect all vulnerability types (especially business logic)

---

## Troubleshooting

### Common Assessment Challenges

| Challenge | Solution |
|-----------|----------|
| False positives in scanning | Manual verification, contextual analysis |
| Business logic flaws missed | Manual testing, threat modeling, abuse case analysis |
| Encrypted traffic analysis | Proxy configuration, certificate installation |
| WAF blocking tests | Rate adjustment, IP rotation, payload encoding |
| Session handling issues | Cookie management, authentication state tracking |
| API discovery | Swagger/OpenAPI enumeration, traffic analysis |

### Vulnerability Verification Techniques

| Vulnerability Type | Verification Approach |
|-------------------|----------------------|
| Injection | Payload testing with encoded variants |
| XSS | Alert boxes, cookie access, DOM inspection |
| CSRF | Cross-origin form submission testing |
| SSRF | Out-of-band DNS/HTTP callbacks |
| XXE | External entity with controlled server |
| Access Control | Horizontal/vertical privilege testing |
| Authentication | Credential rotation, session analysis |

---

## References

- OWASP Top 10 Web Application Security Risks
- CWE/SANS Top 25 Most Dangerous Software Errors
- OWASP Testing Guide
- OWASP Application Security Verification Standard (ASVS)
- NIST Cybersecurity Framework
- Source: Kumar MS - Top 100 Web Vulnerabilities


# Merged section: api-security-best-practices (from security/api-security-best-practices)
Supporting files from this skill live in `references/api-security-best-practices/`, `scripts/api-security-best-practices/`, `data/api-security-best-practices/` (whichever exist).

# API Security Best Practices

## Overview

Guide developers in building secure APIs by implementing authentication, authorization, input validation, rate limiting, and protection against common vulnerabilities. This skill covers security patterns for REST, GraphQL, and WebSocket APIs.

## When to Use This Skill

- Use when designing new API endpoints
- Use when securing existing APIs
- Use when implementing authentication and authorization
- Use when protecting against API attacks (injection, DDoS, etc.)
- Use when conducting API security reviews
- Use when preparing for security audits
- Use when implementing rate limiting and throttling
- Use when handling sensitive data in APIs

## How It Works

### Step 1: Authentication & Authorization

I'll help you implement secure authentication:
- Choose authentication method (JWT, OAuth 2.0, API keys)
- Implement token-based authentication
- Set up role-based access control (RBAC)
- Secure session management
- Implement multi-factor authentication (MFA)

### Step 2: Input Validation & Sanitization

Protect against injection attacks:
- Validate all input data
- Sanitize user inputs
- Use parameterized queries
- Implement request schema validation
- Prevent SQL injection, XSS, and command injection

### Step 3: Rate Limiting & Throttling

Prevent abuse and DDoS attacks:
- Implement rate limiting per user/IP
- Set up API throttling
- Configure request quotas
- Handle rate limit errors gracefully
- Monitor for suspicious activity

### Step 4: Data Protection

Secure sensitive data:
- Encrypt data in transit (HTTPS/TLS)
- Encrypt sensitive data at rest
- Implement proper error handling (no data leaks)
- Sanitize error messages
- Use secure headers

### Step 5: API Security Testing

Verify security implementation:
- Test authentication and authorization
- Perform penetration testing
- Check for common vulnerabilities (OWASP API Top 10)
- Validate input handling
- Test rate limiting


## Examples

### Example 1: Implementing JWT Authentication

```markdown
## Secure JWT Authentication Implementation

### Authentication Flow

1. User logs in with credentials
2. Server validates credentials
3. Server generates JWT token
4. Client stores token securely
5. Client sends token with each request
6. Server validates token

### Implementation

#### 1. Generate Secure JWT Tokens

\`\`\`javascript
// auth.js
const jwt = require('jsonwebtoken');
const bcrypt = require('bcrypt');

// Login endpoint
app.post('/api/auth/login', async (req, res) => {
  try {
    const { email, password } = req.body;
    
    // Validate input
    if (!email || !password) {
      return res.status(400).json({ 
        error: 'Email and password are required' 
      });
    }
    
    // Find user
    const user = await db.user.findUnique({ 
      where: { email } 
    });
    
    if (!user) {
      // Don't reveal if user exists
      return res.status(401).json({ 
        error: 'Invalid credentials' 
      });
    }
    
    // Verify password
    const validPassword = await bcrypt.compare(
      password, 
      user.passwordHash
    );
    
    if (!validPassword) {
      return res.status(401).json({ 
        error: 'Invalid credentials' 
      });
    }
    
    // Generate JWT token
    const token = jwt.sign(
      { 
        userId: user.id,
        email: user.email,
        role: user.role
      },
      process.env.JWT_SECRET,
      { 
        expiresIn: '1h',
        issuer: 'your-app',
        audience: 'your-app-users'
      }
    );
    
    // Generate refresh token
    const refreshToken = jwt.sign(
      { userId: user.id },
      process.env.JWT_REFRESH_SECRET,
      { expiresIn: '7d' }
    );
    
    // Store refresh token in database
    await db.refreshToken.create({
      data: {
        token: refreshToken,
        userId: user.id,
        expiresAt: new Date(Date.now() + 7 * 24 * 60 * 60 * 1000)
      }
    });
    
    res.json({
      token,
      refreshToken,
      expiresIn: 3600
    });
    
  } catch (error) {
    console.error('Login error:', error);
    res.status(500).json({ 
      error: 'An error occurred during login' 
    });
  }
});
\`\`\`

#### 2. Verify JWT Tokens (Middleware)

\`\`\`javascript
// middleware/auth.js
const jwt = require('jsonwebtoken');

function authenticateToken(req, res, next) {
  // Get token from header
  const authHeader = req.headers['authorization'];
  const token = authHeader && authHeader.split(' ')[1]; // Bearer TOKEN
  
  if (!token) {
    return res.status(401).json({ 
      error: 'Access token required' 
    });
  }
  
  // Verify token
  jwt.verify(
    token, 
    process.env.JWT_SECRET,
    { 
      issuer: 'your-app',
      audience: 'your-app-users'
    },
    (err, user) => {
      if (err) {
        if (err.name === 'TokenExpiredError') {
          return res.status(401).json({ 
            error: 'Token expired' 
          });
        }
        return res.status(403).json({ 
          error: 'Invalid token' 
        });
      }
      
      // Attach user to request
      req.user = user;
      next();
    }
  );
}

module.exports = { authenticateToken };
\`\`\`

#### 3. Protect Routes

\`\`\`javascript
const { authenticateToken } = require('./middleware/auth');

// Protected route
app.get('/api/user/profile', authenticateToken, async (req, res) => {
  try {
    const user = await db.user.findUnique({
      where: { id: req.user.userId },
      select: {
        id: true,
        email: true,
        name: true,
        // Don't return passwordHash
      }
    });
    
    res.json(user);
  } catch (error) {
    res.status(500).json({ error: 'Server error' });
  }
});
\`\`\`

#### 4. Implement Token Refresh

\`\`\`javascript
app.post('/api/auth/refresh', async (req, res) => {
  const { refreshToken } = req.body;
  
  if (!refreshToken) {
    return res.status(401).json({ 
      error: 'Refresh token required' 
    });
  }
  
  try {
    // Verify refresh token
    const decoded = jwt.verify(
      refreshToken, 
      process.env.JWT_REFRESH_SECRET
    );
    
    // Check if refresh token exists in database
    const storedToken = await db.refreshToken.findFirst({
      where: {
        token: refreshToken,
        userId: decoded.userId,
        expiresAt: { gt: new Date() }
      }
    });
    
    if (!storedToken) {
      return res.status(403).json({ 
        error: 'Invalid refresh token' 
      });
    }
    
    // Generate new access token
    const user = await db.user.findUnique({
      where: { id: decoded.userId }
    });
    
    const newToken = jwt.sign(
      { 
        userId: user.id,
        email: user.email,
        role: user.role
      },
      process.env.JWT_SECRET,
      { expiresIn: '1h' }
    );
    
    res.json({
      token: newToken,
      expiresIn: 3600
    });
    
  } catch (error) {
    res.status(403).json({ 
      error: 'Invalid refresh token' 
    });
  }
});
\`\`\`

### Security Best Practices

- ✅ Use strong JWT secrets (256-bit minimum)
- ✅ Set short expiration times (1 hour for access tokens)
- ✅ Implement refresh tokens for long-lived sessions
- ✅ Store refresh tokens in database (can be revoked)
- ✅ Use HTTPS only
- ✅ Don't store sensitive data in JWT payload
- ✅ Validate token issuer and audience
- ✅ Implement token blacklisting for logout
```


### Example 2: Input Validation and SQL Injection Prevention

```markdown
## Preventing SQL Injection and Input Validation

### The Problem

**❌ Vulnerable Code:**
\`\`\`javascript
// NEVER DO THIS - SQL Injection vulnerability
app.get('/api/users/:id', async (req, res) => {
  const userId = req.params.id;
  
  // Dangerous: User input directly in query
  const query = \`SELECT * FROM users WHERE id = '\${userId}'\`;
  const user = await db.query(query);
  
  res.json(user);
});

// Attack example:
// GET /api/users/1' OR '1'='1
// Returns all users!
\`\`\`

### The Solution

#### 1. Use Parameterized Queries

\`\`\`javascript
// ✅ Safe: Parameterized query
app.get('/api/users/:id', async (req, res) => {
  const userId = req.params.id;
  
  // Validate input first
  if (!userId || !/^\d+$/.test(userId)) {
    return res.status(400).json({ 
      error: 'Invalid user ID' 
    });
  }
  
  // Use parameterized query
  const user = await db.query(
    'SELECT id, email, name FROM users WHERE id = $1',
    [userId]
  );
  
  if (!user) {
    return res.status(404).json({ 
      error: 'User not found' 
    });
  }
  
  res.json(user);
});
\`\`\`

#### 2. Use ORM with Proper Escaping

\`\`\`javascript
// ✅ Safe: Using Prisma ORM
app.get('/api/users/:id', async (req, res) => {
  const userId = parseInt(req.params.id);
  
  if (isNaN(userId)) {
    return res.status(400).json({ 
      error: 'Invalid user ID' 
    });
  }
  
  const user = await prisma.user.findUnique({
    where: { id: userId },
    select: {
      id: true,
      email: true,
      name: true,
      // Don't select sensitive fields
    }
  });
  
  if (!user) {
    return res.status(404).json({ 
      error: 'User not found' 
    });
  }
  
  res.json(user);
});
\`\`\`

#### 3. Implement Request Validation with Zod

\`\`\`javascript
const { z } = require('zod');

// Define validation schema
const createUserSchema = z.object({
  email: z.string().email('Invalid email format'),
  password: z.string()
    .min(8, 'Password must be at least 8 characters')
    .regex(/[A-Z]/, 'Password must contain uppercase letter')
    .regex(/[a-z]/, 'Password must contain lowercase letter')
    .regex(/[0-9]/, 'Password must contain number'),
  name: z.string()
    .min(2, 'Name must be at least 2 characters')
    .max(100, 'Name too long'),
  age: z.number()
    .int('Age must be an integer')
    .min(18, 'Must be 18 or older')
    .max(120, 'Invalid age')
    .optional()
});

// Validation middleware
function validateRequest(schema) {
  return (req, res, next) => {
    try {
      schema.parse(req.body);
      next();
    } catch (error) {
      res.status(400).json({
        error: 'Validation failed',
        details: error.errors
      });
    }
  };
}

// Use validation
app.post('/api/users', 
  validateRequest(createUserSchema),
  async (req, res) => {
    // Input is validated at this point
    const { email, password, name, age } = req.body;
    
    // Hash password
    const passwordHash = await bcrypt.hash(password, 10);
    
    // Create user
    const user = await prisma.user.create({
      data: {
        email,
        passwordHash,
        name,
        age
      }
    });
    
    // Don't return password hash
    const { passwordHash: _, ...userWithoutPassword } = user;
    res.status(201).json(userWithoutPassword);
  }
);
\`\`\`

#### 4. Sanitize Output to Prevent XSS

\`\`\`javascript
const DOMPurify = require('isomorphic-dompurify');

app.post('/api/comments', authenticateToken, async (req, res) => {
  const { content } = req.body;
  
  // Validate
  if (!content || content.length > 1000) {
    return res.status(400).json({ 
      error: 'Invalid comment content' 
    });
  }
  
  // Sanitize HTML to prevent XSS
  const sanitizedContent = DOMPurify.sanitize(content, {
    ALLOWED_TAGS: ['b', 'i', 'em', 'strong', 'a'],
    ALLOWED_ATTR: ['href']
  });
  
  const comment = await prisma.comment.create({
    data: {
      content: sanitizedContent,
      userId: req.user.userId
    }
  });
  
  res.status(201).json(comment);
});
\`\`\`

### Validation Checklist

- [ ] Validate all user inputs
- [ ] Use parameterized queries or ORM
- [ ] Validate data types (string, number, email, etc.)
- [ ] Validate data ranges (min/max length, value ranges)
- [ ] Sanitize HTML content
- [ ] Escape special characters
- [ ] Validate file uploads (type, size, content)
- [ ] Use allowlists, not blocklists
```


### Example 3: Rate Limiting and DDoS Protection

```markdown
## Implementing Rate Limiting

### Why Rate Limiting?

- Prevent brute force attacks
- Protect against DDoS
- Prevent API abuse
- Ensure fair usage
- Reduce server costs

### Implementation with Express Rate Limit

\`\`\`javascript
const rateLimit = require('express-rate-limit');
const RedisStore = require('rate-limit-redis');
const Redis = require('ioredis');

// Create Redis client
const redis = new Redis({
  host: process.env.REDIS_HOST,
  port: process.env.REDIS_PORT
});

// General API rate limit
const apiLimiter = rateLimit({
  store: new RedisStore({
    client: redis,
    prefix: 'rl:api:'
  }),
  windowMs: 15 * 60 * 1000, // 15 minutes
  max: 100, // 100 requests per window
  message: {
    error: 'Too many requests, please try again later',
    retryAfter: 900 // seconds
  },
  standardHeaders: true, // Return rate limit info in headers
  legacyHeaders: false,
  // Custom key generator (by user ID or IP)
  keyGenerator: (req) => {
    return req.user?.userId || req.ip;
  }
});

// Strict rate limit for authentication endpoints
const authLimiter = rateLimit({
  store: new RedisStore({
    client: redis,
    prefix: 'rl:auth:'
  }),
  windowMs: 15 * 60 * 1000, // 15 minutes
  max: 5, // Only 5 login attempts per 15 minutes
  skipSuccessfulRequests: true, // Don't count successful logins
  message: {
    error: 'Too many login attempts, please try again later',
    retryAfter: 900
  }
});

// Apply rate limiters
app.use('/api/', apiLimiter);
app.use('/api/auth/login', authLimiter);
app.use('/api/auth/register', authLimiter);

// Custom rate limiter for expensive operations
const expensiveLimiter = rateLimit({
  windowMs: 60 * 60 * 1000, // 1 hour
  max: 10, // 10 requests per hour
  message: {
    error: 'Rate limit exceeded for this operation'
  }
});

app.post('/api/reports/generate', 
  authenticateToken,
  expensiveLimiter,
  async (req, res) => {
    // Expensive operation
  }
);
\`\`\`

### Advanced: Per-User Rate Limiting

\`\`\`javascript
// Different limits based on user tier
function createTieredRateLimiter() {
  const limits = {
    free: { windowMs: 60 * 60 * 1000, max: 100 },
    pro: { windowMs: 60 * 60 * 1000, max: 1000 },
    enterprise: { windowMs: 60 * 60 * 1000, max: 10000 }
  };
  
  return async (req, res, next) => {
    const user = req.user;
    const tier = user?.tier || 'free';
    const limit = limits[tier];
    
    const key = \`rl:user:\${user.userId}\`;
    const current = await redis.incr(key);
    
    if (current === 1) {
      await redis.expire(key, limit.windowMs / 1000);
    }
    
    if (current > limit.max) {
      return res.status(429).json({
        error: 'Rate limit exceeded',
        limit: limit.max,
        remaining: 0,
        reset: await redis.ttl(key)
      });
    }
    
    // Set rate limit headers
    res.set({
      'X-RateLimit-Limit': limit.max,
      'X-RateLimit-Remaining': limit.max - current,
      'X-RateLimit-Reset': await redis.ttl(key)
    });
    
    next();
  };
}

app.use('/api/', authenticateToken, createTieredRateLimiter());
\`\`\`

### DDoS Protection with Helmet

\`\`\`javascript
const helmet = require('helmet');

app.use(helmet({
  // Content Security Policy
  contentSecurityPolicy: {
    directives: {
      defaultSrc: ["'self'"],
      styleSrc: ["'self'", "'unsafe-inline'"],
      scriptSrc: ["'self'"],
      imgSrc: ["'self'", 'data:', 'https:']
    }
  },
  // Prevent clickjacking
  frameguard: { action: 'deny' },
  // Hide X-Powered-By header
  hidePoweredBy: true,
  // Prevent MIME type sniffing
  noSniff: true,
  // Enable HSTS
  hsts: {
    maxAge: 31536000,
    includeSubDomains: true,
    preload: true
  }
}));
\`\`\`

### Rate Limit Response Headers

\`\`\`
X-RateLimit-Limit: 100
X-RateLimit-Remaining: 87
X-RateLimit-Reset: 1640000000
Retry-After: 900
\`\`\`
```

## Best Practices

### ✅ Do This

- **Use HTTPS Everywhere** - Never send sensitive data over HTTP
- **Implement Authentication** - Require authentication for protected endpoints
- **Validate All Inputs** - Never trust user input
- **Use Parameterized Queries** - Prevent SQL injection
- **Implement Rate Limiting** - Protect against brute force and DDoS
- **Hash Passwords** - Use bcrypt with salt rounds >= 10
- **Use Short-Lived Tokens** - JWT access tokens should expire quickly
- **Implement CORS Properly** - Only allow trusted origins
- **Log Security Events** - Monitor for suspicious activity
- **Keep Dependencies Updated** - Regularly update packages
- **Use Security Headers** - Implement Helmet.js
- **Sanitize Error Messages** - Don't leak sensitive information

### ❌ Don't Do This

- **Don't Store Passwords in Plain Text** - Always hash passwords
- **Don't Use Weak Secrets** - Use strong, random JWT secrets
- **Don't Trust User Input** - Always validate and sanitize
- **Don't Expose Stack Traces** - Hide error details in production
- **Don't Use String Concatenation for SQL** - Use parameterized queries
- **Don't Store Sensitive Data in JWT** - JWTs are not encrypted
- **Don't Ignore Security Updates** - Update dependencies regularly
- **Don't Use Default Credentials** - Change all default passwords
- **Don't Disable CORS Completely** - Configure it properly instead
- **Don't Log Sensitive Data** - Sanitize logs

## Common Pitfalls

### Problem: JWT Secret Exposed in Code
**Symptoms:** JWT secret hardcoded or committed to Git
**Solution:**
\`\`\`javascript
// ❌ Bad
const JWT_SECRET = 'my-secret-key';

// ✅ Good
const JWT_SECRET = process.env.JWT_SECRET;
if (!JWT_SECRET) {
  throw new Error('JWT_SECRET environment variable is required');
}

// Generate strong secret
// node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"
\`\`\`

### Problem: Weak Password Requirements
**Symptoms:** Users can set weak passwords like "password123"
**Solution:**
\`\`\`javascript
const passwordSchema = z.string()
  .min(12, 'Password must be at least 12 characters')
  .regex(/[A-Z]/, 'Must contain uppercase letter')
  .regex(/[a-z]/, 'Must contain lowercase letter')
  .regex(/[0-9]/, 'Must contain number')
  .regex(/[^A-Za-z0-9]/, 'Must contain special character');

// Or use a password strength library
const zxcvbn = require('zxcvbn');
const result = zxcvbn(password);
if (result.score < 3) {
  return res.status(400).json({
    error: 'Password too weak',
    suggestions: result.feedback.suggestions
  });
}
\`\`\`

### Problem: Missing Authorization Checks
**Symptoms:** Users can access resources they shouldn't
**Solution:**
\`\`\`javascript
// ❌ Bad: Only checks authentication
app.delete('/api/posts/:id', authenticateToken, async (req, res) => {
  await prisma.post.delete({ where: { id: req.params.id } });
  res.json({ success: true });
});

// ✅ Good: Checks both authentication and authorization
app.delete('/api/posts/:id', authenticateToken, async (req, res) => {
  const post = await prisma.post.findUnique({
    where: { id: req.params.id }
  });
  
  if (!post) {
    return res.status(404).json({ error: 'Post not found' });
  }
  
  // Check if user owns the post or is admin
  if (post.userId !== req.user.userId && req.user.role !== 'admin') {
    return res.status(403).json({ 
      error: 'Not authorized to delete this post' 
    });
  }
  
  await prisma.post.delete({ where: { id: req.params.id } });
  res.json({ success: true });
});
\`\`\`

### Problem: Verbose Error Messages
**Symptoms:** Error messages reveal system details
**Solution:**
\`\`\`javascript
// ❌ Bad: Exposes database details
app.post('/api/users', async (req, res) => {
  try {
    const user = await prisma.user.create({ data: req.body });
    res.json(user);
  } catch (error) {
    res.status(500).json({ error: error.message });
    // Error: "Unique constraint failed on the fields: (`email`)"
  }
});

// ✅ Good: Generic error message
app.post('/api/users', async (req, res) => {
  try {
    const user = await prisma.user.create({ data: req.body });
    res.json(user);
  } catch (error) {
    console.error('User creation error:', error); // Log full error
    
    if (error.code === 'P2002') {
      return res.status(400).json({ 
        error: 'Email already exists' 
      });
    }
    
    res.status(500).json({ 
      error: 'An error occurred while creating user' 
    });
  }
});
\`\`\`

## Security Checklist

### Authentication & Authorization
- [ ] Implement strong authentication (JWT, OAuth 2.0)
- [ ] Use HTTPS for all endpoints
- [ ] Hash passwords with bcrypt (salt rounds >= 10)
- [ ] Implement token expiration
- [ ] Add refresh token mechanism
- [ ] Verify user authorization for each request
- [ ] Implement role-based access control (RBAC)

### Input Validation
- [ ] Validate all user inputs
- [ ] Use parameterized queries or ORM
- [ ] Sanitize HTML content
- [ ] Validate file uploads
- [ ] Implement request schema validation
- [ ] Use allowlists, not blocklists

### Rate Limiting & DDoS Protection
- [ ] Implement rate limiting per user/IP
- [ ] Add stricter limits for auth endpoints
- [ ] Use Redis for distributed rate limiting
- [ ] Return proper rate limit headers
- [ ] Implement request throttling

### Data Protection
- [ ] Use HTTPS/TLS for all traffic
- [ ] Encrypt sensitive data at rest
- [ ] Don't store sensitive data in JWT
- [ ] Sanitize error messages
- [ ] Implement proper CORS configuration
- [ ] Use security headers (Helmet.js)

### Monitoring & Logging
- [ ] Log security events
- [ ] Monitor for suspicious activity
- [ ] Set up alerts for failed auth attempts
- [ ] Track API usage patterns
- [ ] Don't log sensitive data

## OWASP API Security Top 10

1. **Broken Object Level Authorization** - Always verify user can access resource
2. **Broken Authentication** - Implement strong authentication mechanisms
3. **Broken Object Property Level Authorization** - Validate which properties user can access
4. **Unrestricted Resource Consumption** - Implement rate limiting and quotas
5. **Broken Function Level Authorization** - Verify user role for each function
6. **Unrestricted Access to Sensitive Business Flows** - Protect critical workflows
7. **Server Side Request Forgery (SSRF)** - Validate and sanitize URLs
8. **Security Misconfiguration** - Use security best practices and headers
9. **Improper Inventory Management** - Document and secure all API endpoints
10. **Unsafe Consumption of APIs** - Validate data from third-party APIs

## Related Skills

- `@ethical-hacking-methodology` - Security testing perspective
- `@sql-injection-testing` - Testing for SQL injection
- `@xss-html-injection` - Testing for XSS vulnerabilities
- `@broken-authentication` - Authentication vulnerabilities
- `@backend-dev-guidelines` - Backend development standards
- `@systematic-debugging` - Debug security issues

## Additional Resources

- [OWASP API Security Top 10](https://owasp.org/www-project-api-security/)
- [JWT Best Practices](https://tools.ietf.org/html/rfc8725)
- [Express Security Best Practices](https://expressjs.com/en/advanced/best-practice-security.html)
- [Node.js Security Checklist](https://blog.risingstack.com/node-js-security-checklist/)
- [API Security Checklist](https://github.com/shieldfy/API-Security-Checklist)

---

**Pro Tip:** Security is not a one-time task - regularly audit your APIs, keep dependencies updated, and stay informed about new vulnerabilities!
