# Evidence Index

| Filename | Category | What it demonstrates |
|---|---|---|
| 01-dfd-before.png | Threat Modelling | Initial Data Flow Diagram before mitigation. |
| 02-dfd-after.png | Threat Modelling | Mitigated Data Flow Diagram post-remediation. |
| 03-public-registration-before.png | Access Control | The initial state where account registration was publicly reachable. |
| 04-rbac-403-denied.png | Access Control | RBAC enforcement denying unauthorized employee access (403). |
| 05-admin-registration-access.png | Access Control | Restricted registration functionality accessible only to administrators. |
| 06-debug-information-disclosure.png | Configuration | Initial application debug information disclosure. |
| 07-object-authorization-404.png | Access Control | Object-level authorization validation and safe 404 behavior during protected resource testing. |
| 08-csp-header-after.png | Configuration | Validated CSP and security headers post-hardening. |
| 09-bandit-before.png | SAST | Bandit static analysis initial findings. |
| 10-bandit-after.png | SAST | Bandit post-remediation scan with no remaining issues. |
| 11-pip-audit-before.png | SCA | Initial known vulnerabilities in Python dependencies. |
| 12-pip-audit-after.png | SCA | Post-remediation dependency scan with no known vulnerabilities. |
| 13-zap-before(1).png | DAST | Initial dynamic testing observations using OWASP ZAP (1). |
| 13-zap-before(2).png | DAST | Initial dynamic testing observations using OWASP ZAP (2). |
| 14-burp-access-control(1).png | Manual Validation | Burp Suite request inspection and access-control validation (1). |
| 14-burp-access-control(2).png | Manual Validation | Burp Suite request inspection and access-control validation (2). |
| 15-security-pipeline-final.png | Validation | Final automated security testing workflow pipeline. |
