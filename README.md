# hello-world-extension
This is a Firefox extension that just shows hello, World

## Publishing signed XPI via GitHub Pages

Steps to publish your signed `.xpi` so Firefox can auto-update from `updates.json`:

1. Sign your extension using `web-ext sign` (see below). The signed file will be saved in `./signed`.
2. Run the helper script to copy the signed `.xpi` to the repository root and push it:

```bash
./publish.sh
```

3. Enable GitHub Pages on the repository (Settings → Pages). Serve from the `main` branch.
4. After Pages is active, your signed XPI will be available at:

```
https://<your-github-username>.github.io/hello-world-extension/hello-world-1.0.1.xpi
```

5. Ensure `manifest.json` contains the `browser_specific_settings.gecko.update_url` pointing to `updates.json` (already set in this repo). Firefox will read `updates.json` to find the XPI for updates.

Notes:
- Replace `<your-github-username>` with your GitHub username (chank-op in your repo URL).
- If you bump the version, run signing again and update `updates.json` accordingly.

