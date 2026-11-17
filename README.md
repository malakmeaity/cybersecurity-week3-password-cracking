**Password Cracking Lab — John the Ripper & Networkwalks Tools**

**Author**: Malak Meaity
**Program**: Networkwalks Cybersecurity & Ethical Hacking — Week 3

Overview

This repo documents two hands-on password-cracking exercises completed as part of a Cybersecurity & Ethical Hacking training program (Week 3 Project Modules, Networkwalks Academy). The goal was to recover the password of an encrypted PDF file (My Locked PDF1.pdf) using two different approaches:

1. John the Ripper (JTR) + Johnny GUI — a classic offline password-auditing tool.
2. Networkwalks Hash Calculator + Password Cracker — free browser-based tools that replicate the same pdf2john/dictionary-attack workflow without installing anything.

⚠️ Disclaimer: This was performed in a controlled training lab on a file provided for that purpose. Password cracking should only ever be done on files/systems you own or have explicit written permission to test.

**Module 1 — Password Cracking with JTR (John the Ripper + Johnny)**

Tools: John the Ripper, Johnny (GUI), Online Hash Extractor

**Steps performed:**

1. Downloaded John the Ripper and the Johnny GUI for Windows.
2. Installed Johnny and pointed it to john.exe under Settings.
3. Extracted the PDF's crackable hash using an online pdf2john-style extractor.
4. Saved the hash (starting with $pdf$...) into a text file (hash1.txt).
5. Opened the hash file in Johnny and ran Start new attack.
6. Johnny recovered the password: password1
7. Used the recovered password to unlock the PDF, revealing Flag 1: nw{networkwalks_flag1_jtr_270521_1}

Screenshot — Johnny after cracking: Johnny cracked password

Screenshot — Flag 1 (JTR method): Flag 1 JTR

**Module 2 — Password Cracking with Networkwalks Tools (No Install Needed)**

Tools: Networkwalks Hash Calculator, Networkwalks Password Cracker

**Steps performed:**

1. Uploaded the locked PDF to the Hash Calculator, which parses the file locally in-browser and extracts a pdf2john/hashcat-compatible hash.
2. Copied the full hash (starting with $pdf$4*4*128*...).
3. Pasted the hash into the Password Cracker, which runs a dictionary attack using a built-in wordlist (same concept as John the Ripper).
4. The tool matched the password after trying a batch of candidates.
5. Opened the PDF with the cracked password and captured the flag:
nw{cybersecurity_flag_captured_2608}

Screenshot — Hash Calculator extracting the PDF hash: Hash Calculator

Screenshot — Online hash extractor output: Online Hash Crack extractor

Screenshot — Flag captured (Networkwalks method): Flag captured

**Key Takeaways**
Password-protected files (PDF, ZIP, Office docs) store a hash of the password, not the password itself — cracking means running candidate words through the same hash function until one matches.
Weak, common, or dictionary-based passwords (e.g. password1) can be cracked in seconds to minutes, even with a small wordlist.
JTR/Johnny represents the "offline tool" workflow security professionals use; the Networkwalks browser tools demonstrate the same concept with zero setup — useful for learning, not for production pentesting.
Strong passwords (length, randomness, mixed character sets) are the main defense against this class of attack.

**Repo Structure**
.
├── README.md
├── docs/
│   ├── W3-PM1_Password_Cracking_with_JTR_v1.pdf
│   └── W3-PM2_Password_Cracking_with_NW_Tools_v1.pdf
└── screenshots/
    ├── johnny-cracked-password.png
    ├── hash-calculator.png
    ├── online-hashcrack.png
    ├── flag1-jtr.png
    └── flag-captured.png
Credits
Lab completed by Malak Meaity
Lab materials and tools by Networkwalks Academy — Cybersecurity & Ethical Hacking training program.
