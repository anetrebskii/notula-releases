# Notula

A documentation editor for teams who write in Markdown and keep it in git.

![Notula with a specification open: the document tree on the left, the document with its properties, and a comment thread anchored to the passage it quotes.](shots/hero.webp)

**[Download the latest release](https://github.com/anetrebskii/notula-releases/releases/latest)** for macOS or Windows. Free, no account, no server.

This repository holds the builds and the release notes. The source lives elsewhere.

## Comments that live in the repository

Select a passage, leave a comment, reply, resolve. Threads are committed next to
the documents as an append-only log with a union merge driver, so they arrive
with a clone and two people commenting at once cannot conflict. The documents
stay clean: no invisible anchors, no block IDs, no HTML comments.

## Only the documentation, none of the code

![The document tree beside a spec, showing folders of specs, docs, runbooks and notes with no source files among them.](shots/tree.webp)

Point it at a repository with thousands of source files and get a clean tree of
Markdown. Folders with no documents in them never appear. Notula asks git for
the file list rather than walking the disk, so a large repository opens as fast
as a small one, and `.gitignore` is respected for free.

## No Markdown syntax. Ever.

![A rollout table and two headings in the editor, with no hashes, asterisks or table pipes anywhere on screen.](shots/editor.webp)

WYSIWYG, not live preview. No hashes, no asterisks, no table pipes, not even on
the line the cursor is on. What lands on disk is ordinary Markdown that your
engineers review in a normal pull request.

## Diagrams draw themselves

![A mermaid flowchart drawn inside the document, from pull request through canary to production.](shots/diagram.webp)

A mermaid block is a picture in the document rather than a wall of arrows and
brackets.

## A one-character edit stays a one-character diff

![A revision shown as a source diff, with one red line and one green line and the rest of the file untouched.](shots/diff.webp)

Notula writes back only what changed. Opening a document and saving it without
editing produces a byte-identical file, and across 6,000 real documents 96.4% of
blocks survive an edit untouched. Every version is there to read and to bring
back.

## You are never the last to know

![Two documents marked in the tree with who changed them, and a bar over the document offering to take the change.](shots/incoming.webp)

Notula fetches in the background and marks every document the rest of the team
has moved on, with who moved it and when. Nothing changes under your cursor
until you take it, and a conflict arrives as a choice between two versions of a
paragraph rather than as conflict markers.

## Download

| Platform | File |
| --- | --- |
| macOS, Apple silicon (M1 and later) | `Notula-macOS-arm64.dmg` |
| macOS, Intel | `Notula-macOS-x64.dmg` |
| Windows, 64-bit | `Notula-Windows-x64.exe` |
| Windows on Arm | `Notula-Windows-arm64.exe` |

The names carry no version, so the same address always serves the newest build.
On macOS, open the disk image and drag Notula into Applications.

### "Notula is damaged and can't be opened"

It is not damaged. Notula is not signed with an Apple Developer ID yet, so macOS
quarantines it on download and refuses to open it. Clear the quarantine flag
once, after moving the app into Applications:

```
xattr -dr com.apple.quarantine /Applications/Notula.app
```

Then open it normally. This is only needed once per install, and it will stop
being needed at all once the app is signed.

### "Windows protected your PC"

The installer is not signed yet either, so SmartScreen stops it the first time.
Choose **More info**, then **Run anyway**. Windows remembers the answer.

## Updates

Notula checks for new versions on launch and every few hours while it is open,
and tells you at the bottom right of the window when one is ready. Nothing is
installed without you pressing Update. You can turn the check off in
Settings - Saving.

## Versions

Stable releases are `vX.Y.Z`. Anything tagged `dev-*` is an untested build from
the tip of the main branch; installed copies of Notula never offer them.
