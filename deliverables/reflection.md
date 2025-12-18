System-Level SBOM and Vulnerability Analysis Reflection
The system-level Software Bill of Materials (SBOM) generated for the Ubuntu Linux Codespace environment identified 1,946 installed packages, highlighting the size and complexity of the operating system’s software supply chain. A vulnerability analysis using Grype revealed a significant number of known vulnerabilities across system components, including 9 critical, 56 high, 1,865 medium, 196 low, and 24 negligible severity vulnerabilities. These findings demonstrate that even widely used and standardized base environments contain a large potential attack surface if not continuously monitored and maintained.
One notable vulnerability identified was CVE-2023-45288, which affects the Go standard library (stdlib) in version go1.19.2. According to the National Vulnerability Database (NVD), this vulnerability allows improper handling of certain inputs within the Go runtime, which could lead to unexpected behavior or security issues in applications compiled with vulnerable versions of Go. This example illustrates how system-level SBOM visibility enables identification of inherited risks from language runtimes and reinforces the importance of regular patching and verification to support complete mediation and defense-in-depth principles in secure system operations.
After refreshing the package index using sudo apt update, the command sudo apt list --upgradable identified 14 packages with available updates in the Ubuntu Codespace environment. Three representative packages with pending updates are listed below:
binutils
 Current version: 2.38-4ubuntu2.10
 Target version: 2.38-4ubuntu2.12


libpng16-16
 Current version: 1.6.37-3build5
 Target version: 1.6.37-3ubuntu0.1


python3.10
 Current version: 3.10.12-1~22.04.11
 Target version: 3.10.12-1~22.04.12


These updates include system utilities, core libraries, and language runtimes, indicating that security and stability improvements are available for critical components of the operating environment. The presence of upgradable packages demonstrates the need for regular patching as part of maintaining assurance and enforcing continuous verification in secure system operations.
REFLECTION
How does maintaining updated packages illustrate complete mediation?
 Maintaining updated packages illustrates complete mediation by ensuring that all system components are continuously re-evaluated and verified rather than implicitly trusted. Applying updates forces the operating system to re-check each package against known vulnerabilities and security fixes, ensuring access and execution are governed by current security controls rather than outdated assumptions.
Why is generating a new SBOM after patching essential to assurance?
 Generating a new SBOM after patching is essential because it provides an updated and accurate inventory of the system’s software components and their versions. Without regenerating the SBOM, security assessments would be based on stale data, undermining assurance and making it difficult to verify whether vulnerabilities were actually mitigated.
What risks persist when organizations delay system updates?
 When organizations delay system updates, known vulnerabilities remain exploitable, increasing the risk of privilege escalation, denial of service, or remote code execution. Attackers frequently target unpatched systems because the weaknesses are publicly documented and often easy to exploit.
How does this exercise embody the secure design lifecycle principle?
 This exercise embodies the secure design lifecycle by demonstrating that security does not end at deployment but requires continuous monitoring, verification, and maintenance. By combining SBOM generation, vulnerability scanning, patching, and post-update validation, the process reinforces security as an ongoing operational responsibility rather than a one-time design task.

