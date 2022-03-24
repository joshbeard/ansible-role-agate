# Ansible Role for Agate

An Ansible role for managing the installation of the [Agate](https://github.com/mbrubeck/agate)
[Gemini](https://gemini.circumlunar.space/) service.

Visit my Gemini capsule at <gemini://jbeard.co>

## What This Role Does

* Downloads and extracts the Agate release from GitHub.
* Copies the `agate` executable to `/usr/local/bin`.
* Manages the Agate configuration directory.
* Manages an _rsyslog_ and _logrotate_ configuration.
* Manages the service.

## Variables

Refer to [defaults/main.yml](defaults/main.yml).

### agate_hosts

Required list of hostnames to serve.

### agate_version

The version number (_X.Y.Z_) of Agate to download and install.
This should match a release on GitHub.

Default : `3.2.3`

### agate_source

The URL for the Git repository to clone for installation.

Default: "https://github.com/mbrubeck/agate/releases/download/v{{ agate_version }}/agate.x86_64-unknown-linux-gnu.gz"

### agate_dest

The absolute path to install the _agate_ executable to.

Default: `/usr/local/bin/agate`

### agate_data_dir

The absolute path to the root content directory.
A '.certificates' and 'content' sub-directory will be created here.

Default: `/srv/gemini`

### agate_systemd_dir

The absolute path to the systemd configuration directory.

Default: `/etc/systemd/system`

### agate_start_args

Optional startup arguments for Agate.

Default: _none_
