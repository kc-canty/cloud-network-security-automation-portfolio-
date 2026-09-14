# Access Risk Automation

## Project Overview

The Access Risk Automation project is designed to identify users who may have unnecessary, outdated, expired, or excessive access to company systems and network resources.

Organizations regularly grant employees and contractors access to applications, VPNs, servers, administrative systems, and network resources.

As employees change roles, contractors complete assignments, and business responsibilities change, some of this access may remain in place longer than necessary.

Manually reviewing this information can be time-consuming and inconsistent.

This project explores how automation can help identify potential access risks and provide security teams with information that can be reviewed and acted upon.

---

# Business Scenario

For this project, the simulated organization is:

**NorthStar Financial Services**

NorthStar Financial Services has employees and contractors across several departments, including:

* Finance
* Human Resources
* Marketing
* Information Technology

Users may receive access to different network resources depending on their job responsibilities.

Examples include:

* Corporate VPN
* Finance VPN
* Department servers
* Administrative network resources
* Internal applications

Over time, access may become outdated or inappropriate.

The security team needs a faster way to identify accounts that may require review.

---

# Business Problem

The organization currently performs user access reviews manually.

This creates several challenges.

Examples include:

* Employees retaining access after changing departments
* Contractors retaining access after their contracts expire
* Accounts remaining active even after long periods of inactivity
* Users receiving administrative privileges that are not required for their job
* Security teams spending significant time reviewing access records manually

These situations can increase the organization's security risk and make compliance reviews more difficult.

---

# Project Goal

The goal of this project is to create a Python-based automation tool that analyzes identity and access information and identifies potential security risks.

The system will compare:

```text
User Information
        +
Assigned Access
        +
Security Policy
        ↓
Access Risk Analysis
        ↓
Security Findings
```

The tool will initially use simulated data.

Future versions may integrate with real enterprise technologies such as Active Directory, Microsoft Entra ID, VPN platforms, SIEM systems, and cloud environments.

---

# Who Would Use This?

Potential users of this type of solution include:

* Identity and Access Management analysts
* Security analysts
* Network administrators
* Security engineers
* IT administrators
* Compliance teams
* Internal auditors

---

# Initial Security Checks

The first version of the project will identify four primary access risks.

## 1. Stale Accounts

Identify users who have not logged in within an approved period of time.

Example:

```text
User: John Smith
Last Login: 120 days ago
Policy: 90 days

Finding: Stale Account
```

---

## 2. Expired Contractor Access

Identify contractors whose contracts have ended but whose accounts remain active.

Example:

```text
User: Jane Doe
Employment Type: Contractor
Contract End Date: August 30
Account Status: Active

Finding: Expired Contractor Access
```

---

## 3. Department Access Mismatch

Identify users who have access to resources that do not align with their department.

Example:

```text
User: Robert Jones
Department: Marketing
Resource: Finance Server

Finding: Department Access Mismatch
```

---

## 4. Excessive Privileged Access

Identify users who have administrative privileges that may not be appropriate for their role.

Example:

```text
User: Sarah Williams
Department: Marketing
Access: Network Administrator

Finding: Unauthorized Privileged Access
```

---

# Security Concepts Demonstrated

This project demonstrates several important cybersecurity concepts.

### Least Privilege

Users should receive only the access required to perform their job responsibilities.

### Identity and Access Management

Access decisions should consider both who the user is and what resources they are authorized to access.

### Privileged Access

Administrative access represents increased security risk and should receive additional review.

### Account Lifecycle Management

Access should change when employees join the organization, change roles, or leave.

### Risk-Based Prioritization

Not every security finding represents the same level of risk.

Findings can be categorized as:

```text
MEDIUM
HIGH
CRITICAL
```

to help analysts prioritize investigations.

---

# Planned Architecture

The initial version of the project will use the following architecture:

```text
users.csv
      \
       \
        ──────> Python Analyzer ──────> findings.csv
       /                │
access.csv              │
                        └─────────────> summary.md
       \
        \
      policies.json
```

### `users.csv`

Contains information about employees and contractors.

Examples:

* User ID
* Name
* Department
* Employment type
* Account status
* Last login
* Contract expiration date

### `access.csv`

Contains information about resources assigned to users.

Examples:

* VPN access
* Server access
* Network access
* Administrative privileges

### `policies.json`

Contains security rules used by the analyzer.

Examples:

* Maximum inactivity period
* Approved resources by department
* Privileged access requirements

### Python Analyzer

Processes user, access, and policy information and identifies security findings.

### `findings.csv`

Contains detailed findings that could be reviewed by a security analyst or imported into another system.

### `summary.md`

Provides a human-readable summary of the access review.

---

# Planned Project Structure

```text
01-access-risk-automation/
│
├── README.md
│
├── data/
│   ├── users.csv
│   └── access.csv
│
├── config/
│   └── policies.json
│
├── src/
│   └── analyzer.py
│
├── reports/
│   ├── findings.csv
│   └── summary.md
│
└── docs/
    └── architecture.md
```

---

# Initial Technology Stack

The first version will use:

* Python
* CSV
* JSON
* Git
* GitHub
* VS Code

Security and networking concepts demonstrated include:

* Identity and Access Management
* Least privilege
* Privileged access
* Network access control
* Access governance
* Security automation
* Risk analysis

---

# Future Improvements

The first version intentionally uses simple simulated data.

Future versions may expand the project by integrating:

* Active Directory
* Microsoft Entra ID
* Cisco network devices
* VPN systems
* Splunk
* REST APIs
* ServiceNow or ticketing systems
* Automated email or messaging alerts
* Scheduled security scans
* AWS
* Microsoft Azure
* Cloud security groups
* Cloud IAM
* Dashboards
* Automated remediation

The long-term goal is to evolve this project from a basic access analysis tool into a more complete network and cloud security automation solution.

---

# Project Status

**Current Status:** In Development

### Version 1 Goals

* [ ] Create simulated user data
* [ ] Create simulated network access data
* [ ] Define security policies
* [ ] Read data using Python
* [ ] Detect stale accounts
* [ ] Detect expired contractors
* [ ] Detect department access mismatches
* [ ] Detect excessive privileged access
* [ ] Assign severity levels
* [ ] Generate findings report
* [ ] Generate management summary
* [ ] Document project architecture

