# Productivity Booster

A legacy Electron desktop widget implemented with HTML, CSS, and browser JavaScript.

## Windows 11 PowerShell: exact start commands

This project uses **Node.js and Electron**, not Python. Install Git and Node.js 22 LTS first. Then open PowerShell and run each command **separately**:

```powershell
git clone https://github.com/Tyler-Keesee/Productivity-Booster.git
```
```powershell
Set-Location .\Productivity-Booster
```
```powershell
node --version
```
```powershell
npm --version
```
```powershell
npm ci
```
```powershell
npm start
```

A desktop window should load the local `index.html` file. Close the window to stop the app. For a browser-only preview that does **not** exercise Electron, run `python -m http.server 8000` and open http://localhost:8000/.

**Why the old clone failed:** `package.json` pointed at `main-electron.js` but that file was absent. The secure Electron entry file is now included. The project still depends on the older Electron 25 series and requires compatibility/security upgrades before any production use.

**Verification:** CI checks the Electron entry and JavaScript syntax, but Electron window rendering and individual widgets still need manual tests on Windows. No `venv` or `pip` setup is required.

## Troubleshooting

- If `npm ci` fails, check Node/npm versions and network access; do not delete the lockfile as a workaround.
- If Windows flags the Electron app, do not bypass security prompts blindly.
- If the UI has missing features or JavaScript errors, open DevTools and inspect Console. These are application-level issues, not Python environment problems.

