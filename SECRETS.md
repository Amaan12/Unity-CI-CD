# Secrets & Variables Guide

Configure these in your game repository under:
**Settings** $\rightarrow$ **Secrets and variables** $\rightarrow$ **Actions**

---

## 1. Secrets (Encrypted / Sensitive)

Click **New repository secret**:

| Secret Name | Required? | Description |
| :--- | :---: | :--- |
| `UNITY_LICENSE` | **YES** | The XML content of your Unity `.ulf` license file from `C:\ProgramData\Unity\Unity_lic.ulf`. |
| `UNITY_EMAIL` | **YES** | The email address associated with your Unity account (e.g. your Gmail). |
| `UNITY_PASSWORD` | **YES** | The password for your Unity account (set via [id.unity.com](https://id.unity.com)). |
| `BUTLER_API_KEY` | *Optional (Itch CD)* | Your API key from [itch.io/user/settings/api-keys](https://itch.io/user/settings/api-keys). |
| `STEAM_USERNAME` | *Optional (Steam CD)* | Your Steamworks developer account username. |
| `STEAM_CONFIG_VDF` | *Optional (Steam CD)* | Raw or base64-encoded `config.vdf` containing Steam Guard authorization. |

> [!NOTE]
> **Google Sign-In Accounts:**
> If you normally log in to Unity with Google, your account still has your Gmail address as its Unity ID. You can set a direct password by visiting [id.unity.com](https://id.unity.com) $\rightarrow$ **Security** $\rightarrow$ **Password** (or click "Forgot Password" on your Gmail). This sets a password for CI without affecting your 1-click Google login.

---

## 2. Variables (Non-Sensitive)

Click the **Variables** tab $\rightarrow$ **New repository variable**:

| Variable Name | Required? | Example Value | Description |
| :--- | :---: | :--- | :--- |
| `ITCH_USER` | *Optional (For Itch)* | `my-studio` | Your Itch username or organization name. |
| `ITCH_GAME` | *Optional (For Itch)* | `dungeon-crawler` | The URL slug of your game page on Itch. |
| `STEAM_APP_ID` | *Optional (For Steam)* | `480` | Your Steamworks numeric App ID. |

---

## 3. How to Locate Your `UNITY_LICENSE`

Unity Hub automatically generates and updates your license file locally:
* **Windows:** `C:\ProgramData\Unity\Unity_lic.ulf`
* **macOS:** `/Library/Application Support/Unity/Unity_lic.ulf`
* **Linux:** `~/.local/share/unity3d/Unity/Unity_lic.ulf`

Open the `.ulf` file in Notepad, copy the entire XML text, and paste it into GitHub as secret `UNITY_LICENSE`.
