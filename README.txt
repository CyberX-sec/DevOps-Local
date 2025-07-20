DevOps-Local

A purposely vulnerable web application project designed for security testing, DevOps pipeline practice, and static analysis tool demonstrations.
Table of Contents

    Overview
    Key Features & Vulnerabilities
    Setup Instructions
    Security & Static Analysis Tools
    How to Scan
    Notes
    Next Steps

Overview

This project includes:

    A Python-based web application with an SQLite database.
    Intentionally introduced vulnerabilities for educational and testing purposes.
    A bash script for automated security and static analysis tool execution.
    All required tools and dependencies bundled or referenced for local use.

Key Features & Vulnerabilities

The web application intentionally contains several common security flaws to facilitate learning and tool testing, including:

    Broken Access Control: Admin page accessible without authentication checks.
    Cross-Site Scripting (XSS): User input not properly sanitized.
    Logic Flaws: Application logic is deliberately insecure.
    Plaintext Password Storage: User credentials stored in cleartext.
    Missing CSRF Protection: Forms lack CSRF tokens.
    Weak Session Key: Hardcoded, short session secret.
    No Input Validation: User inputs are not validated.

Setup Instructions

    Clone the repository:
    sh

git clone https://github.com/CyberX-sec/DevOps-Local.git
cd DevOps-Local

Install Python dependencies:
sh

    pip install -r requirements.txt

    Install security tools (if not already installed):
        Most tools can be installed with pip or npm as needed.

    Ensure gitleaks.exe is present in the project directory.
        This is required for secret scanning and should be run directly (not via PATH).

Security & Static Analysis Tools

The following tools are set up to scan the project for issues:

Security Tools

    bandit: Scan Python code for common security issues.
    snyk: Scan dependencies in requirements.txt for known vulnerabilities.
    gitleaks: Scan repository history and code for secrets like API keys and passwords.

Static Analysis Tools (SAST)

    pyright: Check Python code for type errors.
    pylint: Analyze code for errors, bad practices, and style issues.
    flake8: Enforce PEP8 coding style.

How to Scan

    Install all dependencies and tools.

    Run the scan script using PowerShell (in VS Code terminal or similar):
    sh

.\scan.ps1

    This will execute all the security and static analysis tools automatically.

Snyk authentication:
Before using Snyk for the first time, authenticate with:
sh

    snyk auth

Notes

    The requirements.txt was generated with:
    sh

    pip freeze > requirements.txt

    gitleaks.exe must be present in the project directory; running it directly is required as it's not added to the system PATH.
    The web application is intentionally insecure and should not be deployed in a production environment.

Next Steps

Once you’ve built and tested your CI/CD pipeline using this intentionally vulnerable app, the plan is to refactor and create a stable, security-hardened version.
Contribution

Feel free to open issues or submit pull requests for improvements or new security scenarios.

CyberX-sec Team

Let me know if you’d like to add badges, deployment instructions, or CI/CD sample configurations!
