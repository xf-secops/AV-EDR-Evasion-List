# 🔴 AV-EDR-Evasion-List

A repository that includes PoC and techniques to evade various security solutions such as Antivirus and EDR systems.

> **Adversary Simulation | Malware Development | AV/EDR Evasion Research**

---

## 📑 Repository Index

* [🧭 Overview](#-overview)
* [🎯 Objectives](#-objectives)
* [🧠 Malware Types & Techniques](#-malware-types--techniques)
* [🛡️ AV / EDR Evaluation Results](#-av--edr-evaluation-results)
* [🎥 Proof of Concept (PoC)](#-proof-of-concept-poc)
* [⚠️ Disclaimer](#-disclaimer)
* [🧩 Future Work](#-future-work)

---

## 🧭 Overview

This repository presents a **practical adversary simulation project** focused on evaluating and bypassing modern **Antivirus (AV) and Endpoint Detection & Response (EDR)** solutions.

The project replicates real-world offensive techniques used by advanced threat actors.

---

## 🎯 Objectives

* Simulate **real-world malware behavior**
* Evaluate detection capabilities across multiple AV engines
* Implement and test **evasion techniques used in red teaming**
* Provide a **hands-on reference** for security researchers and defenders

---

## 🧠 Malware Types & Techniques

This project uses **distinct malware delivery types**, each designed to bypass specific detection mechanisms.

---

### 🧬 1. Shellcode Injector `t_f_shell.exe`

![Remote Injection](imgs/RemoteShelloadEvador.jpg)

**Malware Type:**
➡️ **Fileless Loader / In-Memory Injector**

**Technique Used:**
➡️ Remote Process Injection (Shellcode Execution)

**Behavior:**

* Injects shellcode into a legitimate **remote process**
* Executes payload fully **in memory**
* No malicious file written to disk

**Why it bypasses AV:**

* Avoids signature-based detection 
* Evades static analysis engines
* Mimics real-world malware loaders

---

### 📦 2. Trojanized DLL (Side-Loaded Payload) — `libcurl.dll`

![DLL Side Loading](imgs/Dllsideloaidng_gup.jpg)

**Malware Type:**
➡️ **Trojanized DLL / Side-Loaded Payload**

**Technique Used:**
➡️ DLL Side Loading

**Behavior:**

* Malicious DLL placed next to a trusted executable
* Loaded automatically by the application
* Executes under **trusted process context**

**Why it bypasses AV:**

* Trusted application masks malicious execution
* Weak DLL validation in legitimate software
* Common in targeted APT attacks

---

## 🛡️ AV / EDR Evaluation Results

| Security Product          | Malware Type Used | Technique Used   | Result   |
| ------------------------- | ----------------- | ---------------- | -------- |
| Kaspersky Plus            | t_f_shell.exe     | Remote Injection | Bypassed |
| Norton                    | t_f_shell.exe     | Remote Injection | Bypassed |
| Malwarebytes              | t_f_shell.exe     | Remote Injection | Bypassed |
| Microsoft Defender        | t_f_shell.exe     | Remote Injection | Bypassed |
| ESET                      | t_f_shell.exe     | Remote Injection | Bypassed |
| Bitdefender TotalSecurity | libcurl.dll       | DLL Side Loading | Bypassed |

---

## 🎥 Proof of Concept (PoC)

> Click on any link to view the execution video.

---

### 🔹 Kaspersky Plus

[![Kaspersky PoC]()](AV/kaspersky_plus_havoc.mp4)

---

### 🔹 Norton

[![Norton PoC]()](AV/norton_havoc.mp4)

---

### 🔹 Malwarebytes

[![Malwarebytes PoC]()](AV/malwarebytes_havoc.mp4)

---

### 🔹 Microsoft Defender

[![Microsoft Defender PoC]()](AV/windows_defender_havoc.mp4)

---

### 🔹 ESET

[![ESET PoC]()](AV/eset_havoc.mp4)

---

### 🔹 Bitdefender TotalSecurity

[![Bitdefender PoC]()](AV/bitdefender_havoc.mp4)

---

## ⚠️ Disclaimer

This project is intended for:

* Security research
* Educational purposes
* Defensive improvement

🚫 Unauthorized use of these techniques is strictly prohibited.


## 🧩 Future Work

* Implement advanced techniques
* Test against enterprise-grade EDR solutions
* Automate multi-AV testing environment
* Add detection telemetry and analysis

