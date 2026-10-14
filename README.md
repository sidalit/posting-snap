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
sudo snap install posting                   # or a local build: ./posting_2.11.2_*.snap --dangerous
sudo snap connect posting:removable-media   # optional: /media, /mnt
mkdir -p ~/my-api
posting --collection ~/my-api
```

## Known limitations

### Config and default collection location

Posting keeps its settings and default collection in the snap's own folder, not in `~/.config/posting` or `~/.local/share/posting`:

| What | Path |
|---|---|
| Config file | `~/snap/posting/current/.config/posting/config.yaml` |
| Default collection | `~/snap/posting/current/.local/share/posting/default` |
| Themes | `~/snap/posting/current/.local/share/posting/themes` |

`posting locate config`, `posting locate collection` and `posting locate themes` print these paths. To reuse an existing setup, copy it over:

```bash
mkdir -p ~/snap/posting/current/.config/posting
cp ~/.config/posting/config.yaml ~/snap/posting/current/.config/posting/
```

Keep your collections in a normal (not hidden) folder in your home directory and open them with `--collection`.

### Hidden folders in your home directory

The snap cannot read hidden files or folders directly in your home directory, such as `~/.api-collections`. Posting still opens, but the collection looks empty. Use a normal folder instead.

### External editor and pager

The snap cannot run programs installed on your system, so editors and pagers such as `nano`, `vim` or `code` are not found. Only `vi` (vim.tiny) and `less` from the core26 base work:

```bash
EDITOR=vi PAGER=less posting --collection ~/my-api
```

### Clipboard

Copying uses your terminal's clipboard support (OSC 52). It works in most modern terminals, but not in some (for example macOS Terminal or some terminal multiplexer setups).

## Update to a new upstream release

Change `version` and `source-tag` in `snap/snapcraft.yaml`, then rebuild.

## License

The packaging is MIT-licensed (see `LICENSE`). Posting is Apache-2.0-licensed; its dependencies carry their own licenses.
