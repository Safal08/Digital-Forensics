README.md — autorun.inf / README.pdf Analysis

## Summary:

This repository contains a short analysis of an autorun-based dropper that references README.pdf. Static inspection and PDF object analysis show README.pdf is malicious: it embeds a Windows executable and contains an /OpenAction JavaScript that exports the payload. The PDF is flagged as malicious on VirusTotal.

## Files examined

autorun.inf — (provided artifact)
README.pdf — referenced by autorun.inf
extracted_cmd.exe — extracted embedded file (named cmd.exe inside the PDF)

Important: Do not open README.pdf or extracted_cmd.exe on a host OS. All analysis was performed in an isolated VM/sandbox.

## Environment / tools used

Linux (analysis VM)
hexdump / xxd — inspect raw bytes
file — identify file types
sha256sum — compute hashes
extract embedded files
pdf-parser.py — inspect PDF objects and JavaScript
VirusTotal — file reputation

## Takeaways

1. The autorun.inf file was set up to automatically open a malicious README.pdf.
2. The PDF file’s header confirmed it was a real PDF, not a renamed executable.
3. Inside the PDF, an embedded cmd.exe file was found — clear sign of malware.
4. The PDF contained an /OpenAction that ran JavaScript to export the embedded file.
5. This means the PDF was designed to drop and potentially execute malware on Windows.
6. VirusTotal confirmed the file as malicious.
