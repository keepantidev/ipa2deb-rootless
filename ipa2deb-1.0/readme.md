# IPA2DEB Rootless

Convert iOS .ipa files to .deb packages for rootless jailbreaks (palera1n, Dopamine, etc).

## Changes from original

- **Removed Python dependency** - uses PlistBuddy or Python3 fallback for plist parsing
- **Removed sudo requirements** - works without root privileges
- **Rootless layout** - `Architecture: iphoneos-arm64`, installs to `/var/jb/Applications`
- **Temp files in `$TMPDIR`** instead of `/var/tmp`

## Important: Store Apps on Rootless

Store applications (App Store apps like Geometry Dash) require code signing and path patching to work on rootless jailbreaks. This converter only changes the format from IPA to DEB with rootless layout.

**For Store apps to work, after installation use:**
- [Xinamine Rootless Patcher](https://onejailbreak.com/blog/xinamine-rootless-patcher-script/)
- Or install AppSync Unified + run `uicache`

The jailbreak bootstrap (Procursus/Dopamine) handles signing automatically for most tweaks, but not for Store apps without patching.

## Usage

### Local conversion

```bash
./ipa2deb-1.0/ipa2deb <ipa file or directory> <output dir> "Name <email>" "https://website.com"
```

### GitHub Actions

1. Upload IPA to the [latest release](https://github.com/keepantidev/ipa2deb-rootless/releases)
2. Go to **Actions** → **Build .deb from IPA**
3. Click **Run workflow**
4. Enter IPA URL from release, maintainer info, website
5. Download .deb from Artifacts

## License

Public domain (Unlicense).
