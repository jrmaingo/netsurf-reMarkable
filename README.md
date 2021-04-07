# NetSurf-reMarkable [![Build for reMarkable](https://github.com/alex0809/netsurf-reMarkable/actions/workflows/build.yml/badge.svg)](https://github.com/alex0809/netsurf-reMarkable/actions/workflows/build.yml)

This repository contains a script that builds NetSurf for the reMarkable.
The source code is cloned during the build, using fixed versions defined in [versions.sh](scripts/versions.sh). 
To support drawing on the reMarkable, [a fork of libnsfb](https://github.com/alex0809/libnsfb-reMarkable) is used.

## Current status

- [X] Build pipeline
- [X] Screen refresh
- [X] Touch support
- [X] Pen support
- [X] Hardware-button support
- [X] Virtual keyboard (is already built-in)

## Installation

1. Copy required resources to the device. These are provided with every release (contents of the `resources` folder) and can be copied to any of these locations:
    - `/usr/share/netsurf/`
    - `$NETSURFRES/`
    - `~/.netsurf/`
2. Add required "Choices" file to the device. See [Configuration section](#configuration) for details. This file can be located at any of these locations:
    - `$NETSURFRES/Choices`
    - `~/.netsurf/`
3. Copy the `nsfb` binary to `/opt/bin/` on the the device.
4. Optionally copy `netsurf.draft` to `/opt/etc/draft/` for launcher support.


## Configuration

To configure netsurf, you can use a "Choices" file.
See [here](https://ci.netsurf-browser.org/jenkins/job/docs-netsurf/doxygen/md_docs_netsurf-options.html) for configuration options.

The configuration options are stores as key:value pairs.

At minimum, you will have to configure the font files. See [here](example/Choices) for an example configuration
with some sensible default values and preconfigured fonts that should be available on every reMarkable.

## Building locally

```
docker-compose up
```
