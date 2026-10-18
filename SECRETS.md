# Secrets & Variables Guide

Configure these in your game repository under:
**Settings** $\rightarrow$ **Secrets and variables** $\rightarrow$ **Actions**

---

## 1. Secrets (Encrypted / Sensitive)

Click **New repository secret**:

| Secret Name | Required? | Description |
| :--- | :---: | :--- |
| `UNITY_LICENSE` | **YES (Required for CI)** | The XML content of your Unity `.ulf` license file from `C:\ProgramData\Unity\Unity_lic.ulf`. |
| `BUTLER_API_KEY` | *Optional (Only for Itch CD)* | Your API key from [itch.io/user/settings/api-keys](https://itch.io/user/settings/api-keys). |
| `STEAM_USERNAME` | *Optional (Only for Steam CD)* | Your Steamworks developer account username. |
| `STEAM_CONFIG_VDF` | *Optional (Only for Steam CD)* | Raw or base64-encoded `config.vdf` containing Steam Guard authorization. |

> [!NOTE]
> **No Unity Account Email or Password Needed!**
> Because you use your locally activated `Unity_lic.ulf` file, Unity operates in offline manual license mode. No email or password secrets are needed.

---

## 2. Variables (Non-Sensitive)

Click the **Variables** tab $\rightarrow$ **New repository variable**:

| Variable Name | Required? | Example Value | Description |
| :--- | :---: | :--- | :--- |
| `ITCH_USER` | *Optional (For Itch)* | `my-studio` | Your Itch username or organization name. |
| `ITCH_GAME` | *Optional (For Itch)* | `dungeon-crawler` | The URL slug of your game page on Itch. |
| `STEAM_APP_ID` | *Optional (For Steam)* | `480` | Your Steamworks numeric App ID. |

---

## How to Get Your `UNITY_LICENSE` (2 Minutes)

1. In your repo, go to **Actions** $\rightarrow$ **Get Unity License Activation File** $\rightarrow$ **Run workflow**.
2. When finished, download the `Unity-Activation-File.zip` artifact and extract the `.alf` file.
3. Open [license.unity3d.com](https://license.unity3d.com) in your browser.
4. Upload the `.alf` file, select **Personal Edition** (or enter Pro serial), and download the resulting `.ulf` file.
5. Open the `.ulf` file with Notepad, copy the entire XML text, and paste it into GitHub as secret `UNITY_LICENSE`.
