# Encrypted Video Traffic Trace Dataset (CSV)

Privacy-preserving CSV traces of **self-collected encrypted video sessions** from **YouTube / Bilibili / Twitch**, released for reproducible research on **early identification of encrypted video traffic under resource constraints**.

This dataset contains **only**:
- **packet direction** (uplink/downlink relative to the client)
- **packet size** (bytes)
- **relative timestamp** (seconds since session start)

**Not included**: IP addresses, ports, MACs, payloads, URLs, SNI/Host, certificates, JA3/JA4, QUIC CIDs, or any other protocol handshake identifiers.

---

## What’s inside

- **Platforms**: YouTube / Bilibili / Twitch
- **Transport (in our captures)**:
  - **YouTube**: predominantly **QUIC (UDP/HTTP3)**
  - **Bilibili**: predominantly **HTTPS over TCP**, with **TLS 1.2 and TLS 1.3**
  - **Twitch**: **TLS 1.3** (over TCP)
- **Capture setting**: controlled **100 Mbps** access rate, focusing on the **first 30 seconds after video playback starts**.
  > If you need the original PCAP files, please contact **feelingevening@gmail.com**.
---

## Repository structure

