# Arcads runtime logs

Runtime API logs are generated locally and are not committed. They may contain timestamps, endpoint names, model choices, asset/product/project identifiers, credit usage, output URLs, and request metadata. Treat them as private operational data.

The `arcads-api.jsonl` path is reserved for local runtime use. Git ignores this path. Before sharing logs, remove identifiers, URLs, prompts, and customer/product details. Apply the account's retention and deletion policy.

No public sample log is included in this repository. No log replay or cost-estimation behavior is guaranteed by this README.
