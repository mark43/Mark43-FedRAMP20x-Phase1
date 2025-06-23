# Mark43 FedRAMP 20x Phase One Pilot Submission

Welcome to Mark43's repository for our participation in the FedRAMP 20x Phase One pilot. This repository demonstrates our cloud service's readiness for authorization using a modern, automated, and machine-readable approach. It aligns with the 20x initiative to reduce redundant documentation and streamline validation through Key Security Indicators (KSIs), reusable evidence, and automation.

> **Note:** This package is being submitted as a **draft** for review. It will be **iteratively and agilely updated** based on feedback from the FedRAMP PMO, community stakeholders, and our 3PAO. All changes will be tracked transparently in this repository.

> **Important:** Mark43 is submitting **two separate packages** to the 20x pilot:
>
> 1. **An already-authorized FedRAMP High environment** deployed in AWS GovCloud. GitHub Repository: [https://github.com/mark43/Mark43-High-FedRAMP20x-Phase1](https://github.com/mark43/Mark43-High-FedRAMP20x-Phase1)
> 2. **A separate SLG-focused environment** that has not yet been FedRAMP authorized but aligns to the High baseline and is supported by existing SOC 2 evidence and inherited controls. GitHub Repository: [https://github.com/mark43/Mark43-FedRAMP20x-Phase1](https://github.com/mark43/Mark43-FedRAMP20x-Phase1)

We are leveraging the [FedRAMP OSCAL schema](https://pages.nist.gov/OSCAL/) for machine-readable content and working with **KRATOS** as our Third Party Assessment Organization (3PAO) to validate and attest to our implementation of security objectives.

---

## Overview: 9-Step Approach to the 20x Pilot

### **Step One: Lightweight Documentation**

We begin with a simplified profile of the Mark43 Public Safety Platform:

- **Environment**: SLG-focused SaaS platform 
- **FedRAMP Authorization Status**: Not yet authorized
- See `README.md` in the main branch for a narrative system overview.

### **Step Two: Key Security Indicators and Validations**

We reviewed the current version of FedRAMP's KSIs and created a structured assertion for each KSI Validation. Assertions will be expressed as `true`, `false`, or `partial` and mapped to existing FedRAMP High controls.

- See `machine-readable-package` and `results` directories

### **Step Three: Validation Evidence**

Evidence is mapped to each KSI Validation marked `true`. Supporting materials may include:

- SOC 2 Type II report
- Compliance automation outputs
- 3PAO validation (pending)
- See `evidence/` directory and references within the file.

### **Step Four: Automation and Machine-Readable Data Requirements**

We generate `controls-validation.json`, a machine-readable file containing:

- KSI Validation assertions
- Linked evidence (document names, file hashes, timestamps)
- Custom schema metadata
- Rebuildable output generated via API solution
- See `machine-readable/README.md` directory

#### Sample JSON Format

```json
[
  {
    "control_id": "AC-2",
    "ksi_validation": "Account provisioning is logged",
    "assertion": "true",
    "evidence": "SOC2_Audit2024.pdf",
    "evidence_hash": "3f8e9f...",
    "last_validated": "2024-05-20",
    "continuous_reporting": true,
    "collection_frequency": "daily",
    "collected_by": "AWS CloudTrail",
    "validator": "KRATOS",
    "attestation": "digitally-signed"
  }
]
```

### **Step Five: 3PAO Review (KRATOS)**

KRATOS, our FedRAMP-accredited 3PAO, will:

- Review the mapped KSIs
- Add attestation to each `true` assertion
- Digitally sign the machine-readable file
- Provide a summary of assessment methods used
- Status: **In Progress**
- 📄 [KRATOS Commitment Letter (PDF)](./3PAO/Kratos-Committment-Letter-Mark43-FedRAMP-20X-Pilot_30MAY.pdf)
- See `3PAO` directory

### **Step Six: Continuous Reporting Indication**

We annotate in our JSON file which KSIs are continuously verifiable (e.g., via logging, scan outputs, cloud telemetry).

- Metadata includes: collection method, frequency, tool name, and evidence location
- See `machine-readable-package` directory

### **Step Seven: Prototype for Continuous Reporting**

Mark43 will define an API solution that exposes:

- Real-time KSI statuses for selected indicators
- Hash of latest evidence file
- Timestamp of evidence generation
- Authentication: API Key with scoped read-only access
- See `dashboard` and `audit` directories

### **Step Eight: CSP Rationale and Summary**

We will provide a full rationale for our pilot submission approach:

- KSI mapping methodology
- Evidence reuse strategy (SOC 2, SSP control inheritance)
- 3PAO integration for digital attestation
- OSCAL readiness objectives

### **Step Nine: CSP Submission**

Mark43 publicly hosts these packages on GitHub:

-

  1. **An already-authorized FedRAMP High environment** deployed in AWS GovCloud. GitHub Repository: [https://github.com/mark43/Mark43-High-FedRAMP20x-Phase1](https://github.com/mark43/Mark43-High-FedRAMP20x-Phase1)

-

  2. **A separate State, Local, and Government (SLG)-focused environment** that has not yet been FedRAMP authorized but aligns to the High baseline and is supported by existing SOC 2 evidence and inherited controls. GitHub Repository: [https://github.com/mark43/Mark43-FedRAMP20x-Phase1](https://github.com/mark43/Mark43-FedRAMP20x-Phase1)

- Access does **not** require FedRAMP to create an account

- All supporting documentation, evidence summaries, and JSON files are structured for easy navigation and consumption

---

## Public References

- [FedRAMP.gov - 20x Pilot](https://www.fedramp.gov/20x/)
- [FedRAMP Community Discussions](https://github.com/FedRAMP/community/discussions/categories/20xp1-pilot-drafts)
- [FedRAMP OSCAL](https://pages.nist.gov/OSCAL/)
- [Mark43 Public Safety Platform](https://www.mark43.com/platform/)

---

## About Mark43

Mark43 provides a secure, cloud-native, multi-tenant SaaS platform for public safety agencies. We are committed to FedRAMP compliance and innovative approaches to government cloud security validation.

[www.mark43.com](https://www.mark43.com)

---

## :busts_in_silhouette: Contact

- **FedRAMP Program Lead**:  
  Kelsey McMichael  
  Director of Federal Security Enablement  
  :email: [kelsey.mcmichael@mark43.com](mailto:kelsey.mcmichael@mark43.com)

- **Security Team**:  
  :email: [security@mark43.com](mailto:security@mark43.com)

*This repository and all contents are provided for the purposes of FedRAMP 20x pilot participation. No Controlled Unclassified Information (CUI) or sensitive operational data is included in this public repository.*

