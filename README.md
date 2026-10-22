# Hostname fallback regression evidence

Synthetic local fixtures only. No scans or network probes were executed.

- Before: upstream commit `a214aba483356b1099445d3a6a47b9935d8bd2d4`.
- After: fix commit `861a50fba37334167b443007ab866ec90356f916`.
- Production standalone builds, Node 22, Chromium-based in-app browser.
- Import `two-hosts.xml`, then select the unnamed secondary host `192.0.2.20`.
- Before, the TLS command uses `-servername primary.example`.
- After, it uses `-servername 192.0.2.20`. The named primary still uses `primary.example`.

The Copy button displayed its success toast. The browser bridge did not expose clipboard contents, so the screenshots establish rendered command text only.
