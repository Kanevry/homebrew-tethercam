# homebrew-tethercam

Homebrew tap for [TetherCam](https://tethercam.app), the iPhone-over-USB camera
plugin for OBS ([main repo](https://github.com/Kanevry/tethercam)).

## Install

```sh
brew tap kanevry/tethercam
brew install --cask tethercam-obs
```

This copies the signed, notarized `obs-iphone-usb-cam.plugin` bundle straight into
`~/Library/Application Support/obs-studio/plugins/`, the same place
`scripts/install.sh` in the main repo puts it by hand. No admin rights needed; nothing
is installed outside your own home directory. Restart OBS afterwards, then use
Tools -> "TetherCam: Add iPhone camera to current scene".

## Uninstall

```sh
brew uninstall --cask tethercam-obs
```

## Updating the cask

The cask tracks the signed `TetherCam-obs-plugin.zip` release asset from the main
repo. On every new plugin release, bump `version` and `sha256` in
`Casks/tethercam-obs.rb` by hand:

```sh
curl -sL https://github.com/Kanevry/tethercam/releases/download/vX.Y.Z/TetherCam-obs-plugin.zip -o /tmp/tc.zip
shasum -a 256 /tmp/tc.zip
```

## License

MIT, see `LICENSE`.
