# Mac Dictation Privacy Matrix

An open, source-reviewed dataset comparing the documented privacy boundaries of
17 Mac dictation products.

The matrix separates questions that are often collapsed into one label:

- where microphone audio becomes a transcript;
- whether an optional cloud, cleanup, assistant, or agent path exists;
- whether the documented speech path works offline after setup;
- what the publisher says it retains;
- which account, subscription, license, or provider boundary applies; and
- which platform requirements and caveats materially qualify the claim.

This repository is a distribution mirror for the canonical research page:

**[Private Mac Dictation Apps: Local vs Cloud (2026)](https://iravoice.com/research/mac-dictation-privacy-matrix)**

## Data

| File | Use |
|---|---|
| [`data/mac-dictation-privacy-matrix.csv`](data/mac-dictation-privacy-matrix.csv) | Flat rows for spreadsheets and analysis |
| [`data/mac-dictation-privacy-matrix.json`](data/mac-dictation-privacy-matrix.json) | Structured metadata, methodology, product rows, caveats, and source records |
| [`DATA_DICTIONARY.md`](DATA_DICTIONARY.md) | Field definitions and interpretation rules |

Current release: **1.2.0**

Last reviewed: **2026-07-26**

Products: **17**

First-party sources: **31**

## Method

1. Review current first-party product, help, security, and privacy pages.
2. Separate speech transcription from later cleanup, formatting, assistant,
   sync, or destination processing.
3. Describe configurable modes explicitly instead of transferring a local or
   retention claim from one mode to every mode.
4. State what the reviewed documentation does not establish.
5. Publish the same product order in the HTML, CSV, and JSON editions.

## Important limitation

This is documentation research published by IraVoice, not an independent
security audit, packet inspection, source-code review, or product ranking.
IraVoice appears as one row and is identified as the publisher. Verify
time-sensitive claims against the linked first-party sources and the active
product configuration.

“Local,” “cloud,” “offline,” and “zero retention” are not interchangeable:

- local transcription does not prove that optional cleanup or the destination
  is local;
- zero retention does not mean audio was never transmitted;
- offline availability may depend on model, app, or license setup; and
- the destination app creates a separate privacy and retention boundary after
  text is inserted.

## Integrity

SHA-256:

```text
6210a03dd9865648c110730688d9e50c822e8577c37e63c4526f6b01a0e1065c  data/mac-dictation-privacy-matrix.csv
1fb0183b584a953ea9166f6f158d87dc1de84b72467d92b84b5f6bcc29a19b20  data/mac-dictation-privacy-matrix.json
```

## Corrections

Open an issue with:

1. the product and field that needs correction;
2. the exact first-party URL;
3. the relevant dated language; and
4. the proposed replacement wording.

Unsupported marketing claims, affiliate roundups, and undated third-party
summaries are not accepted as primary evidence.

## Citation

Use the repository's [`CITATION.cff`](CITATION.cff), or cite:

> IraVoice for Mac. *Mac Dictation Privacy Matrix: Local vs Cloud*. Version
> 1.2.0, reviewed 2026-07-26.
> https://iravoice.com/research/mac-dictation-privacy-matrix

## License

The dataset and documentation in this repository are licensed under
[Creative Commons Attribution 4.0 International](LICENSE).
