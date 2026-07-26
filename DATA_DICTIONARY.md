# Data dictionary

The JSON edition is the canonical machine-readable representation. The CSV
edition flattens the same product rows and expands source identifiers into URLs.

| Field | Meaning |
|---|---|
| `product` | Product name used by its publisher |
| `processing` | Where microphone audio becomes a transcript in the documented path |
| `configurableCloudPath` / `configurable_cloud_path` | Optional provider, hosted model, cleanup, assistant, sync, or agent paths that can change what leaves the Mac |
| `offline` | Whether the documented speech-to-text path can work without a live connection after required setup |
| `retention` | What the publisher says it or a named processor keeps |
| `account` | Account, subscription, license, provider-key, or synced-history boundary |
| `platform` | Documented platform and hardware requirements |
| `caveat` | Qualification needed to avoid overgeneralizing the claim |
| `sourceIds` | JSON references into the top-level `sources` collection |
| `source_urls` | CSV list of the first-party URLs supporting the row |

## Interpretation rules

- `processing` covers the audio-to-transcript step, not every later use of the
  resulting text.
- `offline` is configuration-specific. A local mode does not make optional
  connected modes local.
- A no-retention statement can describe storage after a cloud request; it does
  not by itself establish on-device processing.
- Account and license traffic can exist even when speech processing is local.
- Text inserted into another app follows that destination's own storage,
  sharing, telemetry, and retention rules.
- Missing documentation is recorded as uncertainty, not converted into a
  favorable or unfavorable claim.
