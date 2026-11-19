# Week 3 – Password Cracking Practical (Combined): JTR/Johnny + NetworkWalks Browser Tools

![Status](https://img.shields.io/badge/Status-Educational%20Lab-success)
![Tool](https://img.shields.io/badge/Tool-John%20the%20Ripper-black)
![Tool](https://img.shields.io/badge/Tool-NetworkWalks%20Tools-red)

A single write-up treating **two different approaches to the same password-auditing task** as one combined practical: recovering the password of a protected PDF, first using locally installed tooling (**John the Ripper + Johnny**), then using **NetworkWalks' own browser-based tools** (Hash Calculator + Password Cracker) — no installation required.

---

## Table of Contents

1. [Overview](#overview)
2. [Objective](#objective)
3. [Lab Information](#lab-information)
4. [Tools & Technologies](#tools--technologies)
5. [Repository Structure](#repository-structure)
6. [Approach A — Local Auditing with JTR + Johnny](#approach-a--local-auditing-with-jtr--johnny)
7. [Approach B — Browser-Based Auditing with NetworkWalks Tools](#approach-b--browser-based-auditing-with-networkwalks-tools)
8. [Approach Comparison](#approach-comparison)
9. [Screenshot Evidence](#screenshot-evidence)
10. [Result](#result)
11. [Learning Outcomes](#learning-outcomes)
12. [Security Insights](#security-insights)
13. [Ethical Disclaimer](#ethical-disclaimer)
14. [References](#references)
15. [Author](#author)

---

## Overview

Both approaches tackle the identical underlying task — recover the password of a locked PDF — but represent two different skill sets:

- **Approach A** uses locally installed, industry-standard tooling (John the Ripper, driven through the Johnny GUI) — the kind of workflow a security professional would use on their own machine.
- **Approach B** uses NetworkWalks' own browser-based Hash Calculator and Password Cracker — no installation needed, suited to any computer.

Documenting them together makes the comparison explicit: the *concept* (extract a hash, attack it with a wordlist, verify the result) is identical; only the tooling differs.

## Objective

- Recover the password of a protected lab PDF using two independent methods.
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
| Both | Target PDF | Password-protected lab file (`My Locked PDF1.pdf`) |

## Repository Structure

```text
NETWORKWALKS-B084J-WK3-PASSWORD-AUDITING/
│
├── README.md
│
├── Module-1-JTR-Johnny/
│   └── screenshots/
│       └── (Approach A screenshots)
│
├── Module-2-NetworkWalks-Tools/
│   └── screenshots/
│       └── (Approach B screenshots)
│
└── PDF/
    └── My Locked PDF1.pdf
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

Evidence for each approach is organized under its own `screenshots/` folder (see [Repository Structure](#repository-structure)), grouped as:

- Setup / tool access
- Hash extraction
- Attack execution
- Result & verification

## Result

Both approaches successfully recovered the password of the protected lab PDF, confirmed by reopening the file. Flags captured across the combined practical:

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
