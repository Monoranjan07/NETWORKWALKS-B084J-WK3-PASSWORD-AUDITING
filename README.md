# Week 3 – Password Cracking Practical (Combined): JTR/Johnny + NetworkWalks Browser Tools

![Status](https://img.shields.io/badge/Status-Educational%20Lab-success)
![Tool](https://img.shields.io/badge/Tool-John%20the%20Ripper-black)
![Tool](https://img.shields.io/badge/Tool-NetworkWalks%20Tools-red)
[![Watch the video](https://img.shields.io/badge/LinkedIn-Watch%20the%20video-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/feed/update/urn:li:activity:7529288882555809792/)

A single write-up treating **two different approaches to the same password-auditing task** as one combined practical: recovering the password of protected PDFs, first using locally installed tooling (**John the Ripper + Johnny**), then using **NetworkWalks' own browser-based tools** (Hash Calculator + Password Cracker) — no installation required.

---

## Table of Contents

1. [Video Walkthrough](#video-walkthrough)
2. [Overview](#overview)
3. [Objective](#objective)
4. [Lab Information](#lab-information)
5. [Tools & Technologies](#tools--technologies)
6. [Repository Structure](#repository-structure)
7. [Approach A — Local Auditing with JTR + Johnny](#approach-a--local-auditing-with-jtr--johnny)
8. [Approach B — Browser-Based Auditing with NetworkWalks Tools](#approach-b--browser-based-auditing-with-networkwalks-tools)
9. [Approach Comparison](#approach-comparison)
10. [Screenshot Evidence](#screenshot-evidence)
11. [Result](#result)
12. [Learning Outcomes](#learning-outcomes)
13. [Security Insights](#security-insights)
14. [Ethical Disclaimer](#ethical-disclaimer)
15. [References](#references)
16. [Author](#author)

---

## Video Walkthrough

A recorded walkthrough of this practical is posted on LinkedIn:

[![Watch on LinkedIn](https://img.shields.io/badge/▶%20Watch%20the%20walkthrough-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/feed/update/urn:li:activity:7529288882555809792/)

> 🔗 [https://www.linkedin.com/feed/update/urn:li:activity:7529288882555809792/](https://www.linkedin.com/feed/update/urn:li:activity:7529288882555809792/)

## Overview

Both approaches tackle the identical underlying task — recover the password of a locked PDF — but represent two different skill sets:

- **Approach A** uses locally installed, industry-standard tooling (John the Ripper, driven through the Johnny GUI) — the kind of workflow a security professional would use on their own machine.
- **Approach B** uses NetworkWalks' own browser-based Hash Calculator and Password Cracker — no installation needed, suited to any computer.

Documenting them together makes the comparison explicit: the *concept* (extract a hash, attack it with a wordlist, verify the result) is identical; only the tooling differs.

## Objective

- Recover the password of protected lab PDFs using two independent methods.
- Understand the shared underlying workflow: hash extraction → dictionary-based attack → verification.
- Compare a locally installed tool-chain against a browser-based one for the same task.
- Document both approaches, with evidence, as a single combined practical.

## Lab Information

| Field | Detail |
|---|---|
| Program | Cybersecurity & Ethical Hacking Internship / Practical Training |
| Organization | NetworkWalks Academy |
| Batch | B084J |
| Week | Week 3 |
| Scope | Combined write-up of Module 1 (JTR/Johnny) + Module 2 (NetworkWalks Tools) |

## Tools & Technologies

| Approach | Tool | Role |
|---|---|---|
| A — Local | [John the Ripper](https://www.openwall.com/john/) | Core password-auditing engine |
| A — Local | [Johnny](https://openwall.info/wiki/john/johnny) | GUI front end for JTR |
| B — Browser | [NetworkWalks Hash Calculator](https://networkwalks.com/hash-calculator/) | Extracts the PDF's password hash |
| B — Browser | [NetworkWalks Password Cracker](https://networkwalks.com/password-cracker/) | Attacks the extracted hash |
| Both | Target PDFs | 4 password-protected lab files in [`PDF/`](NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/PDF) |

## Repository Structure

```text
NETWORKWALKS-B084J-WK3-PASSWORD-AUDITING/
│
├── README.md
│
└── NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/
    │
    ├── PDF/
    │   ├── My Locked PDF1.pdf
    │   ├── My Locked PDF1 (for NW Tools Lab WK3-PM2).pdf
    │   ├── My Locked PDF2.pdf
    │   └── My Locked PDF3.pdf
    │
    └── SS/
        └── (26 screenshots — see Screenshot Evidence below)
```

## Approach A — Local Auditing with JTR + Johnny

1. Download John the Ripper and Johnny; install Johnny and point it at `john.exe`.
2. Download the protected PDF to the PC.
3. Extract the PDF's password hash (e.g. via an online PDF-hash extractor), save it as `hash1.txt`.
4. In Johnny, open the hash file and click **Start new attack**.
5. Once cracked, use the recovered password to reopen the PDF and confirm it works.

## Approach B — Browser-Based Auditing with NetworkWalks Tools

1. Download the protected PDF from the NetworkWalks lab page.
2. Open the NetworkWalks **Hash Calculator**, upload the PDF, and generate its hash (`$pdf$...` format).
3. Copy the hash and paste it into the NetworkWalks **Password Cracker**; start the recovery.
4. Once the password is returned, use it to reopen the PDF and confirm it works.

## Approach Comparison

| Aspect | Approach A (JTR + Johnny) | Approach B (NetworkWalks Tools) |
|---|---|---|
| Installation required | Yes (JTR + Johnny) | No — browser only |
| Where it runs | Local machine | Any device with a browser |
| Interface | Johnny GUI over JTR engine | NetworkWalks web tools |
| Skill transfer | Mirrors real-world local tooling | Beginner-friendly, concept-first |
| Underlying method | Hash extraction → dictionary attack → verify | Same: hash extraction → attack → verify |

## Screenshot Evidence

All 26 screenshots from the practical, in chronological order (click any image to open it full-size on GitHub):

<table>
<tr>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20014535.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20014535.png" width="200"/></a><br/><sub>2026-11-16 014535</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20015330.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20015330.png" width="200"/></a><br/><sub>2026-11-16 015330</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20020842.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20020842.png" width="200"/></a><br/><sub>2026-11-16 020842</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20021923.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20021923.png" width="200"/></a><br/><sub>2026-11-16 021923</sub></td>
</tr>
<tr>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022003.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022003.png" width="200"/></a><br/><sub>2026-11-16 022003</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022040.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022040.png" width="200"/></a><br/><sub>2026-11-16 022040</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022211.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022211.png" width="200"/></a><br/><sub>2026-11-16 022211</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022325.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022325.png" width="200"/></a><br/><sub>2026-11-16 022325</sub></td>
</tr>
<tr>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022428.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022428.png" width="200"/></a><br/><sub>2026-11-16 022428</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022501.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022501.png" width="200"/></a><br/><sub>2026-11-16 022501</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022535.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022535.png" width="200"/></a><br/><sub>2026-11-16 022535</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022948.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20022948.png" width="200"/></a><br/><sub>2026-11-16 022948</sub></td>
</tr>
<tr>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20023009.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20023009.png" width="200"/></a><br/><sub>2026-11-16 023009</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20023138.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20023138.png" width="200"/></a><br/><sub>2026-11-16 023138</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20023154.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20023154.png" width="200"/></a><br/><sub>2026-11-16 023154</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20024811.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20024811.png" width="200"/></a><br/><sub>2026-11-16 024811</sub></td>
</tr>
<tr>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20024857.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20024857.png" width="200"/></a><br/><sub>2026-11-16 024857</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20025526.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20025526.png" width="200"/></a><br/><sub>2026-11-16 025526</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20025615.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20025615.png" width="200"/></a><br/><sub>2026-11-16 025615</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20025641.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-16%20025641.png" width="200"/></a><br/><sub>2026-11-16 025641</sub></td>
</tr>
<tr>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-20%20013958.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-20%20013958.png" width="200"/></a><br/><sub>2026-11-20 013958</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-20%20014047.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-20%20014047.png" width="200"/></a><br/><sub>2026-11-20 014047</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-20%20014122.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-20%20014122.png" width="200"/></a><br/><sub>2026-11-20 014122</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-20%20014213.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-20%20014213.png" width="200"/></a><br/><sub>2026-11-20 014213</sub></td>
</tr>
<tr>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-20%20014239.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-20%20014239.png" width="200"/></a><br/><sub>2026-11-20 014239</sub></td>
<td align="center"><a href="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-20%20014533.png"><img src="NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS/Screenshot%202026-11-20%20014533.png" width="200"/></a><br/><sub>2026-11-20 014533</sub></td>
<td></td>
<td></td>
</tr>
</table>

Didn't load above, or want the full-resolution originals? Open the folder directly:

[![Open screenshots folder](https://img.shields.io/badge/📁%20Open-SS%20folder%20on%20GitHub-blue?style=for-the-badge)](https://github.com/Monoranjan07/NETWORKWALKS-B084J-WK3-PASSWORD-AUDITING/tree/main/NETWORKWALKS-B084J-WK3-JTR-PASSWORD-AUDIT-main/SS)

## Result

Both approaches successfully recovered the password of the protected lab PDFs, confirmed by reopening the files. Flags captured across the combined practical:

```text
nw{networkwalks_flag_260821_1}
nw{cybersecurity_flag_captured_2608}
nw{networkwalks_flag1_jtr_270521_1}
nw{networkwalks_persistence_jtr_270521}
```

## Learning Outcomes

- Practical exposure to password auditing via two distinct tool stacks.
- Clear understanding of the shared concept underlying both: hash extraction, dictionary-based attack, verification.
- Comparative insight into when local tooling vs. browser-based tooling is more appropriate.
- Reinforced understanding of the `$pdf$` hash format and why hashing ≠ encryption.
- Strengthened documentation and evidence-based writeup skills.

## Security Insights

- Weak passwords fall quickly regardless of which tool stack is used to test them — the vulnerability is in the password, not the tool.
- Browser-based tools lower the barrier to password auditing, which cuts both ways: useful for defenders, but a reminder that attackers face a similarly low barrier.
- Strong, unique passwords plus MFA remain the real mitigation, independent of which cracking approach is demonstrated.

## Ethical Disclaimer

Both practicals were conducted for educational purposes within an authorized NetworkWalks training environment. Password auditing and recovery tools shown here should only be used against files, systems, and data you have explicit permission to test. This repository does not present or endorse unauthorized password cracking.

## References

- John the Ripper: [https://www.openwall.com/john/](https://www.openwall.com/john/)
- Johnny: [https://openwall.info/wiki/john/johnny](https://openwall.info/wiki/john/johnny)
- NetworkWalks Hash Calculator: [https://networkwalks.com/hash-calculator/](https://networkwalks.com/hash-calculator/)
- NetworkWalks Password Cracker: [https://networkwalks.com/password-cracker/](https://networkwalks.com/password-cracker/)
- NetworkWalks Academy: [https://networkwalks.com/](https://networkwalks.com/)

## Author

**Monoranjan Banik**
Cybersecurity Student — NetworkWalks Cybersecurity & Ethical Hacking Program (Batch B084J)

- GitHub: [monoranjan07](https://github.com/monoranjan07)
- Repository: [NETWORKWALKS-B084J-WK3-PASSWORD-AUDITING](https://github.com/Monoranjan07/NETWORKWALKS-B084J-WK3-PASSWORD-AUDITING)
- LinkedIn: [monoranjan-banik](https://www.linkedin.com/in/monoranjan-banik-3a0092335/)
- Video walkthrough: [LinkedIn post](https://www.linkedin.com/feed/update/urn:li:activity:7529288882555809792/)
