# Posting snap

[![posting](https://snapcraft.io/posting/badge.svg)](https://snapcraft.io/posting)

Snap packaging for [Posting](https://github.com/darrenburns/posting), an interactive terminal HTTP/API client with request collections and environments.

Unofficial build, not affiliated with or endorsed by the Posting project.

## Build

```bash
snapcraft pack
```

## Install and try

<a href="https://snapcraft.io/posting"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install posting
sudo snap connect posting:removable-media   # optional: /media, /mnt
mkdir -p ~/my-api
posting --collection ~/my-api
```

## Known limitations

- Collections must be in a non-hidden home folder or connected removable storage. Hidden files directly under your home directory are inaccessible.
- Settings, themes and the default collection use the snap's own directories. Use `posting locate config`, `posting locate themes` or `posting locate collection` to find them.
- Host editors and pagers are unavailable. Use the base's tools with `EDITOR=vi PAGER=less posting --collection ~/my-api`.
- Clipboard copying requires terminal support for OSC 52.

## Update to a new upstream release

Change `source-tag` in `snap/snapcraft.yaml`, then rebuild. The version is taken from the upstream project metadata.

## Automation

Builds, publishing, and dependency updates use [snap-automation](https://github.com/sidalit/snap-automation).

## License

The packaging is MIT-licensed (see `LICENSE`). Posting is Apache-2.0-licensed; its dependencies carry their own licenses.
