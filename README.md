# scoop-bucket

Scoop manifests for tools by [sinnerk](https://github.com/sinnerk).

## Add the bucket

```powershell
scoop bucket add sinnerk https://github.com/sinnerk/scoop-bucket
```

Scoop asks for nothing else, installs into your user profile, and needs no admin rights.

## envdoctor

A read-only health check for a Windows dev environment: PATH health, Microsoft Store stubs,
duplicate toolchains, long-path support, cache bloat, occupied dev ports and git config. One
static binary, no dependencies, no telemetry, no network access.

```powershell
scoop install envdoctor
envdoctor
```

Update and remove it the usual way:

```powershell
scoop update envdoctor
scoop uninstall envdoctor
```

The tool lives at [sinnerk/envdoctor](https://github.com/sinnerk/envdoctor); use its issue
tracker for bugs and the [checks reference](https://github.com/sinnerk/envdoctor/blob/main/docs/CHECKS.md)
to understand a finding.

## What is in this bucket

| Manifest | Upstream | What it does |
| --- | --- | --- |
| `envdoctor.json` | [sinnerk/envdoctor](https://github.com/sinnerk/envdoctor) | Diagnoses a broken Windows dev setup and scores it out of 100. |

## How updates work

Each manifest carries a `checkver` pointing at the upstream GitHub releases and an
`autoupdate` URL template, so `scoop update` picks up new versions without a manifest edit.
When a release changes the asset name or adds an architecture, the manifest is updated by hand
and the hash is regenerated.
