# Proscan Scan Results

Real scan results from [Proscan](https://proscan.one) against deliberately vulnerable applications. These are actual scanner outputs — not fabricated examples.

All targets are well-known open-source vulnerable-by-design projects maintained by OWASP and the security community.

> **Note:** These are basic comprehensive reports demonstrating Proscan's scanning capabilities. They provide a high-level overview of detected vulnerabilities with severity, CWE classification, and compliance mapping. For in-depth detailed analysis including taint tracking, call graph visualization, and remediation guidance with code examples, use the full Proscan platform.

---

## SAST — Static Application Security Testing

60 open-source vulnerable applications scanned with Proscan's SAST engine across 10+ programming languages.

**[Browse SAST Reports →](sast/)**

| Language | Projects |
|----------|----------|
| Java | JavaVulnerableLab, WebGoat, WebGoat-Legacy, WebGoat-BBP, dvja, java-goof, VulnerableApp, juice-shop-ctf |
| JavaScript/TypeScript | juice-shop, NodeGoat, dvna, dvna-2, dvws-node, nodejs-goof, vulnerable-node, vuln-javascript-app, vuln-typescript-app |
| Python | DSVW, django.nV, dvga, dvpwa, Vulnerable-Flask-App, vuln-python-app, python-docs-samples |
| PHP | DVWA, DVWA-2, dvws, hackazon, vapi, vuln-php-app |
| Go | govwa, vuln-go-app, kubernetes-goat, huskyCI, kics |
| Ruby | railsgoat, vuln-ruby-app, dawnscanner |
| C# | vuln-csharp-app |
| Kotlin | vuln-kotlin-app |
| Multi-language | vuln-multi-lang, vuln-light-app, secDevLabs, vulhub, vuln-code-snippets |
| IaC/Cloud | cfngoat, terragoat |
| Mobile | mastg, diva-android, hackazon, vapi |

Each project directory contains:
- `comprehensive-report.html` — full scan report with findings and remediation
- `compliance-owasp-top10.json` — OWASP Top 10 compliance assessment
- `compliance-pci-dss.json` — PCI DSS 4.0 compliance assessment
- `compliance-nist-800-53.json` — NIST 800-53 Rev 5 compliance assessment

---

## Binary Analysis

15 vulnerable applications scanned with Proscan's binary scanner. 156 binaries analyzed across JVM (JAR/WAR), Go (ELF/PE), and Android (APK/DEX) formats.

**[Browse Binary Analysis Reports →](binary-analysis/)**

| Metric | Value |
|--------|-------|
| Total binaries scanned | 156 |
| Total findings | 1,190 |
| Scan errors | 0 |

| Project | Type | Findings | Source |
|---------|------|----------|--------|
| [JavaVulnerableLab](binary-analysis/reports/JavaVulnerableLab/) | Java WAR | 25 (11 crit) | [GitHub](https://github.com/CSPF-Founder/JavaVulnerableLab) |
| [VulnerableApp](binary-analysis/reports/VulnerableApp/) | Java JAR | 43 (17 crit) | [GitHub](https://github.com/SasanLabs/VulnerableApp) |
| [DVJA](binary-analysis/reports/dvja/) | Java WAR + JARs | Multiple | [GitHub](https://github.com/appsecco/dvja) |
| [java-goof](binary-analysis/reports/java-goof/) | Java WAR + JARs | Multiple | [GitHub](https://github.com/snyk/java-goof) |
| [log4shell-vuln-app](binary-analysis/reports/log4shell-vuln-app/) | Java JAR | Log4Shell | [GitHub](https://github.com/christophetd/log4shell-vulnerable-app) |
| [govwa](binary-analysis/reports/govwa/) | Go binary | Go vulns | [GitHub](https://github.com/0c34/govwa) |
| [vuln-go-app](binary-analysis/reports/vuln-go-app/) | Go binary | Go vulns | [GitHub](https://github.com/Contrast-Security-OSS/go-test-bench) |
| [kubernetes-goat](binary-analysis/reports/kubernetes-goat/) | Go binaries | K8s security | [GitHub](https://github.com/madhuakula/kubernetes-goat) |
| [OWASP MASTG](binary-analysis/reports/mastg/) | Android APKs | Mobile | [GitHub](https://github.com/OWASP/owasp-mastg) |
| [vulhub](binary-analysis/reports/vulhub/) | Java WARs | Struts2 | [GitHub](https://github.com/vulhub/vulhub) |

---

## Understanding Compliance Scores

Compliance scores in these reports reflect **detection coverage** — whether Proscan checked for and detected vulnerabilities in each compliance category. They do not represent the application's security posture.

For example, a score on a deliberately vulnerable app means Proscan tested all the relevant categories and found (or did not find) vulnerabilities in each. The comprehensive HTML report shows the actual findings with severity, CWE, and remediation guidance.

A compliance audit requires both automated evidence (what Proscan provides) and manual assessment by a qualified auditor.

---

## Vulnerability Types Detected

Across all scans, Proscan detected vulnerabilities including:

- SQL Injection (CWE-89)
- Cross-Site Scripting — Reflected, Stored, DOM (CWE-79)
- Command Injection (CWE-78)
- Server-Side Request Forgery (CWE-918)
- Insecure Deserialization (CWE-502)
- XML External Entity Injection (CWE-611)
- Path Traversal (CWE-22)
- Weak Cryptography (CWE-326, CWE-327, CWE-328)
- Hardcoded Credentials (CWE-798)
- Information Exposure (CWE-200)
- Cross-Site Request Forgery (CWE-352)
- Unrestricted File Upload (CWE-434)
- Open Redirect (CWE-601)
- Log Injection (CWE-117)

---

## Reproducing These Scans

All scanned projects are open source. To reproduce:

1. Clone the source repository from the links above
2. For SAST: point Proscan at the source code directory
3. For binary analysis: build the project and scan the resulting artifacts

---

## Links

- Website: [proscan.one](https://proscan.one)
- Documentation: [Proscan-hub/docs](https://github.com/Proscan-hub/docs)
- Contact: [contact@proscan.one](mailto:contact@proscan.one)
