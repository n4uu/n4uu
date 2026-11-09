# n4uu

I write up what I find, ship detections for it and report the
indicators.

Blog: https://n4uu.github.io

## Writing

**[A raw TCP backdoor behind the cleverstack git hook lure](https://n4uu.github.io/2026/raw-tcp-backdoor-cleverstack/)** (Nov 2026)
Two files tagged BeaverTail turned out to be a Node.js backdoor that talks
newline-delimited JSON over plain TCP. Delivery chain, protocol, and the three
ways the samples broke my own tooling.

**[What the npm registry remembers](https://n4uu.github.io/2026/what-the-npm-registry-remembers/)** (Nov 2026)
Rebuilding the axios, easy-day-js and qix compromises from registry metadata
alone, with the `curl` and `jq` to check every timestamp.

## Detections and indicators upstream

- [SigmaHQ/sigma#6568](https://github.com/SigmaHQ/sigma/pull/6568): Sigma rules for the raw TCP backdoor (lock file, detached `ss_exec` tasking).
- [Neo23x0/signature-base#434](https://github.com/Neo23x0/signature-base/pull/434): YARA that matches the obfuscated backdoor as distributed.
- Indicators reported to ThreatFox and URLhaus as n4uu.
- [apache/superset#43504](https://github.com/apache/superset/pull/43504): a theme's loading spinner SVG was rendered inline after regex sanitization; it now loads through an `<img>` data URI. Merged September 2026.

## Tools

For the DPRK work, one per stage:

- **[graft](https://github.com/n4uu/graft)** finds compromised releases in npm dependency trees from the registry paper trail (provenance dropped, new publisher, a day-old dependency with an install script). No false positive at medium or above on real trees of 384 and 3,146 packages.
- **[crumble](https://github.com/n4uu/crumble)** pulls config and C2 out of OtterCookie and related implants, decodes their socket.io traffic from pcap and ships the YARA, Sigma and Suricata rules I use.
- **[prowl](https://github.com/n4uu/prowl)** pivots from ThreatFox seeds through URLhaus, certificate transparency, DNS and ASN data, scores what it finds and exports MISP and STIX.

Other things I built:
[wraith](https://github.com/n4uu/wraith) (eBPF sensor for fileless execution and injection on Linux),
[husk](https://github.com/n4uu/husk) (Cobalt Strike Beacon config extractor),
[snitch](https://github.com/n4uu/snitch) and [wireguardian](https://github.com/n4uu/wireguardian) (recon and opsec helpers for authorized work).

## Contact

n47_03@pm.me
