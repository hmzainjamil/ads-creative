# Meta Ads utility

Python utilities for a manual workflow around the Meta Ad Library API. They fetch ads for specified pages or discover candidate page IDs from a supplied website/keyword search, extract media URLs from snapshot pages with Selenium, save records to JSON, and optionally write records to Airtable. They do not publish or edit ads.

## Requirements

- Python packages listed in `requirements.txt`
- Chrome and ChromeDriver support for Selenium creative extraction
- `META_ACCESS_TOKEN` for Meta Graph API requests
- Optional `AIRTABLE_PAT` and an Airtable base ID for schema creation or record writes
- Optional `openai-whisper` and ffmpeg for local video transcription

No dependency lock or validated platform setup is included. Check current official Meta and Airtable documentation, access requirements, and terms before use.

## Setup

Create a local `.env` from the example and set credentials only when needed. Protect the token and grant least required access.

Inspect the available options before running:

```sh
python3 pull_ads.py --help
python3 discover_competitors.py --help
python3 setup_table.py --help
```

These commands have not been executed in this review. `pull_ads.py` requires `--pages`, writes JSON to `ads_output/ads.json` by default, and can request Airtable writes with `--write-to-airtable --base-id ...`. It uses Selenium to visit Meta Ad Library snapshot URLs unless `--skip-creatives` is set. The optional `--transcribe` path downloads video files and transcribes them locally with Whisper.

## Data behavior

The JSON/Airtable schema includes ad/page identifiers, copy, headlines, creative references, landing-page and Ad Library links, status/date fields, and some targeting or media metadata when present in API responses. Results depend on the API response and access available to the account; fields may be empty. The code does not establish that every field is available or accurate for every ad.

The competitor-discovery utility fetches a supplied website URL and uses text-derived keywords in API searches. Use only authorized public URLs; do not point it at internal services or private systems.

## Limits and review

This tool collects third-party advertising material. Review platform terms, privacy, copyright, and permitted reuse before exporting, transcribing, or republishing results. API availability, permissions, endpoint versions, and terms can change.

No live API calls, browser sessions, Airtable writes, transcription, tests, or deployment were performed for this review. The repository has no documented release or support process.
