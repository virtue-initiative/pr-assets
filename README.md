# pr-assets

Images referenced from pull requests in
[virtue-initiative/virtue-initiative](https://github.com/virtue-initiative/virtue-initiative).

## Why this repo exists

GitHub's own uploader — the one that gives you a `user-attachments` link when you
drag a file into a comment box — only works from a signed-in browser session.
There's no API for it, so anything scripted (or written by an agent) can't put a
screenshot in a PR that way.

The workaround is to host the image in a repo and link it. That's all this is.

It has to be **public**: GitHub proxies images through its own cache, and the
proxy can't authenticate to a private repo, so a `raw.githubusercontent.com`
link from a private repo renders as a broken image.

## Layout

One directory per pull request:

```
pr/<pr-number>/<descriptive-name>.png
```

Reference it from the PR body with the raw URL:

```markdown
![Status dialog on Windows](https://raw.githubusercontent.com/virtue-initiative/pr-assets/main/pr/623/windows-status-dialog.png)
```

Keep the names descriptive rather than sequential (`windows-status-dialog.png`,
not `screenshot-3.png`) — they're the alt text and the only index anyone gets.

## Housekeeping

Nothing here is built, deployed, or referenced by any code. Deleting a
directory only breaks the images in the PR that pointed at it, so it's safe to
prune once a PR is merged and its screenshots stop being interesting — though
they're small, and leaving them keeps merged PRs readable.

## Contents

- `pr/623/` — consistent status pages on Linux, Windows and Android (#622).
- `pr/624/` — consistent status screens on macOS and iOS (#622).
- `pr/645/` — client usability fixes on Mac and iOS (#630, #631, #633, #634).
