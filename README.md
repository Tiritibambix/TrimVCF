# TrimVCF

TrimVCF is a simple Python script to clean VCF (vCard) files by removing dashes (`-`) from all phone number (`TEL`) lines. This is useful when standardizing phone number formats for import/export between contact systems.

## Features

- Removes all `-` characters from phone numbers in `TEL` lines.
- Supports large VCF files.
- Keeps the rest of the VCF file unchanged.
- Optional output file path.

## Usage

```bash
python clean_tel_vcf.py input.vcf [--output cleaned.vcf]
```

### Arguments

| Argument       | Description                              |
|----------------|------------------------------------------|
| `input.vcf`    | Path to the original VCF file             |
| `--output`     | (Optional) Output file path (default: `cleaned.vcf`) |

### Example

```bash
python clean_tel_vcf.py contacts.vcf --output contacts_clean.vcf
```

## Installation

No external dependencies are required. Works with Python 3.7+.

```bash
git clone https://github.com/yourusername/TrimVCF.git
cd TrimVCF
python clean_tel_vcf.py --help
```

## License

GPL3

---

Feel free to contribute or suggest improvements!
