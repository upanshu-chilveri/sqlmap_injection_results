# SQL Injection Documentation - UCEOU

This repository documents the results during a web application security analysis that lead to the identification of:

- **Time-Based Blind SQL Injection**
- **Boolean-Based Blind SQL Injection**

The purpose of this repository is documentation of methodology and technical workflow, and the results obtained in the Reconnaissance of the website.

---

## Assessment Process

### 1. Attack Surface Mapping
- Identified accessible endpoints and user-controlled parameters.
- Observed request methods (GET/POST) and parameter transmission.
- Established how input influenced backend processing.

### 2. Traffic Interception & Analysis
- Routed application traffic through an intercepting proxy.
- Inspected request structure, headers, and parameter encoding.
- Modified parameters incrementally to observe:
  - Logical response differences  
  - Response time variations  
  - HTTP status changes  

Behavioral inconsistencies indicated potential SQL interaction.

### 3. Manual Injection Validation
- Tested parameters using controlled logical conditions.
- Observed differential responses for Boolean conditions.
- Introduced timing-based payloads to detect delayed execution patterns.

These indicators confirmed blind injection behavior.

### 4. Automated Confirmation & Enumeration
- Validated injection vectors using `sqlmap`.
- Fingerprinted backend DBMS.
- Enumerated databases and tables.
- Performed controlled data extraction.
- Preserved session and execution logs for documentation.

---

## Tools Used

- **Burp Suite** — HTTP interception and parameter analysis  
- **sqlmap** — Injection validation and database enumeration  
- **Nmap** — Service reconnaissance  

---


<table>
  <tr>
    <td><img width="1854" height="1048" alt="image" src="https://github.com/user-attachments/assets/9a94042e-074e-45d0-8b7a-96410d4a7c33" /> </td>
    <td><img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d3888746-3adb-4bea-b9b9-3219c953c1f1" /> </td>
  </tr>
   <tr>
    <td><img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/8785f181-829c-480a-b1c7-669aeacb40c8" /> </td>
    <td><img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d857600b-b3eb-4d65-a8b5-9334681e9e85" /> </td>
  </tr>
  <tr>
    <td><img width="750" height="464" alt="image" src="https://github.com/user-attachments/assets/06100a39-8de6-4b93-a63c-5a55b3aadffa" /> </td>
    <td><img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1704f187-367c-47a3-942c-b58727ed3213" /> </td>
  </tr>
</table>



## Key Observations

- Manual behavioral analysis preceded automation.
- Boolean-based discrepancies revealed backend query manipulation.
- Time-based payloads confirmed blind execution paths.
- Automation was used for validation and structured enumeration, not initial discovery.

---

All activities referenced in this repository were conducted in an authorized environment for educational and security research purposes only.
