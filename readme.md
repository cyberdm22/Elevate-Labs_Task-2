# Task 2: Analyze a Phishing Email Sample

## Objective
Identify phishing characteristics in a suspicious email sample.

## Tools Used
* **OS:** Kali Linux (Command Line Forensics using `grep`, `less`)
* **Dataset:** Raw `.eml` phishing sample (`sample_phish.eml`)
* **Header Analyzer:** Web-based Email Header Analyzer (Google Admin Toolbox / MXToolbox)

## Executive Summary
This repository contains the forensic analysis of a simulated phishing email mimicking PayPal. The analysis confirms the email is a malicious phishing attempt utilizing email spoofing, deceptive URLs, and social engineering tactics designed to harvest user credentials.

## Phishing Indicators Found

### 1. Social Engineering & Visual Indicators
* **Urgency and Threats:** The subject line explicitly uses "URGENT:" and the body utilizes a common pressure tactic, threatening that "Failure to verify your account within 24 hours will result in permanent suspension."
* **Spelling and Grammar Errors:** The email contains obvious typographical errors, such as "Costumer" instead of Customer, "immediatly" instead of immediately, and a typo-squatted signature "PayPaI" (using a capital 'I' instead of a lowercase 'l').
* **Mismatched URLs (Link Spoofing):** Extracting the URLs revealed a discrepancy. The visible text in the email implies a secure link (`https://www.paypal.com/us/signin`), but the underlying HTML `href` attribute directs the victim to an unencrypted, malicious site: `http://www.update-security-paypal.com/login.php?token=8f9a2b`.

### 2. Technical Header Analysis & Spoofing
* **Sender Mismatch:** The `From:` address is forged to look like `security@paypal.com`, but extracting the `Return-Path:` reveals the true sender domain as `bounces@mail.update-security-paypal.com`.
* **Authentication Failures:** Analysis of the email routing headers shows that SPF, DKIM, and DMARC all registered as `fail`. The sending IP (`103.24.15.99`) is not authorized to send emails on behalf of the legitimate `paypal.com` domain.

## Conclusion
Based on the failed authentication headers, mismatched deceptive URLs, and high-pressure social engineering tactics, this email is a confirmed phishing attempt.
