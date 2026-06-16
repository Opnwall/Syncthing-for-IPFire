# Syncthing for IPFire

This plugin installs Syncthing on IPFire with:

- an init script at `/etc/rc.d/init.d/syncthing`
- a Web UI page at `/srv/web/ipfire/cgi-bin/syncthing.cgi`
- a menu entry at `/var/ipfire/menu.d/84-syncthing.menu`
- settings under `/var/ipfire/syncthing`
- Syncthing data/config under `/var/lib/syncthing`

## Install

Run as root from this directory:

```sh
sh install.sh
```

The installer uses `src/usr/local/bin/syncthing` when it exists and is
executable. If no local binary is present, it downloads the latest Syncthing
Linux release for the detected architecture from GitHub.

To force an architecture:

```sh
SYNCTHING_ARCH=amd64 sh install.sh
```

Supported architecture values are `amd64`, `arm64`, `arm-v7`, `arm`, and `386`.

## Uninstall

```sh
sh uninstall.sh
```

The uninstall script maps files from the `src/` mirror back to their real IPFire
paths and removes runtime state under `/var/ipfire/syncthing` and
`/var/lib/syncthing`.
