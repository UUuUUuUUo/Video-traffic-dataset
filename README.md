# Encrypted Video Traffic Trace Dataset (CSV)

Privacy-preserving CSV traces of **self-collected encrypted video sessions** from **YouTube / Bilibili / Twitch**, released for reproducible research on **early identification of encrypted video traffic under resource constraints**.

This dataset contains **only**:
- **packet direction** (uplink/downlink relative to the client)
- **packet size** (bytes)
- **relative timestamp** (seconds since session start)

**Not included**: IP addresses, ports, MACs, payloads, URLs, SNI/Host, certificates, JA3/JA4, QUIC CIDs, or any other protocol handshake identifiers.

### Notes
- Every 50 sessions are saved into a single CSV file.

---

## What’s inside

- **Platforms**: YouTube / Bilibili / Twitch
- **Transport (in our captures)**:
  - **YouTube**:  **QUIC (UDP/HTTP3)**
  - **Bilibili**: observed **both** (i) **HTTPS over TCP** with **TLS 1.2 / TLS 1.3**, and (ii) **QUIC over UDP (HTTP/3)** in some sessions
  - **Twitch**: **TLS 1.3** (over TCP)
- **Capture setting**: controlled **100 Mbps** access rate, focusing on the **first 30 seconds after video playback starts**.


### Header

The CSV contains **two columns**:

| column | type | description |
|---|---:|---|
| `rel_ts_us` | int | Relative packet arrival time in **microseconds (µs)** since the first packet of the session (`rel_ts_us >= 0`). |
| `len` | int | **Total packet length** in bytes. |

### Notes

- `rel_ts_us` is **relative time** (not wall-clock time).
- `len` is the total packet length in bytes (consistent with how packets were exported from the capture pipeline).



## Repository structure
```text
├── DataSet/
│   ├── YouTube/
│   │   ├── 1080/
│   │   ├── 720/
│   │   └── 480/
│   ├── Twitch/
│   │   ├── 1080/
│   │   ├── 720/
│   │   └── 480/
│   └── BiliBili/
│       ├── 1080/
│       ├── 720/
│       └── 480/
└── README.md
```
### Notes
Due to repository size limits, we only upload a **subset** of the CSV files. If you need **all CSV files** or the **original PCAP files**, please contact **feelingevening@gmail.com**.

