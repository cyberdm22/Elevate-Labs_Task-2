# Elevate-Labs_Task-2
Task 2: Analyse a Phishing Email Sample.
# Task 2: Analyze a Phishing Email Sample

## Objective
Identify phishing characteristics in a suspicious email sample to develop awareness of phishing tactics and email threat analysis skills.

## Tools Used
* Dataset: Raw phishing email sample (.eml text)
* Tool: VirusTotal/ AbuseIPDB/ DNS Lookups/ MXToolbox / Google Admin Toolbox (Free Online Header Analyzer)

## Executive Summary
This report summarizes the phishing traits found in the analyzed email sample. The email attempts to use social engineering to trick the user into [state the goal, e.g., giving up credentials]. 

## Phishing Indicators Found

### 1. Social Engineering & Visual Discrepancies
* **Urgent/Threatening Language:** The email creates a false sense of urgency by stating "[insert quote from email]".
* **Spelling and Grammar:** Several errors were found, such as "[insert error]". 
* **Mismatched URLs:** Hovering over the link revealed a deceptive URL. The text displayed was `[fake link]`, but the actual destination was `[malicious link]`.
* **Suspicious Attachments:** The email included a highly suspicious attachment named `[attachment name]`.

### 2. Technical Header Analysis & Spoofing
* **Sender Discrepancy:** Examining the sender's email address for spoofing revealed that while the `From` address was `[fake sender]`, the actual `Return-Path` was `[real attacker email]`.
* **Header Discrepancies:** The header analysis tool flagged that the sender failed SPF and DKIM authentication checks, confirming the email is spoofed.

## Conclusion
Based on the urgent language, mismatched URLs, and failed header authentication, this email is a confirmed phishing attempt.
