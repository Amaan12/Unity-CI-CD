# Unity CI/CD On-Demand Appliance

A clean, turnkey GitHub Actions pipeline for Unity game development:
* **Manual button-triggered builds (`workflow_dispatch`)** — 0 minutes burned on normal commits.
* **Auto-incrementing version numbers:** `$GAME_NAME-$VERSION-$PLATFORM-$ARCHITECTURE-$SCRIPTING_BACKEND` (e.g. `TemplateProject-1.0.1-PC-Windows-x64-Mono.zip`).
* **Multi-platform selection:** Interactive checkboxes for Windows, WebGL, Android, macOS, and Linux that compile concurrently in parallel runners.
* **Smart CD Routing:** Choose between direct download (`raw_download`), Itch.io (Butler channel tags), Steam (SteamCMD), or both.
* **Automatic artifact cleanup:** Zips expire after 7 days to preserve storage quota.

---

## Quick Install Into Any Game Repo

Run this single command from the **root directory of your Unity game repository**:

### Option 1: PowerShell (Windows)
```powershell
git clone --depth=1 https://github.com/Amaan12/Unity-CI-CD.git _temp_ci; Copy-Item -Recurse _temp_ci\.github .; Remove-Item -Recurse -Force _temp_ci
```

### Option 2: Bash / Git Bash / macOS / Linux
```bash
git clone --depth=1 https://github.com/Amaan12/Unity-CI-CD.git _temp_ci && cp -r _temp_ci/.github . && rm -rf _temp_ci
```

Once copied:
```bash
git add .github/
git commit -m "ci: add manual on-demand build and deploy workflow"
git push origin main
```

---

## Configuration

See [SECRETS.md](SECRETS.md) for full setup instructions.

* **Required Secrets:** `UNITY_LICENSE`, `UNITY_EMAIL`, `UNITY_PASSWORD`.
* **Optional Secrets for Stores:** `BUTLER_API_KEY` (Itch), `STEAM_USERNAME` + `STEAM_CONFIG_VDF` (Steam).
* **Before Building:** Ensure **Build Addressables on Player Build** is enabled in Unity if your project uses Addressables.
