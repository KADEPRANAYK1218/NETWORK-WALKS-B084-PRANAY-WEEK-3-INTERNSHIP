# 🔐 Password Cracking Lab — JTR & NetworkWalks Tools

**Recovering password-protected PDFs' passwords using John the Ripper (Johnny GUI) and the NetworkWalks Hash Calculator / Password Cracker**

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Week-03-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/John%20the%20Ripper-1.9.0--jumbo-E87500?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Skill-Password%20Cracking-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Tool-Johnny%20GUI-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Tool-NetworkWalks%20Hash%20Calculator-C00000?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
</p>

---

## 📌 Project Overview

This project covers **Week 3's two essential project modules** of the NetworkWalks Cybersecurity & Ethical Hacking course:

- **PM1 — Password Cracking with JTR:** recovering three password-protected PDFs' passwords using **John the Ripper (JTR)** via the **Johnny** GUI.
- **PM2 — Password Cracking with NetworkWalks Tools:** recovering the same class of password-protected PDFs using the **NetworkWalks Hash Calculator** and **Password Cracker** web tools.

Both modules use the same underlying idea: a locked PDF's password is stored as a hash, and that hash is extracted and then run through a wordlist-based cracking tool until a match is found.

⚠️ **Important:** These tools and techniques are for educational use only, on files you own or have explicit permission to test.

---

## 🎯 Objectives

- Extract a crackable password hash (`$pdf$...`) from a locked PDF file.
- Use **Johnny** (GUI for John the Ripper) to run a dictionary attack against the hash.
- Use the **NetworkWalks Hash Calculator** to extract the same type of hash from a locked PDF in-browser.
- Use the **NetworkWalks Password Cracker** to run a dictionary attack against that hash.
- Unlock the PDF files using the recovered passwords.
- Document the process, tools, and results.

---

## 🧰 Tools Used

| Tool | Purpose |
|---|---|
| **John the Ripper (JTR) 1.9.0-jumbo-1** | Password cracking engine |
| **Johnny** | GUI front-end for John the Ripper |
| **Online Hash Crack — PDF Hash Extractor** | Converts a locked PDF into a pdf2john/hashcat-compatible `$pdf$...` hash for use with JTR |
| **NetworkWalks Hash Calculator** | Extracts a crackable `$pdf$...` hash from a locked PDF in-browser |
| **NetworkWalks Password Cracker** | Runs a dictionary attack against a `$pdf$...` hash in-browser |

---

## 🪜 PM1 — Password Cracking with JTR

### Step 1. Extract the hash and set up Johnny

Each locked PDF's hash was extracted into `$pdf$...` format using an online pdf2john-style extractor, saved to a text file, and loaded into **Johnny**, which was configured to point to the John the Ripper executable (`john.exe`).

<img width="1902" height="822" alt="image" src="https://github.com/user-attachments/assets/753461b4-8205-4174-8640-5c04b3bdb2d0" />


### Step 2. Run the attack — PDF1

Johnny was used to start a new attack against the loaded hash using its built-in wordlist, and it successfully cracked the password in a single attack run (`1/1 cracked`).

<img width="1890" height="970" alt="image" src="https://github.com/user-attachments/assets/7c2b4e05-2b9a-433f-84be-464042563277" />


<img width="1917" height="962" alt="image" src="https://github.com/user-attachments/assets/2aed86eb-f162-40cd-8391-0e5ed7889ed5" />



*(Password text has been masked above; the PDF was confirmed to open successfully with the recovered password.)*

### Step 3. Run the attack — PDF2

The same flow was repeated for the second locked PDF — hash extracted, loaded into Johnny, attack started.

<img width="1901" height="875" alt="image" src="https://github.com/user-attachments/assets/d90462aa-daac-4e37-b8b2-e0fac4d738f6" />




*(Password text has been masked above.)*

### Step 4. Run the attack — PDF3

The same flow was repeated for the third locked PDF.

<img width="1917" height="1018" alt="image" src="https://github.com/user-attachments/assets/d56f0fc0-1924-4f0d-b2a2-37626dc783c8" />

<img width="1917" height="907" alt="image" src="https://github.com/user-attachments/assets/5c3be646-050c-4e1c-bf4a-9a82e25471de" />

*(Password text has been masked above.)*

### Step 5. PDFs opened

All three PDFs were opened in Google Chrome using their recovered passwords, and each one confirmed with a congratulations/flag page.

<img width="1901" height="965" alt="image" src="https://github.com/user-attachments/assets/8eeaaa3d-0078-40c2-b7b5-913a3209896f" />

<img width="1917" height="1017" alt="image" src="https://github.com/user-attachments/assets/eb5dc28a-9244-4d44-8bfe-31d025a2a442" />

<img width="1910" height="966" alt="image" src="https://github.com/user-attachments/assets/8a481102-f436-4d09-96b6-aed24620639b" />



## 🪜 PM2 — Password Cracking with NetworkWalks Tools

### Run 1 — My Locked PDF1.pdf

**Step 1. Extract the hash with the Hash Calculator**

The locked PDF was uploaded to the NetworkWalks Hash Calculator, which parsed it locally in the browser and returned a `$pdf$...` hash (pdf2john / hashcat compatible format).

<img width="1905" height="907" alt="image" src="https://github.com/user-attachments/assets/efabbd78-3bf6-4655-b9a7-71d65aef7805" />


**Step 2. Paste the hash into the Password Cracker & crack it**

The extracted hash was pasted into the NetworkWalks Password Cracker, using the built-in 100-password wordlist. The dictionary attack tried different candidate passwords and found a match at 91/100.

<img width="1890" height="970" alt="image" src="https://github.com/user-attachments/assets/73eb7968-c5eb-46e1-a384-4399424aa34e" />


*(Password text has been masked above.)*

**Step 3. PDF opened**

<img width="1902" height="907" alt="image" src="https://github.com/user-attachments/assets/1d559136-9d09-4012-a050-444ad454f9cd" />


### Run 2 — My Locked PDF2.pdf

**Step 1. Extract the hash with the Hash Calculator**

The second locked PDF was uploaded to the Hash Calculator to extract its `$pdf$...` hash.

<img width="1915" height="962" alt="image" src="https://github.com/user-attachments/assets/25a21532-c59d-4b84-be74-4fd2c90ba8f6" />


**Step 2. Paste the hash into the Password Cracker & crack it**

The hash was pasted into the Password Cracker, the attack was started, and the tool found a match at 91/100.

<img width="1901" height="906" alt="image" src="https://github.com/user-attachments/assets/d551460d-fa71-4cf7-bd85-5f22dbc0fac8" />



*(Password text has been masked above.)*

**Step 3. PDF opened**

<img width="1917" height="912" alt="image" src="https://github.com/user-attachments/assets/82685496-0327-4a5c-a63a-13f4437f3148" />


### Run 3 — My Locked PDF3.pdf

**Step 1. Extract the hash with the Hash Calculator**

The third locked PDF was uploaded to the Hash Calculator to extract its `$pdf$...` hash.

<img width="960" alt="NW Hash Calculator PDF3" src="images/nw-pdf3-hashcalc.png" />

**Step 2. Paste the hash into the Password Cracker & crack it**

The hash was pasted into the Password Cracker and the attack found a match at 35/100.

<img width="960" alt="NW Password Cracker PDF3 result" src="images/nw-pdf3-cracker.png" />

*(Password text has been masked above.)*

**Step 3. PDF opened**

<img width="700" alt="PDF3 opened with cracked password" src="images/nw-pdf3-flag.png" />

---

## 🔎 Results Summary

| Module | Tool | Hash Source | Result |
|---|---|---|---|
| PM1 — Run 1 | Johnny / John the Ripper | My Locked PDF1.pdf | ✅ Password cracked, PDF unlocked |
| PM1 — Run 2 | Johnny / John the Ripper | My Locked PDF2.pdf | ✅ Password cracked, PDF unlocked |
| PM1 — Run 3 | Johnny / John the Ripper | My Locked PDF3.pdf | ✅ Password cracked, PDF unlocked |
| PM2 — Run 1 | NetworkWalks Hash Calculator + Password Cracker | My Locked PDF1.pdf | ✅ Password cracked successfully |
| PM2 — Run 2 | NetworkWalks Hash Calculator + Password Cracker | My Locked PDF2.pdf | ✅ Password cracked successfully |
| PM2 — Run 3 | NetworkWalks Hash Calculator + Password Cracker | My Locked PDF3.pdf | ✅ Password cracked successfully |

---

## 💡 What I Learned

- How a password-protected PDF stores its password as a hash (`$pdf$...` format), and how that hash is extracted using a `pdf2john`/hashcat-compatible approach.
- How a dictionary attack works: trying candidate passwords from a wordlist against a hash until a match is found.
- The difference between a desktop GUI tool (Johnny/JTR) and browser-based tools (NetworkWalks Hash Calculator & Password Cracker) for doing the same type of attack.
- Why short, common passwords (like the ones used in this lab) can be cracked almost instantly, which highlights the importance of using long, complex, unique passwords.
- The importance of masking cracked credentials before sharing screenshots or documentation publicly.

---

## 🔐 Security & Ethical Use

This lab was performed strictly for educational purposes on sample files provided by NetworkWalks for this course. The techniques shown here must only be used on systems/files you own or have explicit permission to test.

---

## 👤 Author

**K. Pranay Kumar** — B084
Cybersecurity Professional, NetworkWalks

---

## 📌 Project Information

**Program Name:** Cybersecurity at NetworkWalks | **Week:** 03 | **Project:** Password Cracking with JTR (PM1) & NetworkWalks Tools (PM2) | **Repository:** GitHub
