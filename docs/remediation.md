# Remediation Matrix

The following table summarizes the key security areas addressed during the assessment, the corresponding remediations applied, and the method used to validate the outcome.

| Security Area | Before Remediation | Remediation Applied | Validation Method | Outcome |
|---|---|---|---|---|
| **Access Control (Registration)** | Registration endpoint publicly reachable, allowing arbitrary account creation. | Restricted user registration exclusively to authenticated administrators. | Manual Testing (Burp Suite) | Unauthorized registration attempts denied. |
| **Access Control (RBAC)** | Employees could potentially access administrative views and functions. | Applied robust Role-Based Access Control (RBAC) to privileged application routes. | Manual Testing (Burp Suite) | Unauthorized employee access returns HTTP 403 Forbidden. |
| **Object-Level Authorization** | Object-level authorization behavior required validation. | Protected object access was included in authorization testing. | Manual Testing (Burp Suite) | Access to unauthorized objects denied (HTTP 404/403). |
| **Secrets Management** | Sensitive values (Django `SECRET_KEY`, Database credentials) hardcoded in source. | Extracted secrets to environment variables. | SAST (Bandit) | Hardcoded secrets removed from source code; Bandit reports clean. |
| **Debug Configuration** | Django `DEBUG` mode enabled, leaking internal stack traces on errors. | Disabled `DEBUG` mode; secured error handling. | Manual Request Inspection | Stack traces no longer exposed to clients. |
| **Dependency Vulnerabilities** | Python packages contained known vulnerabilities. | Upgraded packages to secure versions. | SCA (pip-audit) | `pip-audit` reports no known vulnerabilities. |
| **HTTP Security Headers** | Missing headers (e.g., CSP) leaving clients exposed to injection attacks. | Configured security headers including Content Security Policy. | DAST (OWASP ZAP) | Headers present; further policy refinement may be required. |
