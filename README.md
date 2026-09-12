# n4uu

Malware analysis, detection engineering, offensive tooling.

## Projects

**[wraith](https://github.com/n4uu/wraith)**
eBPF sensor for fileless execution and process injection on Linux. Six tracepoint-level rules mapped to MITRE ATT&CK, running entirely in-kernel with no file-hash heuristics and no cloud lookups.

**[husk](https://github.com/n4uu/husk)**
Clean-room Cobalt Strike Beacon configuration extractor. Recovers the XOR key and offset by brute force rather than hardcoded signatures, then decodes the full TLV config, including the Malleable C2 instruction opcodes.

**[snitch](https://github.com/n4uu/snitch)**
Single static-binary recon orchestrator chaining subfinder, httpx, nmap, nuclei, ffuf, and katana with injection testing (dalfox, crlfuzz, sqlmap). Dedupes findings and exports JSON, CSV, and SARIF.

**[wireguardian](https://github.com/n4uu/wireguardian)**
Fail-closed opsec guard for WireGuard. Verifies exit IP and checks for DNS/IPv6 leaks before you touch a target, with a kill switch built in.

## Focus

- Reverse engineering C2 protocols and implant configuration formats
- Kernel-level detection engineering: eBPF, syscall tracing
- Offensive tooling for authorized engagements

## Contact

n47_03@pm.me
