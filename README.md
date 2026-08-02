# Notula

A documentation editor for teams who write in Markdown and keep it in git.

**[Download the latest release](https://github.com/anetrebskii/notula-releases/releases/latest)**

This repository holds the builds and the release notes. The source lives elsewhere.

## macOS

Pick the download that matches your Mac:

| Mac | File |
| --- | --- |
| Apple silicon (M1 and later) | `Notula-<version>-arm64.dmg` |
| Intel | `Notula-<version>.dmg` |

Open the disk image and drag Notula into Applications.

### "Notula is damaged and can't be opened"

It is not damaged. Notula is not signed with an Apple Developer ID yet, so macOS
quarantines it on download and refuses to open it. Clear the quarantine flag
once, after moving the app into Applications:

```
xattr -dr com.apple.quarantine /Applications/Notula.app
```

Then open it normally. This is only needed once per install, and it will stop
being needed at all once the app is signed.

## Updates

Notula checks for new versions on launch and every few hours while it is open,
and tells you at the bottom right of the window when one is ready. Nothing is
installed without you pressing Update. You can turn the check off in
Settings - Saving.

## Versions

Stable releases are `vX.Y.Z`. Anything tagged `dev-*` is an untested build from
the tip of the main branch; installed copies of Notula never offer them.
