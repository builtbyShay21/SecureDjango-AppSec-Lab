# Static Application Security Testing (SAST)

## Objective
To identify insecure coding patterns and vulnerabilities within the application source code without executing it.

## Tool
**Bandit**: A security linter specifically designed for Python code.

## Initial Scan
The original Bandit assessment identified security-sensitive configurations, specifically flagging issues related to hardcoded secrets. 

## Findings
The initial scan identified findings centered around security-sensitive configuration, such as:
- Hardcoded Django `SECRET_KEY`.
- Database password and configuration stored directly in source files.

**Initial Bandit Findings:**
![Bandit before remediation](../screenshots/09-bandit-before.png)

## Remediation
Configuration secrets were extracted from the codebase and migrated to environment variables (e.g., using `python-dotenv`).

## Post-Remediation Validation
Bandit reported no remaining issues in the post-remediation scan.

**Post-Remediation Bandit Results:**
![Bandit after remediation](../screenshots/10-bandit-after.png)

## Evidence
Artifacts related to the SAST process are documented in `security-artifacts/sast/`.

## Limitations
Bandit only represents one form of static analysis for Python applications. A clean Bandit report does not guarantee the absence of all vulnerabilities, particularly logic flaws, authorization issues, or runtime vulnerabilities that SAST tools cannot detect.
