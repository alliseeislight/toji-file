# Toji File

A 7-day bodyweight workout tracker styled after the *Toji File* manga poster. Tick off every exercise, follow the progression rules, and log your push-up max. No gym needed.

> Personal fan project. The poster artwork belongs to its original creators.

## Download

Get the latest build from the [Releases page](../../releases/latest).

| Platform | File |
|----------|------|
| Android | `Toji-File-<version>-android.apk` |
| Arch Linux (any Linux) | `Toji-File-<version>-linux-x86_64.AppImage` |

## Install on Android

1. Download the `.apk` from Releases on your phone.
2. Open it and allow installs from your browser or file manager when Android asks.
3. Tap **Install**. Play Protect may warn about an unknown developer because this is a self-built app. Tap **Install anyway**.

## Install on Arch Linux

AppImages need FUSE:

~~~bash
sudo pacman -S --needed fuse2
chmod +x Toji-File-*-linux-x86_64.AppImage
./Toji-File-*-linux-x86_64.AppImage
~~~

Or run it from source with Arch's Electron package:

~~~bash
sudo pacman -S --needed electron
git clone https://github.com/alliseeislight/toji-file.git
cd toji-file/desktop
cp ../www/index.html .
electron .
~~~

## The plan

| Day | Focus |
|-----|-------|
| 1 | Push (strength) |
| 2 | Pull (strength) |
| 3 | Legs (power) |
| 4 | Conditioning and core |
| 5 | Upper body (hypertrophy) |
| 6 | Lower body (hypertrophy) |
| 7 | Rest and recovery |

Everything is bodyweight: push-up variations, table and backpack rows, single-leg squats, sprints. A pull-up bar is the one upgrade worth finding.

## Features

- Seven day tabs, one tickable checklist per day, progress saved on the device
- Overall progress bar
- Warm-up, progression rules and a simple eating guide
- Push-up max log that tracks your best
- Works offline

## Repo layout

| Path | What it is |
|------|-----------|
| `www/index.html` | The whole app (single file) |
| `desktop/` | Electron wrapper for Linux |
| `.github/workflows/build.yml` | Builds the APK and AppImage, publishes releases |

## Build and release

Every push to `main` builds both apps and attaches them to the workflow run. Pushing a version tag also publishes a release:

~~~bash
git tag v1.0.1
git push origin v1.0.1
~~~

To update the app, edit `www/index.html`, commit, push, then tag.
