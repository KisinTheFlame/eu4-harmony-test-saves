# eu4-harmony-test-saves

Clean, compressed, full-DLC **Europa Universalis IV v1.37.5.0 Inca** (vanilla checksum `491d`, zero mods) save files distributed for automated test scenarios in [`eu4-harmony`](https://github.com/KisinTheFlame/eu4-harmony).

## Specification

- **Game version**: EU4 `v1.37.5.0 Inca`
- **Checksum**: `491d` (unmodified base game, zero mods enabled)
- **DLCs**: All 31 expansions / content packs enabled cleanly through Steam
- **Format**: Compressed `.eu4` ZIP archives (`PK\x03\x04`; `EU4txt` metadata for regular/observer saves, `EU4bin` for the 1444 Ironman save)

## Usage

From an `eu4-harmony` checkout:

```powershell
cargo xtask saves fetch
cargo xtask saves verify
```

`cargo xtask saves fetch` downloads the release assets defined in `xtask/saves.toml`, verifies every SHA-256 digest, and saves them under `%LOCALAPPDATA%\eu4-harmony-dev\saves\` (or `$EU4_HARMONY_DEV_DIR\saves\`).

To regenerate saves locally from scratch on a clean claim, run `cargo xtask saves generate --short --owner <name>` or `cargo xtask saves generate --late --owner <name>`.

## Assets (`v1`)

| Release Asset | Local Filename | Kind | Notes |
| --- | --- | --- | --- |
| `test-regular-1444.eu4` | `test-regular-1444.eu4` | `short` | `1444.11.11`, `ENG`, uncompressed-text inside ZIP |
| `test-utf8-1444.eu4` | `test-中文-1444.eu4` | `short` | `1444.11.11`, `FRA`, stored locally with UTF-8 CJK filename |
| `test-ironman-1444.eu4` | `test-ironman-1444.eu4` | `short` | `1444.11.11`, `CAS`, local Ironman (`EU4bin`) |
| `observer-1600.1.1.eu4` | `observer-1600.1.1.eu4` | `late` | `1600.1.1`, observer (`O00`) |
| `observer-1700.1.1.eu4` | `observer-1700.1.1.eu4` | `late` | `1700.1.1`, observer (`O00`) |
| `observer-1760.7.1.eu4` | `observer-1760.7.1.eu4` | `late` | `1760.7.1`, observer (`O00`) |
| `observer-1780.7.1.eu4` | `observer-1780.7.1.eu4` | `late` | `1780.7.1`, observer (`O00`) |
| `observer-1800.7.1.eu4` | `observer-1800.7.1.eu4` | `late` | `1800.7.1`, observer (`O00`) |
| `observer-1820.7.1.eu4` | `observer-1820.7.1.eu4` | `late` | `1820.7.1`, observer (`O00`) |
