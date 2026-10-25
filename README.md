<div align="center">

<img src="snap/gui/posting.png" alt="Posting logo" width="128" />

# Posting

**An HTTP client for your terminal**

[![posting](https://snapcraft.io/posting/badge.svg)](https://snapcraft.io/posting)
[![Base: core26](https://img.shields.io/badge/Base-core26-2C8C3C?logo=canonical&logoColor=white)](https://snapcraft.io/core26)
![Confinement: strict](https://img.shields.io/badge/Confinement-strict-2C8C3C)
[![Maintainer: sidaliteir](https://img.shields.io/badge/Maintainer-sidaliteir-2C8C3C?logo=snapcraft&logoColor=white)](https://snapcraft.io/publisher/sidaliteir)
![Architectures: amd64 and arm64](https://img.shields.io/badge/Architectures-amd64%20%7C%20arm64-2C8C3C?logo=linux&logoColor=white)

[Getting Started](#getting-started) · [Configure](#configure) · [Limitations](#limitations) · [Build](#build) · [Support](#support) · [License](#license)

Unofficial snap packaging for [Posting](https://github.com/darrenburns/posting), an interactive API client with request collections and environments.

</div>

---

## Getting Started

<a href="https://snapcraft.io/posting"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install posting
mkdir -p ~/my-api
posting --collection ~/my-api
```

## Configure

There are no `snap set` options. Use Posting's own settings and command-line options.

| Setting or file | How to select or locate it |
| --- | --- |
| Request collection | `--collection ~/my-api` |
| Environment file | `--env ~/my-api/dev.env` |
| Settings | `posting locate config` |
| Themes | `posting locate themes` |
| Default collection | `posting locate collection` |

Settings, themes and the default collection use the snap's directories. For `/media` or `/mnt` access:

```bash
sudo snap connect posting:removable-media
```

## Limitations

- Keep collections in a non-hidden home folder or connected removable storage. Hidden files directly under your normal home directory are inaccessible.
- Host editors and pagers are unavailable. Use `EDITOR=vi PAGER=less posting --collection ~/my-api` for the bundled tools.
- Clipboard copying requires terminal support for OSC 52.

## Build

```bash
git clone https://github.com/sidalit/posting-snap.git
cd posting-snap
sudo snap install snapcraft --classic
snapcraft pack
```

## Support

- **Installation or snap issues:** [open a packaging issue](https://github.com/sidalit/posting-snap/issues).
- **Application bugs:** [report them upstream](https://github.com/darrenburns/posting/issues).

## License

Snap packaging: [MIT](https://github.com/sidalit/posting-snap/blob/main/LICENSE).
