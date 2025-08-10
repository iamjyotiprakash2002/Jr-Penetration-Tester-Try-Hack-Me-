# Jr-Penetration-Tester-Try-Hack-Me-
Professional penetration testing write-ups for Try Hack Me labs and challenges I have completed, following a structured methodology (Reconnaissance, Enumeration, Exploitation, Privilege Escalation).

Offensive Security Intro – Write-Up
📌 Overview
This lab introduces the fundamentals of offensive security by allowing the user to legally hack a vulnerable website in a controlled environment. The objective is to gain hands-on experience in identifying and exploiting web vulnerabilities while understanding the mindset and methodology of an ethical hacker.

🛠 Methodology
1️⃣ Reconnaissance
Goal: Gather publicly available information about the target environment before active testing.
Approach: Since this was a simulated TryHackMe web challenge, I began with passive reconnaissance — simply browsing the application’s interface to understand its structure.

Why: In a real engagement, this helps avoid triggering alerts early on.

Observations: Multiple pages (Home, Login, About) and a contact form. No obvious admin panel in the visible navigation.

2️⃣ Enumeration
Goal: Actively discover potential vulnerabilities and hidden resources.
Tools: Browser Developer Tools, page source viewing.

Checked HTML source for comments, hidden form fields, or unused parameters.

Noted query strings such as ?id=1 which could be vulnerable to parameter tampering.

Why: Parameters often lead to injection vulnerabilities or hidden functionality.

3️⃣ Exploitation
Vulnerability: SQL Injection on the id parameter.
Process:

Tested the parameter with ' OR '1'='1 and noticed abnormal behavior (all records displayed).

Used a manual exploitation approach to confirm database extraction potential.

Why manual over automated tools? In an introductory lab, manual testing reinforces understanding and keeps control over the payloads used.

4️⃣ Privilege Escalation
Leveraged SQL Injection to enumerate user credentials from the database.

Logged in as an admin account, granting access to restricted site functionality.

Why: This mirrors a common real-world scenario where a low-severity bug becomes high-severity when combined with credential reuse or privilege misuse.

5️⃣ Post-Exploitation
Documented findings: database structure, sensitive data exposed, affected endpoints.

In a real engagement: Would include data exfiltration limits, persistence methods, and clean-up to restore the system to its pre-test state.

🧠 Key Learnings
Web parameters must be validated and sanitized to prevent SQL Injection.

Even in simple environments, following the Recon → Enumeration → Exploitation flow leads to systematic vulnerability discovery.

Manual testing builds intuition that complements automated tools like sqlmap.
