# rastabasta another pentesting tool
# RastaBasta - Simplified Ethical Reconnaissance Toolkit

RastaBasta is a direct and efficient Python-based ethical hacking tool designed to quickly perform reconnaissance and information gathering against target domains. It streamlines the process of running popular open-source intelligence (OSINT), DNS enumeration, network scanning, and web application analysis tools with a focus on immediate execution and clear feedback.

Forget complex configurations and deep menus. RastaBasta provides a highly focused interface, allowing you to:

* Install Essential Tools: Easily install required penetration testing tools directly from the application.
* Target and Execute: Specify a domain or subdomain, choose a specific tool (or run all installed tools), and execute.
* Choose Your Mode: Run scans in "Safe Mode" (stealthy with increased delays) or "Fuck it mode" (normal speed).
* Automated Reporting: All scan outputs are automatically saved into organized .txt reports within domain-specific directories for easy review.

RastaBasta is built for ethical testers who value straightforward functionality and actionable results, cutting down on setup time to get straight to the reconnaissance.

## Features

* Direct Execution Flow: Minimal menu navigation; get straight to running tools against your target.
* Tool Management: Install individual tools with cross-distribution support (apt, dnf, yum, pacman, brew, pip, snap).
* Flexible Targeting: Specify a single domain or subdomain for immediate scanning.
* "All Tools" Option: Run all currently installed and applicable tools against your target with one command.
* Execution Modes: Toggle between "Safe Mode" (increased delays) and "Fuck it mode" (standard delays).
* Automated .txt Reporting: All tool outputs are automatically saved to scan_reports/ as .txt files in domain-specific subdirectories.
* Robust Error Handling: Clear, actionable messages for installation failures and command execution issues, with automatic retries.
* Security Focus: Input sanitization using shlex.quote prevents command injection.

## Supported Tools

RastaBasta integrates a variety of command-line tools. The tool definitions, including their installation commands for different package managers, are loaded from tools.json.

Examples of integrated tools:
* dig (DNS query)
* nslookup (DNS lookup)
* nmap (Port scanning)
* whatweb (Web technology detection)
* Sublist3r (Subdomain enumeration)
* theHarvester (OSINT for emails/subdomains)
* dirb / gobuster (Directory brute-forcing)
* sslscan / testssl.sh (SSL/TLS analysis)
* whois (Domain information)
* shodan (Device search - requires API key)
* And more...

(The full list and their details are in tools.json.)

## Installation

1.  Clone the repository:
    ```bash
    git clone [https://github.com/rastabastaNL/RastaBasta-Pentest-Tool.git](https://github.com/rastabastaNL/RastaBasta-Pentest-Tool.git) /rastabasta
    cd /rastabasta
    ```

2.  Install Python Dependencies:
    ```bash
    pip3 install -r requirements.txt
    ```
    (The requirements.txt file ensures you have necessary Python libraries like colorama and dnspython.)

3.  Make the script executable:
    ```bash
    chmod +x rastabasta.py
    ```

4.  Run the script:
    ```bash
    ./rastabasta.py
    ```
    * First Run: The script will automatically create rastabasta.conf (for settings) and rastabasta.log (for activity logging) if they don't exist.
    * Crucially, if tools.json is not found, the script will create a default tools.json file for you on the first run. Please review its content, as it defines the tools RastaBasta uses.

## Usage

Upon running the script, you will be presented with a simple main menu:
