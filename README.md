# Integrity Monitor — Website

Static informational page: what the apps do, how they work, and download links for Windows and Android.
Plain HTML/CSS, no build step, no server required.

## Privacy note (important — read before hosting)

You asked for this to stay private for now, just for you and people you share the
link with directly. Here's honestly what that means with a free GitHub Pages setup:

- The page **will not** show up in Google or any search engine (`robots.txt` and a
  `noindex` meta tag both block that).
- The page **will not** be linked from anywhere else, so nobody stumbles onto it.
- **However**, on GitHub's free plan, Pages requires the source repo to be public.
  That means someone who specifically visits your GitHub profile and browses your
  repositories could find this one and guess the URL. This is "unlisted," not
  true password-protected privacy.

If you ever need *real* access control (a login wall before anyone sees anything),
that requires a different host — ask, and I can walk you through a free option
(Cloudflare Pages + Cloudflare Access) that actually gates access behind a login.
For now, this setup matches what you described: not discoverable, shareable by link.

## Setting this up on GitHub Pages

1. Create a new GitHub repo (e.g. `fims-website`) — keep the name low-key rather
   than something obviously tied to the project, for a little extra obscurity.
2. Push these files to `main`:
   ```
   cd fims-website
   git init
   git add .
   git commit -m "Initial website"
   git branch -M main
   git remote add origin https://github.com/timothymartinluther1-gif/fims-website.git
   git push -u origin main
   ```
3. Repo → **Settings → Pages** → Source: **Deploy from a branch** → Branch: **main**,
   folder **/ (root)** → **Save**.
4. Wait ~1 minute, refresh that page — your live URL will be shown, something like
   `https://timothymartinluther1-gif.github.io/fims-website/`.
5. Share that exact URL directly with whoever needs it. Don't post it anywhere public.

## Keeping the download link working

The download button points to:
```
https://github.com/timothymartinluther1-gif/fims-desktop/releases/download/latest/IntegrityMonitor.exe
```
This already updates automatically on every push to `fims-desktop`, thanks to the
release-publishing step already set up in that repo's GitHub Actions workflow —
nothing extra needed here.

## Keeping the Android download link working

The Android button points to:
```
https://github.com/timothymartinluther1-gif/fims-app/releases/download/android-latest/app-debug.apk
```
That release is refreshed by the fims-app GitHub Actions build on every push, so the link
always gives the newest APK.

## Editing content later

Plain HTML/CSS, edit directly and push. GitHub Pages redeploys automatically within
a minute or two of any push to `main`.
