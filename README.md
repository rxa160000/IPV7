# IPV7

🌐 IPv7 — A human-readable, flexible, and massive-scale addressing system for the future internet. Next Generation Addressing System


📖 Overview

IPv7 is an experimental network addressing system designed as an alternative to IPv4 and IPv6.
It introduces numeric and alphanumeric formats with flexible block sizing, case-sensitive characters, and symbolic meaning — while remaining compatible with IPv4/IPv6 through translation layers.

IPv7 aims to provide:

- Human-readable yet machine-parsable addresses

- Flexible structure for zones, device types, groups, and IDs

- Symbolic representation via alphanumeric blocks

- Large-scale address space suitable for IoT, operating systems, and experimental protocols

🔢 Numeric Format
1AAAA.BBBB.CCCC.DDDD

-4 blocks separated by .
-Each block length depends on prefix /n
-First digit (e.g., 1) indicates class

Examples by Prefix:

/3 → 123.456.789.012

/6 → 123456.654321.111222.333444

/12 → 123456789012.987654321000.111222333444.555666777888

🔠 Alphanumeric Format
Bloc1.Bloc2.Bloc3.Bloc4

- 4 blocks separated by " . "
- Each block contains exactly n characters (depending on /n)
- Allowed characters:
- Uppercase (A–Z)
- Lowercase (a–z)
- Digits (0–9)
- Case-sensitive: IPv7 ≠ ipv7

Examples by Prefix:

/3 → Rik.Ali.Net.OS

/4 → RikY.AliA.Test.LovE

/12 → R1kYaLiA0001.lOvESeRvEr01.NeTwOrKnOdE12.TeStCaSe0009

⚙️ Addressing Rules

Separator: " . "  (dot) is mandatory between blocks

Prefix /n: defines block length (from /3 to /12)

/3 → 3 characters per block

/12 → 12 characters per block

Numeric Mode: digits only (0–9)

Alphanumeric Mode: base-62 (A–Z, a–z, 0–9)

Subnetting: hierarchical, similar to CIDR in IPv4/IPv6

Subnet Examples:

/3 → RikY.*.*.* (all addresses starting with RikY)

/6 → RikY.AliA.*.* (all under RikY.AliA)

/12 → RikY.AliA.0001.LoVe (single host)


🌐 IPv4/IPv6 Compatibility

IPv7 addresses can be mapped into existing IPv4/IPv6 infrastructure:

- IPv7 → IPv4 mapping
Numeric addresses compressed into 32-bit space.
Example: 123.456.789.012 (/3) → 192.168.0.1

- IPv7 → IPv6 mapping
Alphanumeric addresses encoded into IPv6 hexadecimal fields.
Example: RikY.AliA.0001.LoVe (/4) → 2001:db8:7269:6b79:616c:6961:3030:3031

This ensures IPv7 nodes remain interoperable with the current internet.

🔐 Security Considerations

IPv7 is designed with security awareness from the ground up:

- Structured Allocation:
Unlike arbitrary free-form addresses, IPv7 uses a prefix system (/3–/12) that enforces valid block lengths. This prevents malformed or ambiguous addresses.

- Case-Sensitive Blocks:
Alphanumeric blocks support uppercase, lowercase, and digits, but must follow defined syntax rules. This avoids spoofing attempts (e.g., love ≠ LoVe).

- Reserved Blocks:
Certain ranges/zones can be reserved for system-level usage (e.g., loopback, multicast, private networks), preventing conflicts and abuse.

- Validation Layer:
IPv7 includes a parsing layer that rejects addresses that do not conform to prefix/block rules. This ensures no “random” or invalid addresses are injected into the system.

- Compatibility Security:
When mapping to IPv4/IPv6, translation must enforce strict checksum/validation so attackers cannot bypass security via malformed mappings.

- Future Potential:
IPv7 can integrate cryptographic identity binding, where blocks may embed signatures or hashes to validate authenticity of the device or group.

🚀 Key Features

- Flexible addressing /3 … /12
- Numeric and alphanumeric formats
- Case-sensitive symbolic addressing
- Human-readable and machine-parsable
- IPv4/IPv6 interoperability
- Massive address space
- Numeric: ~10^17
- Alphanumeric: ~10^27

🔧 Use Cases

- IoT addressing (ESP32, Arduino, embedded systems)
- Alternative networking in experimental OS 
- Research on next-generation internet protocols

📦 Getting Started

Clone this repository:

git clone https://github.com/username/IPv7.git
cd IPv7


Parser, simulator, and IPv7-to-IPv4/IPv6 gateway will be provided in upcoming releases.

📜 License

This project is licensed under the MIT License
.
You are free to use, modify, and distribute with proper attribution.

👤 Author

Developed by Rizqi Bayu Pratama (Rikiya)
"Reimagining IP addressing — from numbers to identities."
