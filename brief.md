Version: NAFATH-V4
Track: Networking

## Overview
A national digital identity service depends on several connected technology fields, and a hidden compromise in one field can affect the others. Software configuration must protect credentials, while AI systems need defenses against manipulated inputs and training data. Mobile applications must protect sensitive information and communicate securely. Networking must deliver traffic to the legitimate service, because unauthorized BGP route announcements can redirect it. Cybersecurity practices help organizations identify and fix vulnerabilities such as Log4Shell. Data transparency, including a Software Bill of Materials (SBOM), helps teams identify vulnerable software components. These fields reinforce one another: secure code can still be exposed through unsafe routing, and a protected network cannot compensate for a vulnerable application. Combining secure development, verification, monitoring, and timely updates reduces the risk of hidden compromise.

## Software
The Twelve-Factor App methodology says deployment-specific configuration, including service credentials and database connection details, should be stored in environment variables rather than hardcoded in source code. Configuration changes between development, testing, and production, while application code should remain consistent. Keeping secrets out of code reduces accidental exposure through public repositories and version history. Sensitive production credentials should also be protected with access controls and a secrets manager.

Resource: The Twelve-Factor App — Config - https://12factor.net/config

## AI
Adversarial machine learning attacks target different stages of a model’s lifecycle. Evasion changes inputs at inference time to trigger incorrect predictions. Poisoning corrupts training data or the training process, influencing what the model learns. Other attacks seek private training information or introduce hidden backdoor behavior. Defenses include protecting datasets, testing models with adversarial examples, restricting access, and monitoring unusual predictions after deployment.

Resource: NIST AI 100-2 E2025 — Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations - https://csrc.nist.gov/pubs/ai/100/2/e2025/final

## Mobile
The OWASP Mobile Application Security Verification Standard (MASVS) defines security controls for mobile applications, including storage, cryptography, authentication, network communication, platform interaction, code quality, resilience, and privacy. Developers use it to establish security requirements; testers assess the app against relevant controls and document findings. The Mobile Application Security Testing Guide (MASTG) provides practical testing methods. MASVS supports consistent verification, but following a checklist alone does not guarantee an application is secure.

Resource: OWASP Mobile Application Security Verification Standard (MASVS) - https://mas.owasp.org/MASVS/

## Networking
BGP connects internet networks by exchanging route announcements. In a route hijack, a network announces an unauthorized route for another network’s IP prefix, potentially causing traffic to be misdirected or disrupted. RPKI enables address holders to publish Route Origin Authorizations (ROAs), which routers can use to validate whether an announcing Autonomous System is authorized. Operators can configure policies to reject invalid announcements. However, RPKI origin validation does not validate the entire AS path or prevent every route leak or interception attack.

Resource: RFC 6811 — BGP Prefix Origin Validation - https://www.rfc-editor.org/rfc/rfc6811

## Cybersecurity
Log4Shell (CVE-2021-44228) was a critical vulnerability in Apache Log4j 2, a widely used Java logging library. In affected versions and configurations, attacker-controlled log data could trigger unsafe JNDI lookups and potentially execute code remotely. It was rated CVSS 10.0 because exploitation could be remote and cause severe impact. The main fix was upgrading affected Log4j versions; the initial 2.15.0 fix was incomplete in some configurations, so organizations needed later appropriate patched releases and verification.

Resource: Apache Log4j CVEs - https://news.apache.org/foundation/entry/apache-log4j-cves

## Data
A Software Bill of Materials (SBOM) is a structured inventory of software components and their supply-chain relationships. NTIA identifies seven minimum data fields: supplier name, component name, component version, other unique identifiers, dependency relationship, SBOM data author, and timestamp. These fields help organizations identify which applications include a vulnerable library and prioritize remediation. SBOMs should be machine-readable and kept current, but an inventory alone does not prove that a component is safe or vulnerability-free.

Resource: The Minimum Elements for a Software Bill of Materials (SBOM) - https://www.ntia.gov/report/2021/minimum-elements-software-bill-materials-sbom

## Misconception in My Track

## Open Question
