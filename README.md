# Chrome PDF Editor — GitHub Actions build

This repository builds the PDF editor extension on GitHub's Ubuntu runner, so Windows users **do not need to run a PowerShell script**.

## One-time setup

1. Download `chrome-pdf-text-editor.zip` from ChatGPT.
2. Open this repository in GitHub and choose **Add file → Upload files**.
3. Upload the ZIP to the **repository root** under the exact name `chrome-pdf-text-editor.zip`, then commit.
4. Navigate to **Actions → Build PDF Editor Chrome Extension → Run workflow** (or use the automatic run triggered by the ZIP commit).
5. Once the run is successful, open it and download the **chrome-pdf-editor-ready** artifact.
6. Extract the downloaded artifact ZIP. Then extract `chrome-pdf-editor-ready.zip` inside it if present.
7. In Chrome, open `chrome://extensions`, enable Developer mode, select **Load unpacked**, and pick the folder containing `manifest.json` (`pdf-editor-extension`).

The workflow runs `setup-dependencies.ps1` on the hosted runner using `pwsh`, checks the vendor scripts, and packages a ready-to-install ZIP. Note that this editor overlays replacement text; it does not securely erase original text from PDFs.
