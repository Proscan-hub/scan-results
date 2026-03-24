# Proscan Binary Analysis — Scan Results

Real scan results from [Proscan](https://proscan.one) binary analysis against deliberately vulnerable applications. These are actual scanner outputs — not fabricated examples.

All artifacts scanned are from well-known open-source vulnerable-by-design projects maintained by OWASP and the security community.

> **Note:** These are basic comprehensive reports demonstrating Proscan's binary analysis capabilities. They provide a high-level overview of detected vulnerabilities with severity, CWE classification, and compliance mapping. For in-depth detailed analysis including bytecode-level taint tracking, call graph visualization, and remediation guidance with code examples, use the full Proscan platform.

## Scan Summary

| Metric | Value |
|--------|-------|
| Total binaries scanned | 156 |
| Total findings | 1,190 |
| Formats analyzed | JVM (JAR/WAR), Go (ELF/PE), Android (APK/DEX) |
| Scan errors | 0 |
| False positives | 0 |

## Projects Scanned

| Project | Type | Findings | Source |
|---------|------|----------|--------|
| [JavaVulnerableLab](reports/JavaVulnerableLab/) | Java WAR | 25 (11 crit, 9 high) | [GitHub](https://github.com/CSPF-Founder/JavaVulnerableLab) |
| [VulnerableApp](reports/VulnerableApp/) | Java JAR | 43 (17 crit, 18 high) | [GitHub](https://github.com/SasanLabs/VulnerableApp) |
| [DVJA](reports/dvja/) | Java WAR + JARs | Multiple | [GitHub](https://github.com/appsecco/dvja) |
| [java-goof](reports/java-goof/) | Java WAR + JARs | Multiple | [GitHub](https://github.com/snyk/java-goof) |
| [log4shell-vuln-app](reports/log4shell-vuln-app/) | Java JAR | Log4Shell (CVE-2021-44228) | [GitHub](https://github.com/christophetd/log4shell-vulnerable-app) |
| [log4j-shell-poc](reports/log4j-shell-poc/) | Java JAR | Log4j exploitation | [GitHub](https://github.com/kozmer/log4j-shell-poc) |
| [govwa](reports/govwa/) | Go binary | Go security issues | [GitHub](https://github.com/0c34/govwa) |
| [vuln-go-app](reports/vuln-go-app/) | Go binary | Go security issues | [GitHub](https://github.com/Contrast-Security-OSS/go-test-bench) |
| [kubernetes-goat](reports/kubernetes-goat/) | Go binaries | K8s security | [GitHub](https://github.com/madhuakula/kubernetes-goat) |
| [hackazon](reports/hackazon/) | Android APK | Mobile security | [GitHub](https://github.com/rapid7/hackazon) |
| [vapi](reports/vapi/) | Android APK | API security | [GitHub](https://github.com/roottusk/vapi) |
| [OWASP MASTG](reports/mastg/) | Android APKs (7) | Mobile testing | [GitHub](https://github.com/OWASP/owasp-mastg) |
| [vulhub](reports/vulhub/) | Java WARs + JARs | Struts2 vulns (S2-001 to S2-015) | [GitHub](https://github.com/vulhub/vulhub) |
| [huskyCI](reports/huskyCI/) | Go binaries | CI/CD security | [GitHub](https://github.com/globocom/huskyCI) |
| [kics](reports/kics/) | Java JARs | ANTLR parser | [GitHub](https://github.com/Checkmarx/kics) |

## Reports

Each project directory contains:

| File | Description |
|------|-------------|
| `comprehensive-report.html` | Full scan report with findings, severity breakdown, and remediation guidance |
| `compliance-owasp-top10.json` | OWASP Top 10 compliance assessment |
| `compliance-pci-dss.json` | PCI DSS 4.0 compliance assessment |
| `compliance-nist-800-53.json` | NIST 800-53 Rev 5 compliance assessment |

## Understanding Compliance Scores

Compliance scores in these reports reflect **detection coverage** — whether Proscan's binary scanner checked for and detected vulnerabilities in each compliance category. They do not represent the application's security posture.

For example, a 100% OWASP Top 10 compliance score on JavaVulnerableLab means Proscan successfully scanned for all 10 OWASP categories. The app itself is deliberately vulnerable — the findings listed in the comprehensive report show the actual vulnerabilities detected.

This is standard behavior for automated scanning tools: compliance reports document what was tested and what was found, not whether the application passes a security audit. A compliance audit requires both automated evidence (what Proscan provides) and manual assessment by a qualified auditor.

## Vulnerability Types Detected

- SQL Injection (CWE-89)
- Cross-Site Scripting (CWE-79)
- Server-Side Request Forgery (CWE-918)
- Insecure Deserialization (CWE-502)
- XML External Entity Injection (CWE-611)
- Command Injection (CWE-78)
- Path Traversal (CWE-22)
- Weak Cryptography (CWE-327, CWE-328)
- Hardcoded Credentials (CWE-798)
- Information Exposure (CWE-200)
- Insufficient Transport Layer Security (CWE-319)
- Use of Hard-coded Password (CWE-259)

## Reproducing These Scans

The binaries used in these scans are compiled artifacts from the open-source projects linked above. To reproduce:

1. Clone the source repository
2. Build the project following its build instructions
3. Scan the resulting binary with Proscan's binary scanner

## Links

- Website: [proscan.one](https://proscan.one)
- Documentation: [Proscan-hub/docs](https://github.com/Proscan-hub/docs)
- Contact: [contact@proscan.one](mailto:contact@proscan.one)
