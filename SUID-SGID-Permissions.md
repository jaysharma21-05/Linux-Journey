<div align="center">

# 📚 Linux Journey - File Permissions

### Understanding SUID & SGID in Linux

**Author:** Jay Sharma  
**Date:** January 07, 2026  
**Location:** Gangtok, Sikkim  
**Difficulty:** <img src="https://img.shields.io/badge/Level-Intermediate-orange" />

---

</div>

<br>

## 📖 Table of Contents

<details>
<summary>Click to expand</summary>

- [Overview](#overview)
- [1. SUID (Set User ID)](#1-suid-set-user-id)
- [2. SGID (Set Group ID)](#2-sgid-set-group-id)
- [Comparison Table](#comparison-table)
- [Practical Examples](#practical-examples)
- [Important Tips](#important-tips)

</details>

---

<br>

## 🎯 Overview

<table>
<tr>
<td width="50%">

**Special Permissions** Linux mein 3 tarah ke special permissions hote hain:
- ✅ **SUID** - User ID set karta hai
- ✅ **SGID** - Group ID set karta hai  
- ✅ **Sticky Bit** - Delete protection

</td>
<td width="50%" bgcolor="#f6f8fa">

> [!NOTE]  
> **Kya seekhenge?**  
> Is document mein aap SUID aur SGID ke concepts ko detailed examples ke saath samjhenge.

</td>
</tr>
</table>

<br>

---

<br>

## 1️⃣ SUID (Set User ID)

<div style="background-color: #e7f3ff; padding: 20px; border-left: 5px solid #2196F3; margin: 10px 0;">

### 📌 SUID ka matlab

**SUID ka matlab:** Jab koi normal user kisi aisi file ko run karta hai jispe SUID laga ho, to wo file **us user ki power se nahi balki file ke owner ki power se** chalti hai.

</div>

### 🔍 Real-Life Example

<blockquote>
<p><strong>🏫 School ki Attendance Register</strong></p>

Socho aapke school ki ek <strong>Main Attendance Register</strong> hai jo Principal ke cabin mein rehti hai. Sirf Principal (Root) hi usse touch kar sakta hai.

<p>Lekin, agar aapko apni attendance check karni hai, to Principal ne ek <strong>"Special Pen"</strong> (SUID) rakha hai. Jab tak wo pen aapke hath mein hai, aapke paas Principal ki power hai us register ko access karne ki. Jaise hi pen chhoda, aap phir se ek normal student ban gaye.</p>
</blockquote>

### ⚙️ Technical Details

<table width="100%" border="1" style="border-collapse: collapse;">
<thead style="background-color: #4CAF50; color: white;">
<tr>
<th>Property</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Symbol</strong></td>
<td><code>s</code> (owner ke execute 'x' ki jagah)</td>
</tr>
<tr>
<td><strong>Octal Value</strong></td>
<td><code>4</code></td>
</tr>
<tr>
<td><strong>Example File</strong></td>
<td><code>/usr/bin/passwd</code></td>
</tr>
<tr>
<td><strong>Permission String</strong></td>
<td><code>-rwsr-xr-x</code></td>
</tr>
</tbody>
</table>

### 💻 Practical Commands

```bash
# SUID set karne ke liye (u+s)
chmod u+s myfile

# ls -l karke check karo  
ls -l myfile
# Output: -rwsr-xr-x  1 root root

# Yahan 's' ka matlab SUID set hai

# SUID remove karne ke liye
chmod u-s myfile
```

> [!WARNING]  
> **Security Risk:** SUID files ko carefully use karo! Agar kisi malicious file par SUID set ho gaya, to attacker root access pa sakta hai.

<br>

---

<br>

## 2️⃣ SGID (Set Group ID)

<div style="background-color: #fff3cd; padding: 20px; border-left: 5px solid #ff9800; margin: 10px 0;">

### 📌 SGID kaise kaam karta hai

SGID **do tarah** se kaam karta hai:

1. **Files par:** File us group ki permissions se chalegi jo uska group owner hai.
2. **Directories par (Jyada use hota hai):** Agar kisi folder par SGID laga hai, to uske andar koi bhi user file banaye, us file ka **Group** wahi hoga jo us folder ka hai.

</div>

### 🎯 Use Case - Team Collaboration

<table width="100%">
<tr>
<td width="30%" align="center" style="background-color: #e8f5e9;">

**👥 Team Folder**

<img src="https://img.shields.io/badge/Group-developers-success" />

</td>
<td width="70%">

Agar aapki team ek shared folder use kar rahi hai, to SGID set karne se **har nai file automatically team ke group ki** ho jayegi. Isse collaboration easy ho jata hai!

</td>
</tr>
</table>

### ⚙️ Technical Details  

| Property | Value |
|----------|-------|
| **Symbol** | `s` (group ke execute 'x' ki jagah) |
| **Octal Value** | `2` |
| **Best Use** | Shared directories |
| **Permission String** | `drwxrws---` |

### 💻 Practical Commands

```bash
# Directory par SGID set karna (g+s)
mkdir shared_folder
chmod g+s shared_folder

# Ab iske andar koi bhi file banao
touch shared_folder/newfile.txt

# Check karo - group automatically shared_folder wala hi rahega
ls -l shared_folder/newfile.txt
```

<br>

---

<br>

## 📊 Comparison Table

<div align="center">

### SUID vs SGID - Quick Reference

<table border="1" style="border-collapse: collapse; width: 90%;">
<thead style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); color: white;">
<tr>
<th>Feature</th>
<th>SUID</th>
<th>SGID</th>
</tr>
</thead>
<tbody>
<tr style="background-color: #f9f9f9;">
<td><strong>Applies To</strong></td>
<td>Files</td>
<td>Files & Folders</td>
</tr>
<tr>
<td><strong>Function</strong></td>
<td>File owner ki power se chalti hai</td>
<td>Nayi files folder ka group inherit karti hain</td>
</tr>
<tr style="background-color: #f9f9f9;">
<td><strong>Symbol</strong></td>
<td><code>-rws------</code></td>
<td><code>drwxrws---</code></td>
</tr>
<tr>
<td><strong>Octal Value</strong></td>
<td><code>4</code></td>
<td><code>2</code></td>
</tr>
<tr style="background-color: #f9f9f9;">
<td><strong>Common Use</strong></td>
<td><code>/usr/bin/passwd</code></td>
<td>Team collaboration folders</td>
</tr>
</tbody>
</table>

</div>

<br>

---

<br>

## 💡 Important Tips

### Choti Trick: 's' vs 'S'

<table width="100%">
<tr>
<td width="50%" style="padding: 15px; background-color: #d4edda; border: 1px solid #c3e6cb;">

**✅ Chota 's' (Correct)**

```
-rwsr-xr-x
```

MATLAB: Execute permission bhi hai

</td>
<td width="50%" style="padding: 15px; background-color: #f8d7da; border: 1px solid #f5c6cb;">

**❌ Bada 'S' (Error)**

```
-rwSr-xr-x  
```

MATLAB: Execute permission nahi hai (ye ek misconfiguration hai)

</td>
</tr>
</table>

### 🔐 Security Best Practices

> [!CAUTION]  
> **Dhyan Rakho:**
> - SUID files ko regularly audit karo
> - Unnecessary SUID permissions remove karo
> - World-writable SUID files kabhi na banao

<br>

---

<div align="center">

## 🎓 Practice Exercise

<table width="80%" border="1" style="border-collapse: collapse;">
<tr style="background-color: #3f51b5; color: white;">
<td align="center"><strong>Exercise</strong></td>
</tr>
<tr>
<td style="padding: 15px;">

**Task:** Create a shared project folder with SGID

```bash
# 1. Folder banao
mkdir /home/project_team

# 2. Group set karo
chgrp developers /home/project_team

# 3. SGID enable karo  
chmod 2775 /home/project_team

# 4. Verify karo
ls -ld /home/project_team
```

</td>
</tr>
</table>

</div>

<br>

---

<div align="center">

## 🎥 Video Tutorial

### 🎬 Complete Practical Demo

**📺 Watch the Full Tutorial:**

🔗 **[SUID & SGID File Permissions on YouTube](https://youtu.be/JNb5knHk7Lg?si=glfTtqwO8UotP6Nk)**

📌 Video mein ye saare concepts practical karke dikhaye gaye hain!

<br>


### 📝 Notes

**Last Updated:** January 07, 2026, 7:00 PM IST  
**Next Topic:** Sticky Bit & Access Control Lists (ACL)

<br>

![GitHub](https://img.shields.io/badge/GitHub-jaysharma21--05-blue?logo=github)
![Progress](https://img.shields.io/badge/Progress-25%25-yellow)

---

**Made with ❤️ in Gangtok, Sikkim**

</div>
