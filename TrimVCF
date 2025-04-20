# file: clean_tel_vcf.py

import argparse
from pathlib import Path

def parse_args():
    parser = argparse.ArgumentParser(description="Clean TEL lines in a VCF file by removing dashes (-).")
    parser.add_argument("input_path", help="Path to the .vcf file")
    parser.add_argument("-o", "--output", default="cleaned.vcf", help="Output path (default: cleaned.vcf)")
    return parser.parse_args()

def clean_tel_lines(lines: list[str]) -> list[str]:
    cleaned = []
    for line in lines:
        if line.upper().startswith("TEL"):
            parts = line.split(":", 1)
            if len(parts) == 2:
                prefix, number = parts
                number = number.replace("-", "")
                cleaned.append(f"{prefix}:{number}")
            else:
                cleaned.append(line)
        else:
            cleaned.append(line)
    return cleaned

def main():
    args = parse_args()
    input_file = Path(args.input_path)

    if not input_file.is_file():
        print(f"File not found: {input_file}")
        return

    with input_file.open("r", encoding="utf-8") as f:
        lines = f.readlines()

    cleaned_lines = clean_tel_lines(lines)

    with open(args.output, "w", encoding="utf-8") as f:
        f.writelines(cleaned_lines)

    print(f"Cleaned file written to: {args.output}")

if __name__ == "__main__":
    main()
