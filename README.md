# 🧪 Basic SQLi Scanner

Basic SQLi Scanner is a Python-based CLI tool that performs simple SQL injection
testing on a single parameter by analyzing server responses.

It is designed for learning purposes and demonstrates how SQL injection
can be detected using response behavior.

---

## Overview

SQL injection vulnerabilities often reveal themselves through changes in:
- Response length
- Error messages
- HTTP status codes
- Response time

This tool sends multiple SQL payloads to a specified parameter
and compares the responses against a normal baseline request.

---

## Features

- Tests a single URL parameter for SQL injection
- Uses classic boolean, error-based, union-based, and time-based payloads
- Compares response length with baseline
- Detects SQL error messages in responses
- Checks HTTP status code differences
- Identifies response delays for time-based payloads
- Prints clear findings directly to the terminal

---

## How It Works

The scanner first sends a normal request to establish a baseline response.

For each SQL payload:
- The payload is injected into the specified parameter
- A request is sent to the target URL
- The response is analyzed for:
  - Length anomalies
  - SQL error keywords
  - Status code mismatches
  - Response time delays
  - Suspicious SQL comment behavior

If anomalies are detected, a possible SQL injection is reported.

---

## Usage

Run the scanner exactly like this  
python sqli_scanner.py -u <url> -p <parameter>

Example  
python sqli_scanner.py -u https://example.com/item.php -p id

The scanner will test multiple payloads automatically and print results live.

---

## Output

For each payload, the tool displays:
- Payload being tested
- Response length comparison
- Possible SQL injection indicators (if found)

Possible detections include:
- Error-based SQL injection
- Boolean-based SQL injection
- Time-based SQL injection
- General response anomalies

---

## Requirements

- Python 3.x
- requests library

Install dependencies if needed  
pip install requests

---

## Notes

- This tool tests only one parameter at a time
- Payloads are intentionally simple and noisy
- False positives are possible
- Intended strictly for learning and authorized testing

---

## Final Thoughts

SQL injection is about observing behavior, not just errors.
This tool helps build the habit of watching how applications respond
to unexpected input.
