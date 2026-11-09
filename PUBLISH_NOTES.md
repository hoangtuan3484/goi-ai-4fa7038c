# Publish notes — Gói AI static copy

## Status (2026-11-09 Asia/Bangkok)
- Static site READY at `/workspace/goi-ai-4fa7038c/`
- Files: `index.html`, `manifest.json`, `apple-touch-icon.png` (180×180), `.nojekyll`
- Canvas source of truth: `canvas_id` `22bfbcf2-5c53-4994-80bb-5ea826e615ab`
- Intended GitHub account: `hoangtuan3484`
- Intended repo name: `goi-ai-4fa7038c` (public, hard to guess)
- Intended live URL: `https://hoangtuan3484.github.io/goi-ai-4fa7038c/`
- **Not published yet**: box `gh` not logged in; Cursor GitHub tools have no create-repo / push-files; CloudAgent unavailable to this executor.

## How to publish (once `gh` is authenticated as hoangtuan3484)
```bash
cd /workspace/goi-ai-4fa7038c
gh auth login   # device flow if needed
gh repo create goi-ai-4fa7038c --public --source=. --remote=origin --push --description "Standalone Gói AI tracker (iOS home screen)"
gh api repos/hoangtuan3484/goi-ai-4fa7038c/pages -X POST -f source[branch]=main -f source[path]=/
# wait for https://hoangtuan3484.github.io/goi-ai-4fa7038c/ to return 200
```

## Updating after Page changes
1. ReadCanvas canvas_id `22bfbcf2-5c53-4994-80bb-5ea826e615ab`
2. Regenerate `index.html` (same data + design)
3. `git -C /workspace/goi-ai-4fa7038c add -A && git commit -m "sync from canvas" && git push`
4. Do not put API keys in the repo. Card: last 4 only.


## IMPORTANT (9/11 17:55)
Content now lives in `app.html`. `index.html` is a tiny loader that fetches app.html with no-store to beat iPhone caching. Edit app.html only; never overwrite index.html with content.
