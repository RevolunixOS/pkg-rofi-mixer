# rofi-mixer

Minimal Rofi menu for selecting the active PulseAudio/PipeWire-compatible audio
sink or source. It delegates device selection to `rofi-pulse-select` and uses
`focus-rofi` to bring the chooser to the foreground under Hyprland.

## Build

```bash
nix build github:RevolunixOS/pkg-rofi-mixer
```

The derivation installs a `rofi-mixer` command and desktop entry.

## Usage

```bash
rofi-mixer
```

Choose `Heardphone` for an output sink or `Microphone` for an input source. The
menu reopens after each selection until it is dismissed.

## Current limitations

> [!WARNING]
> The script calls `rofi-pulse-select`, but the current package wrapper does not
> provide that executable. Install it separately or add it to `package.nix`
> before expecting the menu to work.

- The package fetches `focus-rofi` from a fixed release URL in the legacy
  `RevoluNix` namespace.
- `focus-rofi` assumes Hyprland and requires `hyprctl` on the host.
- The visible `Heardphone` label is misspelled in the current script.
- The flake targets `x86_64-linux` and pins NixOS 24.05.

## License

See [`LICENSE`](LICENSE).
