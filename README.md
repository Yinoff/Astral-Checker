# AutoClicker Integrity Checker

**AutoClicker Integrity Checker** is a Python-based tool designed to verify the integrity of AutoClicker executable files and identify potential unauthorized modifications.

## Features

- **File Integrity Verification:** Calculates cryptographic fingerprints to determine whether an executable matches a known legitimate release.
- **Multiple Version Support:** Recognizes different official versions of the AutoClicker.
- **VirusTotal Integration:** Retrieves existing file analysis reports through the VirusTotal API.
- **PE File Analysis:** Extracts additional executable identification information, including PE-related hashes.
- **Modification Detection:** Identifies executables that do not match any of the registered legitimate versions.
- **Security Analysis:** Displays available VirusTotal detection statistics, including malicious and suspicious detections.
- **Local Processing:** Calculates file fingerprints locally without automatically uploading executable files to VirusTotal.

## Requirements

- Python 3.15 (or a compatible Python version).
- `requests`
- `pefile`
- A VirusTotal API key (optional).

## Installation

Install the required dependencies:

```bash
pip install requests pefile
```

## Usage

Run the program:

```bash
python main.py
```

1. Select the executable file you want to inspect.
2. The program calculates its identification fingerprints.
3. The executable is compared against registered legitimate versions.
4. Optionally, provide a VirusTotal API key to retrieve its existing analysis report.
5. Review the verification results and security information.

## Verification Results

| Result | Description |
|---|---|
| Original Recognized | The executable matches a registered legitimate version. |
| Unknown Executable | The executable does not match any registered version. |
| VirusTotal Report Available | An existing analysis report was retrieved successfully. |
| File Not Found | VirusTotal has no report associated with the queried file. |

**Important:** An unknown executable is not automatically malicious. It may be a modified, rebuilt, or otherwise different legitimate version.

## VirusTotal Integration

The application uses the VirusTotal API v3 to retrieve existing reports using the executable's fingerprint.

It does not automatically upload files, helping avoid unintended sharing of private executables.

## Disclaimer

This tool is intended for software integrity verification and defensive security purposes.

A matching fingerprint establishes that the inspected file is identical to a registered reference under that fingerprint. It does not guarantee that the software is completely free of vulnerabilities or malicious behavior.

---

**AutoClicker Integrity Checker**  
*Executable Integrity Verification Tool*
