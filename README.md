# portfolio-assets

Master copies of the video and image assets used across
[sayrakurtoglu.com](https://www.sayrakurtoglu.com/).

This repo is an **archive**, not a CDN. Files here are the full-quality originals.
Anything the live site serves is published separately — see [Delivery](#delivery).

## Contents

| File | Project | Spec |
| --- | --- | --- |
| `media/iphone-duo-nikeskims-final.mp4` | iPhone Duo — NikeSKIMS | 26.6 s · 2428×1440 · H.264 · 12.7 Mbps · 40.1 MiB |

## Naming

Lowercase ASCII, words joined by hyphens, no spaces:

```
media/<project>-<subject>-<variant>.mp4

media/iphone-duo-nikeskims-final.mp4
media/aether-mfg-quote-to-delivery.mp4
media/contextos-spatial-capture.mp4
```

Spaces and non-ASCII characters have to be percent-escaped in every URL and
Markdown link, which is how `Apple%20iPhone%20Duo-%20NikeSKIMS-%20final.mp4`
happens. Hyphenated names stay readable everywhere.

## Rules

**Commit final cuts only.** Git keeps every version of every file forever, and
video does not delta-compress. A 40 MB file replaced once costs 80 MB of history
permanently — deleting the old file does not reclaim it. Keep iterations local.

**Keep each file under 50 MB.** GitHub warns above 50 MB and refuses anything
over 100 MB.

**Watch the total.** Roughly 1 GB is where GitHub starts to push back. At the
current file size that is about 20 finished videos.

No Git LFS for now. It adds a required client, a quota to manage, and a
1 GB/month bandwidth cap that a single hotlinked video would exhaust. Revisit
with `git lfs migrate import` if the repo approaches ~500 MB.

## Delivery

Do not link the site to `raw.githubusercontent.com`. It is not a CDN, GitHub's
terms exclude that use, and it is rate-limited with no guarantee of byte-range
seeking — so video scrubbing and mobile playback are unreliable.

Publish delivery copies to a real host instead, and keep this repo as the
source of truth for the master files.
