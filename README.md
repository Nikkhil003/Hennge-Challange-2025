# HENNGE Global Internship Program Challenge 2025

This repository contains the solution to **Mission 1** of the HENNGE challenge, as part of the **Global Internship Program**. The challenge involves processing structured input data, publishing a private solution, and submitting a secure POST request with TOTP-based authentication.

---

## 📌 Mission 1 – Problem Summary

**Goal**:  
Process multiple test cases where each contains:
- An integer `X` representing the expected count of numbers.
- A line with space-separated integers `Yn`.

**Requirements**:
- For each test case, sum the **fourth powers** of non-positive integers in `Yn`.
- If the actual count of integers is not equal to `X`, output `-1` for that test case.
- No intermediate output — only final results after all input is received.

**Constraints**:
- No `for`/`while` loops or comprehensions.
- No global variables.
- Must work with hidden inputs and standard input/output only.

---

## ✅ Mission 2 – Publish as a Secret Gist

For this mission, the solution (`main.py`) must be published as a **secret GitHub Gist**:

1. Go to [https://gist.github.com](https://gist.github.com)
2. Create a new **secret** Gist (not public)
3. Name the file `main.py` and paste your complete solution
4. Save the Gist and copy the generated URL

This Gist URL will be used in Mission 3 for final submission.

> Note: Replace `YOUR_USERNAME` and `YOUR_GIST_ID` with the actual values before submission.

---

## ✅ Mission 3 – Secure Submission

To complete the third mission:
- A JSON payload was created with:
  - `github_url`: Link to the secret gist
  - `contact_email`: My submission email
  - `solution_language`: "python"

- The payload was submitted to the HENNGE API using:
  - `Content-Type: application/json`
  - **HTTP Basic Auth** where:
    - Username: My email
    - Password: 10-digit **TOTP** generated per [RFC6238](https://datatracker.ietf.org/doc/html/rfc6238) using:
      - HMAC-SHA512
      - Time step: 30 seconds
      - Secret key: `email + "HENNGECHALLENGE004"`

---

## 💡 TOTP Generation

A custom script was written to compute the TOTP using Python's `hmac` and `hashlib` libraries to fulfill RFC6238 with SHA-512, ensuring compatibility with HENNGE's server.

---

## 📝 Technologies Used

- Language: Python 3.13 (as of January 2025) or higher.
- Libraries: Standard Library Only (no third-party packages)
- Tools: GitHub Gist, curl, RFC-compliant TOTP generator

---
