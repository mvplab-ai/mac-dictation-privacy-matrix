# Data dictionary

The JSON edition is the canonical machine-readable representation. The CSV
edition flattens the same product rows and expands source identifiers into URLs.

## Top-level summary

`summary.stats` publishes four named documentation cohorts. Each cohort has a
stable `id`, a `value`, an optional `denominator`, a reader-facing `label` and
`description`, a `products` list when the count is product-based, and a
`caveat`. For every product-based cohort, `value` equals the length of
`products`.

| Summary ID | Meaning |
|---|---|
| `documentedLocalPath` | Products with at least one documented local or on-device speech-to-text path in a supported configuration |
| `noDocumentedLocalPath` | Products whose reviewed sources establish cloud speech but no local speech-to-text path |
| `localPlusConnected` | Locally capable products that also document an optional provider, cleanup, assistant, vocabulary, or agent path |
| `firstPartySources` | Number of first-party sources represented in the top-level `sources` collection |

`documentedLocalPath` and `noDocumentedLocalPath` are disjoint and together
cover all 17 product rows. `localPlusConnected` is a subset of
`documentedLocalPath`. A connected path does not necessarily send microphone
audio; the cohort includes transcript text, selected text, vocabulary data,
and finished-specification paths.

## Product fields

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
- Summary cohorts describe reviewed documentation, not independent binary
  verification, security certification, or a universal product ranking.
