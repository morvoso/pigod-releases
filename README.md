# PiGod

PiGod is a Linux desktop app that runs coding CLIs (pi, Claude Code, Copilot CLI and Hermes) in
tabs beside your repositories. This repository holds its builds; the source is not published here.
No GitHub account is needed to download them.

It runs on 64-bit Linux (x86_64) with glibc 2.34 or newer: Ubuntu 22.04, Debian 12, Fedora 35 and
anything newer. Install git and at least one of the CLIs above first.

## Install

Download the newest `PiGod-<version>-x86_64.tar.gz` from the [Releases page](https://github.com/morvoso/pigod-releases/releases),
then unpack it and run the installer inside it:

```sh
tar -xzf PiGod-*-x86_64.tar.gz
PiGod-*-x86_64/install.sh
```

The installer copies PiGod to `~/.local/share/pigod`, links `~/.local/bin/pigod` to it and adds it
to the application menu. It needs no sudo. The downloaded archive and folder can be deleted
afterwards.

To check the download first, put the `.sha256` file from the same release beside it and run
`sha256sum -c PiGod-*-x86_64.tar.gz.sha256`.

## Updates

PiGod checks for new releases and offers them in Settings → Updates.

## Voice

On the first start PiGod offers to download its speech models (about 1.3 GB): a voice for spoken
announcements, speech recognition for dictation, and a small model that words the announcements.
Not now skips it; the models can be downloaded later in Settings → Voice. Everything runs on your
computer.

The small model is run by `llama-server` from llama.cpp. Without `llama-server` on PATH,
announcements use a fixed sentence such as "Your Recipe Box task is finished."

## Uninstall

```sh
rm -rf ~/.local/share/pigod ~/.local/bin/pigod ~/.local/share/applications/pigod.desktop \
  ~/.local/share/icons/hicolor/512x512/apps/pigod.png
```

Settings, history and downloaded models are in `~/.config/pigod-rs`; delete that folder too to
remove everything.
