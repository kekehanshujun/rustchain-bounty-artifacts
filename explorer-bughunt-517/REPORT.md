# RustChain Block Explorer Bug Hunt (#517)

Browser/OS: Google Chrome 148.0.7778.168, Windows NT 10.0.26200.0
Viewport: 1365x900
Date: 2026-05-17 Asia/Shanghai

## Pages Visited

1. https://rustchain.org/explorer/
2. https://rustchain.org/anchors
3. https://rustchain.org/preserved.html
4. https://rustchain.org/manifesto.html

## Bugs / Issues

### 1. Explorer links to `/anchors`, but `/anchors` returns 404

Steps to reproduce:
1. Open https://rustchain.org/explorer/
2. Inspect/click the Anchors navigation link. The explorer HTML contains two `href="/anchors"` links.
3. Navigate to https://rustchain.org/anchors

Actual: 404 Not Found.
Expected: the Anchors page should load, or the explorer should link to the correct deployed path.
Impact: broken navigation from the explorer UI.

## Notes

- The explorer home page itself loaded successfully.
- `preserved.html` and `manifesto.html` loaded successfully as linked RustChain site pages.
- Direct IP explorer URL `https://50.28.86.131/explorer` fails in PowerShell due certificate trust, while the domain URL works. This is expected if the certificate is only trusted for the domain, but it is worth avoiding direct-IP links in user-facing docs.
