# n4uu

Malware analysis, threat intelligence, detection engineering, offensive tooling.

## Projects

### North Korean operations against developers

Three tools, one per stage: the npm release that delivers the implant, the implant itself, and the infrastructure behind it.

**[graft](https://github.com/n4uu/graft)**
Finds compromised releases in npm dependency trees: the stolen-token pattern behind the axios (March 2026) and Mastra (June 2026) compromises, where a trusted package suddenly grafts on a day-old dependency with an install script. Reads each release's registry paper trail (trusted publishing and provenance dropped, publisher changes, impersonation, bursts across unrelated projects), sweeps node_modules and the npm cache for incident response, and reports to GitHub code scanning. Calibrated on real trees of 384 and 3,146 packages with no false positive at medium or above.

**[crumble](https://github.com/n4uu/crumble)**
Config extractor, C2 traffic decoder and detection rules for OtterCookie. Undoes javascript-obfuscator's string array by running the sample's own decoder in an isolated VM, emulates the implant behind recording Node.js stubs to recover its socket.io C2, check-in and staged code, and rebuilds operator sessions from pcap (Engine.IO v3/v4, WebSocket with permessage-deflate). Ships tested YARA and Sigma rules.

**[prowl](https://github.com/n4uu/prowl)**
Infrastructure hunting from public telemetry. Seeds from ThreatFox, pivots through URLhaus, certificate transparency, DNS and ASN data, scores every indicator with an explainable log-odds model (correlated evidence damped, sightings decayed, CDNs and shared hosting kept out), and exports MISP and STIX 2.1.

### Malware and detection

**[wraith](https://github.com/n4uu/wraith)**
eBPF sensor for fileless execution and process injection on Linux. Six tracepoint-level rules mapped to MITRE ATT&CK, running entirely in-kernel with no file-hash heuristics and no cloud lookups.

**[husk](https://github.com/n4uu/husk)**
Clean-room Cobalt Strike Beacon configuration extractor. Recovers the XOR key and offset by brute force rather than hardcoded signatures, then decodes the full TLV config, including the Malleable C2 instruction opcodes.

### Offensive

**[snitch](https://github.com/n4uu/snitch)**
Single static-binary recon orchestrator chaining subfinder, httpx, nmap, nuclei, ffuf, and katana with injection testing (dalfox, crlfuzz, sqlmap). Dedupes findings and exports JSON, CSV, and SARIF.

**[wireguardian](https://github.com/n4uu/wireguardian)**
Fail-closed opsec guard for WireGuard. Verifies exit IP and checks for DNS/IPv6 leaks before you touch a target, with a kill switch built in.

## Focus

- Reverse engineering C2 protocols and implant configuration formats
- Threat intelligence on DPRK-nexus developer-targeting campaigns: npm supply chain, sample triage, infrastructure pivoting, MISP/STIX output
- Kernel-level detection engineering: eBPF, syscall tracing
- Detection content (YARA, Sigma) shipped with positive and negative tests
- Offensive tooling for authorized engagements

## Contact

n47_03@pm.me
