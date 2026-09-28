# Security Validation & Regression Testing

## Objective
To determine whether the implemented security improvements successfully mitigate the identified risks without breaking required application functionality.

## Validation Strategy
The validation phase employed a combination of automated regression testing and manual verification to confirm the effectiveness of the remediations.

- **Access-Control Retesting**: Re-evaluating previously vulnerable endpoints to ensure RBAC and object-level authorization strictly deny unauthorized actions.
- **Bandit (SAST)**: Rerunning static analysis to confirm the removal of hardcoded secrets and insecure configurations.
- **pip-audit (SCA)**: Rerunning dependency checks to ensure known vulnerabilities were successfully patched.
- **OWASP ZAP (DAST)**: Scanning the updated local deployment to verify the presence of security headers and monitor for new dynamic vulnerabilities.
- **Burp Suite (Manual Validation)**: Intercepting web requests to manually validate authorization boundaries, access-control behaviour, and security verification.

### Manual Validation Evidence
Burp Suite was instrumental in manually confirming that the application correctly enforced access-control boundaries.

**Burp Suite Access Control Validation:**
![Burp Access Control Validation 1](../screenshots/14-burp-access-control(1).png)
![Burp Access Control Validation 2](../screenshots/14-burp-access-control(2).png)

### Automated Security Pipeline
To demonstrate DevSecOps principles, an automated security-testing workflow was established to integrate security checks earlier into the development lifecycle.

**Final Automated Security Pipeline:**
![Automated Security Pipeline](../screenshots/15-security-pipeline-final.png)

## Residual Risk and Limitations
- **Local Testing**: The application was assessed locally over HTTP. HTTPS-dependent controls (like `Secure` cookies) could not be fully validated and require a real HTTPS deployment.
- **CSP Tuning**: CSP-related observations remained during later OWASP ZAP validation. These require further policy refinement and production validation.
- **Scanner Limitations**: Security scanners provide evidence about the conditions they test. A clean scanner result (like Bandit or pip-audit) does not prove that an application is completely secure against logic flaws or zero-day vulnerabilities.
- **Scope**: This validation confirms the security of the local academic copy against the identified threats, but does not represent a professional penetration test or exploitation of a production system.
