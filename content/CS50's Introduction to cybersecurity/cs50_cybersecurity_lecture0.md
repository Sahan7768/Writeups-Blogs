# 🔐 CS50 Cybersecurity — Lecture 0: Securing Accounts

> **Course:** [CS50's Introduction to Cybersecurity](https://cs50.harvard.edu/cybersecurity/)
> **Topic:** Account Security — Passwords, Attacks & Defences
> **Level:** Beginner-Friendly

---

## 📋 Table of Contents

1. [What is Security?](#1-what-is-security)
2. [Passwords & Brute-Force Attacks](#2-passwords--brute-force-attacks)
3. [NIST Password Guidelines](#3-nist-password-guidelines)
4. [Multi-Factor Authentication (MFA)](#4-multi-factor-authentication-mfa)
5. [One-Time Passwords (OTP)](#5-one-time-passwords-otp)
6. [Common Attack Types](#6-common-attack-types)
7. [Defences & Tools](#7-defences--tools)
8. [Summary](#8-summary)

---

## 1. What is Security?

Think of security like locking your house. A **key** proves you are the rightful owner before entering.

In the digital world, security works the same way — but with usernames and passwords instead of physical keys.

| Concept | Simple Explanation | Real-World Example |
|---|---|---|
| **Authorization** | Proving you're allowed in | Showing your ID at the door |
| **Username** | Tells the system *who* you are | Your email address on Gmail |
| **Password** | Proves you really *are* that person | A secret only you know |

> ⚠️ **Key Tradeoff:** The more secure a system, the harder it is to use. The easier it is to use, the less secure it tends to be. Good security finds the right *balance*.

---

## 2. Passwords & Brute-Force Attacks

### What is a Brute-Force Attack?

Imagine a padlock with a 4-digit PIN. A thief could just try every combination — `0000`, `0001`, `0002` … all the way to `9999`. That's called a **brute-force attack**.

Hackers use programs to do this automatically, at enormous speed.

### How Password Length & Complexity Helps

| Password Type | Characters Available | 4-Character Combinations |
|---|---|---|
| Digits only (`0–9`) | 10 | 10,000 |
| Letters only (`a–z`, `A–Z`) | 52 | ~7,311,616 |
| Letters + Numbers + Symbols | ~95 | ~81,450,625 |

> 💡 **Simple rule:** Every extra character and character type *multiplies* how hard it is to crack your password.

### Python Code Example

The CS50 course demonstrates this with Python. Here's how all 4-digit PIN combinations are generated:

```python
from string import digits

for i in digits:
    for j in digits:
        for k in digits:
            for l in digits:
                print(i, j, k, l)
```

A computer can run through all 10,000 combinations in **milliseconds**. This is why a 4-digit PIN alone is not enough for important accounts.

---

## 3. NIST Password Guidelines

**NIST** (National Institute of Standards and Technology) is a US government body that publishes best-practice security guidelines. Their key password recommendations are:

### ✅ Do's

- Passwords should be **at least 8 characters** long
- Allow **all** printable characters including symbols (up to 64 characters)
- **Lock accounts** after several failed login attempts
- Check new passwords against known **breached password lists** (e.g., "password123" should be rejected)

### ❌ Don'ts

- Do **not** force users to change passwords regularly (it encourages weak, predictable changes like `Password1` → `Password2`)
- Do **not** show password hints to unauthenticated users

> 💬 **Example:** If you try to set your password to "123456" on a well-designed site, it should reject it because that password is on every known breach list.

---

## 4. Multi-Factor Authentication (MFA)

**Multi-Factor Authentication (MFA)** — also called **2FA** — means using *more than one* method to prove your identity. Think of it like needing both a key *and* a fingerprint to enter a room.

There are three categories ("factors") of authentication:

| Factor | What It Means | Example |
|---|---|---|
| 🧠 **Knowledge** | Something only *you know* | Password, PIN, security question |
| 📱 **Possession** | Something only *you have* | Your phone, a key fob |
| 👁️ **Inherence** | Something only *you are* | Fingerprint, Face ID, retina scan |

> 💡 **Why it matters:** Even if a hacker steals your password (Knowledge factor), they still can't log in without your phone (Possession factor).

---

## 5. One-Time Passwords (OTP)

An **OTP** is a temporary code — usually 6 digits — that expires quickly (e.g., in 30 seconds). It's an extra layer on top of your regular password.

### OTP Methods — From Least to Most Secure

```
Least Secure
    │
    ▼
📱 SMS / Text Message OTP
   ├─ Easy to use
   └─ Vulnerable to SIM Swapping*

    ▼
📲 Authenticator App OTP (e.g., Google Authenticator, Authy)
   ├─ More secure
   └─ Tied to your specific device

    ▼
🔑 Hardware Key Fob (e.g., YubiKey)
   ├─ Most secure
   └─ Physical device required
    │
Most Secure
```

> ⚠️ **SIM Swapping:** A hacker convinces your phone carrier to transfer your number to a SIM card they control. Once they have your number, they receive your SMS OTPs. This is why **authenticator apps are safer than SMS**.

---

## 6. Common Attack Types

### 🔑 Keylogging

> Secretly recording every key you press.

A **keylogger** is malicious software installed on a computer. Every character you type — including usernames, passwords, and OTPs — gets sent to the attacker.

**Defence:** Only log in on devices you trust and own. Avoid logging into sensitive accounts on public computers (e.g., library computers, hotel terminals).

---

### 🗂️ Credential Stuffing

> Using stolen passwords from one site on other sites.

When a website gets hacked, millions of username/password pairs get leaked. Attackers then *automatically try* those same combinations on other websites (banks, email, shopping sites).

**Defence:** Use a **unique password for every website**. If one site gets breached, your other accounts remain safe.

---

### 🎭 Social Engineering

> Manipulating *people* instead of *systems*.

Instead of hacking software, the attacker tricks a human being into revealing credentials.

**Example:** Someone calls pretending to be from your bank's IT department:
> *"Hi, this is Tom from tech support. We've detected suspicious activity. I just need to confirm your password to secure your account."*

A legitimate company will **never** ask for your password.

**Defence:** Be suspicious of unsolicited contacts asking for sensitive information. Verify by calling back on an official number.

---

### 🎣 Phishing

> Fake websites or emails designed to steal your login details.

You receive an email that looks like it's from Google, with a link to a login page — but the website is actually controlled by an attacker. You type your password and they have it.

**Example of a phishing URL:**
```
Legitimate:  https://accounts.google.com/login
Phishing:    https://accounts-google.com-login.xyz/login
             ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
             Looks similar, but it's a completely different domain!
```

**Defence:** Never click login links from emails. Open your browser and type the address yourself.

---

### 🕵️ Machine-in-the-Middle (MitM) Attack

> Intercepting data between you and a website.

Your internet traffic passes through many devices (routers, switches) before reaching a website. A sophisticated attacker who controls one of those devices can *read* or *alter* your data.

**Defence:** Always use **HTTPS** (look for the padlock icon in your browser). Avoid sensitive activities on public Wi-Fi.

---

## 7. Defences & Tools

### 🔗 Single Sign-On (SSO)

SSO lets you use one trusted account (like Google or Apple) to log in to many other services.

| Without SSO | With SSO |
|---|---|
| 20 websites = 20 different passwords | 20 websites = 1 trusted login |
| High risk of reusing passwords | Reduced exposure |
| Hard to manage | Much simpler |

> **Example:** Clicking "Sign in with Google" on Spotify uses SSO. You never give Spotify your password — Google verifies your identity on their behalf.

---

### 🗄️ Password Managers

A **password manager** (e.g., 1Password, Bitwarden, Dashlane) stores all your passwords in an encrypted vault. You only need to remember **one strong master password**.

**Benefits:**
- Generates long, random passwords for every site (e.g., `k#9pLm!qR2vXn`)
- Detects and warns about phishing sites
- Works across devices and browsers
- Alerts you when a saved password has been in a data breach

**Tradeoff:**
> You're putting all your eggs in one basket. If someone gets your master password, they have everything. Use a very strong master password and enable MFA on your password manager.

---

### 🔐 Passkeys *(Emerging Technology)*

Passkeys are the future of login — no password required at all.

| Component | Who Holds It | Purpose |
|---|---|---|
| **Public Key** | The website | Identifies you |
| **Private Key** | Your device | Proves your identity (never leaves your device) |

When you log in, your device uses cryptography to *prove* you are who you say you are — without ever sending a password over the internet. Even if the website is breached, there's no password to steal.

> 💡 You already use passkey-like technology every time you use Face ID or a fingerprint to unlock your phone.

---

## 8. Summary

| Topic | Key Takeaway |
|---|---|
| **Passwords** | Longer + more complex = harder to crack |
| **NIST Guidelines** | Use long passwords; no forced periodic changes; block breached passwords |
| **MFA / 2FA** | Always enable it — even SMS 2FA is better than nothing |
| **OTP** | Authenticator apps are safer than SMS |
| **Keylogging** | Only log in on trusted devices |
| **Credential Stuffing** | Use a unique password on every site |
| **Social Engineering** | Verify before you trust; legitimate companies won't ask for your password |
| **Phishing** | Type URLs manually; don't click email login links |
| **SSO** | Fewer passwords = less risk of reuse |
| **Password Managers** | The best practical solution for managing unique passwords |
| **Passkeys** | The future — passwordless login using cryptography |

---

> 🏫 **Source:** [CS50's Introduction to Cybersecurity — Lecture 0](https://cs50.harvard.edu/cybersecurity/)
> 📝 *Notes simplified for clarity with additional examples added for understanding.*
