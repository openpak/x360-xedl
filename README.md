# Xbox 360 Profile Data Download Server

OpenPak's Xbox 360 profile data download server (Live service 11, `xedl`).

| | |
| --- | --- |
| Network | Xbox 360 |
| Role | Country information for the account recovery time-zone step (`DownloadCountryInfo`) |
| Depends on | [`x360-common`](https://github.com/openpak/x360-common) (vendored) |
| Image | `ghcr.io/openpak/x360-xedl` |
| Used by | XAM through the security gateway |
| Licence | AGPL-3.0-only |

## What it serves

| Path | XRL | What |
| --- | --- | --- |
| `GET /xedl/ProfileInfo/<id>/CountryInfo.cib` |  | Country info file (US settings for every country) |
| `GET /healthz` | | Health probe |

Identity headers (`X-X360-Account`, `X-X360-Users`) are trusted only with `X360_GATEWAY_KEY`. Split out of
[`x360-xuacs`](https://github.com/openpak/x360-xuacs), one repository per Live service.

## Run

```sh
GOWORK=off go run -mod=vendor ./cmd/x360-xedl
```


## Docs

- [Protocol](docs/protocol.md)
- [Evidence](docs/evidence.md)
- [Deploy](docs/deploy.md)

## Licence

AGPL-3.0-only. See [LICENSE](LICENSE).
