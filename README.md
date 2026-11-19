# 🔐 Week 3: Password Cracking with JTR & NetworkWalks Tools

## 📌 Overview

This repository documents my **Week 3 Cybersecurity and Ethical Hacking lab work**, focused on understanding how password cracking works and why strong passwords are important.

The labs covered:

- 🔑 Password cracking with **John the Ripper (JTR)**
- 🖥️ Password cracking using **Johnny**, the graphical interface for JTR
- 🌐 Password cracking with **NetworkWalks online tools**
- 🤖 AI-assisted password cracking using **Claude Desktop + HexStrike MCP**
- 🛡️ Ethical use of password-cracking tools in authorized learning environments

> ⚠️ **Ethical notice:** Password cracking must only be used on systems, files, and accounts that you own or are explicitly authorized to test. These labs were completed for educational purposes only.

---

## 🎯 Learning Objectives

By completing Week 3, I learned how to:

- Understand what password cracking means in cybersecurity.
- Explain the difference between a password and a password hash.
- Extract a hash from a password-protected PDF file.
- Use John the Ripper (JTR) to test password strength.
- Use Johnny, the graphical version of JTR.
- Use online tools to calculate and crack a PDF hash.
- Use AI tools and MCP servers to assist with cybersecurity lab tasks.
- Understand why weak passwords are dangerous.
- Apply ethical and legal practices when testing passwords.

---

## 🧠 What Is Password Cracking?

Password cracking is the process of recovering a password from stored data, such as a password hash or an encrypted file.

Security professionals use password cracking to:

- 🔍 Test password strength.
- 🧪 Identify weak or reused passwords.
- 🛡️ Improve password policies.
- 🚨 Demonstrate security risks.
- 📚 Teach users how to create stronger passwords.

A weak password can be cracked quickly because it may be short, common, predictable, or based on simple words.

---

## 🔑 Passwords vs Hashes

A **password** is the secret text a user enters.

A **hash** is a scrambled value created from that password. Password systems often store hashes rather than the actual password.

Example:

```text
Password: password1
Hash: $pdf$...
```

In this lab, the PDF password hash began with:

```text
$pdf$
```

The cracking tool tested possible passwords against the hash until it found the correct match.

---

## 🧰 Tools Used

| Tool | Purpose |
|---|---|
| 🔨 **John the Ripper (JTR)** | Command-line password-cracking tool |
| 🖥️ **Johnny** | Graphical user interface for John the Ripper |
| 🌐 **NetworkWalks Hash Calculator** | Extracts the hash from a protected PDF |
| 🌐 **NetworkWalks Password Cracker** | Tests possible passwords against the extracted hash |
| 🤖 **Claude Desktop** | AI assistant used with HexStrike MCP |
| ⚙️ **HexStrike MCP** | MCP server used to connect Claude Desktop with cybersecurity tools |
| 🐧 **Kali Linux** | Linux environment used for cybersecurity practice |

---

# 🧪 W3-PM1: Password Cracking with JTR

## 🎯 Task

Crack the password of:

```text
My Locked PDF1.pdf
```

using:

- 🔨 John the Ripper (JTR)
- 🖥️ Johnny GUI

on a Windows PC.

---

## 📥 Step 1: Download John the Ripper

<img width="1391" height="807" alt="01_screenshot_johntheripper" src="https://github.com/user-attachments/assets/4099a5c4-9319-4dd7-9eda-30dc1e040e88" />

I downloaded John the Ripper from the official website:

🔗 [https://www.openwall.com/john/](https://www.openwall.com/john/)

John the Ripper can be used on:

- 🪟 Windows
- 🐧 Linux
- 🍎 macOS

On Kali Linux, John the Ripper is usually pre-installed.

---

## 🖥️ Step 2: Install Johnny GUI

Johnny is the graphical version of John the Ripper.

<img width="1452" height="1010" alt="02_screenshot_johny" src="https://github.com/user-attachments/assets/b12f20f4-9e42-4e54-98ae-d7feca9d1984" />


I downloaded Johnny from:

🔗 [https://openwall.info/wiki/john/johnny](https://openwall.info/wiki/john/johnny)

After installation, I opened Johnny and configured it to locate the JTR executable:

```text
john.exe
```

The `john.exe` file was located in the JTR `run` folder.

---

## 📄 Step 3: Extract the PDF Hash

I uploaded the locked PDF file to the online hash extractor:

🔗 [https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php](https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php)

<img width="1917" height="1025" alt="03_screenshot_hash" src="https://github.com/user-attachments/assets/487c4611-de69-41e4-880f-53ce6b1eddb9" />


The tool produced a hash beginning with:

```text
$pdf$
```

I copied the full hash value.

> ⚠️ **Important:** I removed extra characters such as `b'` if they appeared at the beginning of the hash. The hash needed to start correctly with:
>
> ```text
> $pdf$
> ```

---

## 📝 Step 4: Save the Hash

I opened Notepad and pasted the hash value.

I saved the file as:

```text
PDF1_HASH.txt
```

---

## 🔓 Step 5: Crack the Password with Johnny

In Johnny, I completed the following steps:

1. 📂 Clicked **Open password file**
2. 🗂️ Selected `PDF1_HASH.txt`
3. ▶️ Clicked **Start new attack**
4. ⏳ Waited for JTR to test possible passwords
5. 🔑 Found the cracked password

<img width="945" height="1015" alt="04_screenshot_jtr_crack" src="https://github.com/user-attachments/assets/93f4244b-60a0-419a-91bf-d79950cf4dbc" />


The cracked password was:

```text
good-luck
```

---

## 📄 Step 6: Open the PDF

<img width="952" height="1020" alt="05_screenshot_password_goodluck" src="https://github.com/user-attachments/assets/237ba96d-2d02-4565-bd8a-312cce5ab691" />


I opened the locked PDF file and entered the recovered password:

```text
good-luck
```

The PDF opened successfully. ✅

<img width="953" height="1020" alt="09_screenshot_openpdf1" src="https://github.com/user-attachments/assets/a0e4b1bc-bdda-4d12-818a-47039132d93c" />


---

## 🧠 What I Learned from the JTR Lab

- 🔐 Password-protected files can contain hash data that security tools can analyze.
- 🔨 John the Ripper is a powerful password-cracking tool.
- 🖥️ Johnny makes JTR easier for beginners because it provides a graphical interface.
- 📄 A PDF hash can begin with `$pdf$`.
- ⏳ Cracking time depends on computer speed and password complexity.
- 🔑 Simple passwords such as `good-luck` can be cracked quickly.
- 🛡️ Strong passwords should be long, unique, and difficult to guess.
- ⚖️ Password cracking should only be done with permission.

---

# 🌐 W3-PM2: Password Cracking with NetworkWalks Tools

## 🎯 Task

Crack the password of:

```text
My Locked PDF3.pdf
```

using the NetworkWalks:

- 🧮 Hash Calculator
- 🔓 Password Cracker

Both tools run in a web browser, so no installation was required.

---

## 📥 Step 1: Download the PDF

I downloaded the encrypted PDF file:

```text
My Locked PDF3.pdf
```

from the NetworkWalks lab page:

🔗 [https://networkwalks.com/project-task-lab-password-cracking-with-networkwalks-tools/](https://networkwalks.com/project-task-lab-password-cracking-with-networkwalks-tools/)

---

## 🧮 Step 2: Extract the Hash

I opened the NetworkWalks Hash Calculator:

🔗 [https://networkwalks.com/hash-calculator/](https://networkwalks.com/hash-calculator/)

I uploaded the locked PDF file.

<img width="955" height="1023" alt="06_screenshot_pdf_upload" src="https://github.com/user-attachments/assets/903ca2ef-b4c0-4b30-a713-50f4331b2067" />


The tool generated a hash beginning with:

```text
$pdf$
```

I copied the complete hash value.

<img width="947" height="1028" alt="07_screenshot_copied_pdf" src="https://github.com/user-attachments/assets/1ecadffd-f258-465c-9718-64f569f3314f" />

---

## 🔓 Step 3: Crack the Hash

I opened the NetworkWalks Password Cracker:

🔗 [https://networkwalks.com/password-cracker/](https://networkwalks.com/password-cracker/)

I pasted the full hash into the Password Cracker and started the attack.

The tool tested possible passwords until it found a match.

<img width="955" height="1018" alt="08_screeshot_cracking" src="https://github.com/user-attachments/assets/7ac4dc0e-5851-47f2-9f22-b47c8baf0622" />


The recovered password was:

```text
1qaz2wsx
```

---

## 📄 Step 4: Open the PDF

I opened the encrypted PDF and entered:

```text
1qaz2wsx
```

The PDF opened successfully. ✅

<img width="948" height="1015" alt="10_screenshot_open_pdf3" src="https://github.com/user-attachments/assets/37a3a32e-6107-4f29-82ba-6476ce2d265b" />


---

## 🧠 What I Learned from the NetworkWalks Lab

- 🌐 Online tools can be used to extract and test password hashes.
- 🧮 A hash calculator can read a protected PDF and extract its hash.
- 🔓 A password cracker tests possible passwords against a hash.
- 🔑 The complete hash must be copied correctly, starting with `$pdf$`.
- ⏳ Simple passwords are cracked faster than complex passwords.
- 🛡️ Password protection is only as strong as the password used.
- ⚖️ These tools should only be used for authorized learning and testing.

---

# 🤖 W3-OPTIONAL1: AI-Assisted JTR Password Cracking Lab

## 🎯 Task

Crack the password of:

```text
My Locked PDF2.pdf
```

using:

- 🔨 John the Ripper
- 🤖 Claude Desktop
- ⚙️ HexStrike MCP Server
- 🐧 Kali Linux
- 📚 `rockyou.txt` wordlist

---

## 🧰 Lab Environment

The lab used:

```text
Kali Linux VM
Claude Desktop
HexStrike-AI MCP Server
John the Ripper
rockyou.txt wordlist
```

---

## ⚙️ Step 1: Set Up Claude Desktop on Kali Linux

I followed the setup instructions from the Claude Desktop Debian repository:

🔗 [https://github.com/aaddrick/claude-desktop](https://github.com/aaddrick/claude-desktop)

<img width="955" height="910" alt="11_screenshot_github" src="https://github.com/user-attachments/assets/18ba99b2-079f-46d0-845a-8e6fea348eee" />


I added the GPG key:

```bash
curl -fsSL https://pkg.claude-desktop-debian.dev/KEY.gpg | sudo gpg --dearmor -o /usr/share/keyrings/claude-desktop.gpg
```

I added the repository:

```bash
echo "deb [signed-by=/usr/share/keyrings/claude-desktop.gpg arch=amd64,arm64] https://pkg.claude-desktop-debian.dev stable main" | sudo tee /etc/apt/sources.list.d/claude-desktop.list
```

<img width="955" height="910" alt="12_screenshot_claude_install" src="https://github.com/user-attachments/assets/c2aac4c8-b1bb-4b67-af51-60361c7e6782" />

I updated the system and installed Claude Desktop:

```bash
sudo apt update
sudo apt install claude-desktop
```

Then I opened Claude Desktop and completed the sign-in process.

<img width="955" height="910" alt="14_screenshot_claude" src="https://github.com/user-attachments/assets/f7a94fc6-aa9f-4668-a23d-4d054e1aafc2" />


---

## ⚙️ Step 2: Install HexStrike MCP

I cloned the HexStrike AI repository:

<img width="955" height="910" alt="13_screenshot_hexstrike_install" src="https://github.com/user-attachments/assets/929d0815-4a6e-4889-865a-9fb9d195c716" />


```bash
git clone https://github.com/0x4m4/hexstrike-ai.git
cd hexstrike-ai
```

I created and activated a Python virtual environment:

```bash
python3 -m venv hexstrike-env
source hexstrike-env/bin/activate
```

I installed the required Python dependencies:

```bash
pip3 install -r requirements.txt
```

I started the HexStrike server:

```bash
cd ~/hexstrike-ai
source hexstrike-env/bin/activate
python3 hexstrike_server.py
```

<img width="955" height="910" alt="15_screenshot_hexstrike" src="https://github.com/user-attachments/assets/39423b18-9d81-4609-bad0-bd4a0e88fc26" />


---

## ⚙️ Step 3: Configure Claude Desktop

I added the HexStrike MCP server configuration to Claude Desktop:

<img width="955" height="910" alt="16_screenshot_hexstrike_setup" src="https://github.com/user-attachments/assets/b3d44317-c001-4e9c-8534-1f9931dbd4df" />


```json
{
  "mcpServers": {
    "hexstrike-ai": {
      "command": "/home/kali/hexstrike-ai/hexstrike-env/bin/python",
      "args": [
        "/home/kali/hexstrike-ai/hexstrike_mcp.py",
        "--server",
        "http://localhost:8888"
      ]
    }
  }
}
```

<img width="955" height="910" alt="16_screenshot_server_running" src="https://github.com/user-attachments/assets/c81dc29e-48a2-4edf-9366-903e7785f9e5" />


After saving the configuration, the HexStrike MCP server was running. ✅

---

## 🤖 Step 4: Use AI Prompts

I copied the target PDF to the Kali Linux desktop:

```text
/home/kali/Desktop/My Locked PDF2.pdf
```

I used the following AI prompts in Claude Desktop:

<img width="1920" height="923" alt="17_screenshot_check" src="https://github.com/user-attachments/assets/8011a9d8-3605-4e24-8f41-b96e614b884f" />


```text
Check if John the Ripper is installed in this Hexstrike MCP and show me its version
```

```text
Please calculate the hash value of this PDF file:
/home/kali/Desktop/My Locked PDF2.pdf
```

<img width="1920" height="923" alt="18_screenshot_the_pass" src="https://github.com/user-attachments/assets/42ff3bb3-729e-47d3-bcf4-21fab95613bc" />


```text
Please use JTR tool in this hexstrike MCP server to crack the password of this PDF file.
Use the rockyou.txt wordlist dictionary.
```

The AI-assisted workflow used JTR and the `rockyou.txt` wordlist to recover the PDF password.

---

## 🧠 What I Learned from the AI Lab

- 🤖 AI can help guide cybersecurity tasks by generating commands and explaining steps.
- ⚙️ MCP servers can connect AI assistants to external tools and services.
- 🐧 Kali Linux is useful for cybersecurity practice because it includes many security tools.
- 🔨 John the Ripper can use wordlists such as `rockyou.txt`.
- 📚 A wordlist contains many possible passwords that a cracking tool can test.
- 🧠 AI can speed up learning, but the user must still understand the commands and security risks.
- ⚖️ AI-assisted hacking must still follow ethical and legal rules.

---

# 🛡️ Key Cybersecurity Lessons

## 🔑 Strong Passwords Matter

Weak passwords can be cracked quickly.

A strong password should be:

- ✅ Long
- ✅ Unique
- ✅ Difficult to guess
- ✅ Not based on common words
- ✅ Different for every account
- ✅ Stored in a password manager

Examples of weak passwords:

```text
password1
123456
qwerty
admin
letmein
```

---

## 🔐 Use Multi-Factor Authentication

Multi-Factor Authentication, or **MFA**, adds another layer of protection.

Even if someone learns a password, they may still need:

- 📱 A verification code
- 🔐 An authentication app
- 🔑 A security key
- 📧 An email confirmation

MFA makes unauthorized access much harder.

---

## ⚖️ Ethical Hacking Rules

Password cracking must only be done when you have permission.

Never use these tools on:

- ❌ Someone else’s account
- ❌ A school system without permission
- ❌ A company network without authorization
- ❌ A public Wi-Fi network
- ❌ Any system you do not own

Ethical hackers follow rules, obtain permission, and use their skills to improve security.

---

# 📚 Summary of What I Learned

In Week 3, I learned:

- 🔐 How password cracking works.
- 🔨 How to use John the Ripper.
- 🖥️ How to use Johnny GUI.
- 🌐 How to use NetworkWalks hash and password-cracking tools.
- 📄 How to extract a PDF hash.
- 🧠 What a password hash is.
- 🤖 How AI and MCP servers can assist cybersecurity learning.
- 🛡️ Why strong passwords and MFA are important.
- ⚖️ The importance of ethical and authorized security testing.

This lab helped me understand that cybersecurity is not only about tools—it is also about **responsibility, ethics, and protecting people’s information**. 🛡️

---

# 🚀 Next Steps

For future labs, I plan to:

- 🔍 Learn more about password security.
- 🧪 Practice using JTR in Kali Linux.
- 📚 Study wordlists and password policies.
- 🛡️ Learn about multi-factor authentication.
- 🤖 Continue exploring AI-assisted cybersecurity tools.
- ⚖️ Always follow ethical hacking rules.

---

## Project Information

| Field | Details |
|---|---|
| Project title | Password Cracking with JTR & NetworkWalks Tools |
| Focus area | Password cracking and ethical hacking |
| Tools used | John the Ripper (JTR), Johnny, NetworkWalks online tools, Claude Desktop + HexStrike MCP |
| Status | Completed |
| Date | 18 November 2026 |



> ⚠️ **Do not upload real passwords, private files, or sensitive hashes to GitHub.**
