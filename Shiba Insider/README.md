# PCAP Analysis and Steganography Investigation

## 🧩 Project Overview

This project demonstrates a digital forensics workflow — starting from analyzing a **network capture (PCAP)** file, to uncovering hidden information embedded within an image using **steganography** techniques.

The main steps include:

1. **Analyzing a PCAP file** to extract useful data such as messages and a password.
2. **Extracting and unlocking a ZIP file** using the discovered password.
3. **Inspecting metadata** of a JPEG image using `exiftool`.
4. **Detecting and extracting hidden data** embedded in the image using steganography tools.
5. **Use steghide to uncover the hidden message inside image** use `steghide`

---

## Process Details

### PCAP Analysis

- Used **Wireshark** to analyze the captured network traffic.
- Extracted **response messages** and identified a **ZIP file password** transmitted in plaintext.
