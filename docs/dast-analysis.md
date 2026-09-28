# Dynamic Application Security Testing (DAST)

## Objective
To assess the running application for security vulnerabilities, misconfigurations, and behavioural flaws that only manifest during runtime.

## Tool
**OWASP ZAP** (Zed Attack Proxy): An integrated DAST tool for finding vulnerabilities in web applications.

## Local Testing Scope
The application was assessed locally. Testing focused on spidering and actively scanning the local HTTP deployment to identify potential weaknesses in HTTP responses, session management, and headers.

## Observations
The initial assessment identified several issues, including:
- Content Security Policy (CSP) observations.
- Cookie security attribute observations (e.g., missing Secure flags).
- Unnecessary server information disclosure.

**Initial ZAP Observations:**
![ZAP before remediation 1](../screenshots/13-zap-before(1).png)
![ZAP before remediation 2](../screenshots/13-zap-before(2).png)

## Remediation
Remediation efforts focused on hardening HTTP responses and configuration, notably adding missing security headers to mitigate client-side risks.

## Retesting
The application was rescanned with OWASP ZAP to validate the configuration changes. 

## Remaining CSP Observations
The original assessment documented that some CSP-related observations remained during later validation. This is expected as CSP often requires iterative tuning. Full mitigation may require:
- Broader response coverage.
- Policy refinement.
- Production validation.

## HTTPS/Local-Environment Limitations
Because the testing environment utilized local HTTP, HTTPS-dependent controls could not be fully validated by the scanner. Certain observations (like missing `Secure` attributes on cookies) are expected when testing over unencrypted HTTP and require validation under a real HTTPS deployment. Scanner alerts provide evidence about the conditions they test; a clean or noisy scanner result does not unilaterally prove or disprove complete application security without contextual analysis.
