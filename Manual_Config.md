# 🧰 Post-Format Console Configuration Manual

Guide to restoring and customizing your work environment on Windows with support for WSL, PowerShell, CMD, and Oh-My-Posh. Ideal for developers and enthusiasts who want an efficient and visually appealing setup.

> [Return](README.md)

---

## 📦 Installation Order

### 1. Install PowerShell 7
- Download from [GitHub Releases](https://github.com/PowerShell/PowerShell/releases) or Use winget
  Search Version
  ```bash
  winget search Microsoft.PowerShell
  ```
  Select version with ID and install
  ```bash
  winget install --id Microsoft.PowerShell.Preview --source winget
  ```
- Verify with:
  ```bash
  pwsh
  ```

  🚫 Hide Windows PowerShell (v5) from Windows Terminal
  1. Open Windows Terminal.
  2. Click the dropdown arrow (˅) next to the tab bar and select Settings.
  3. In Startup > Default Profile, set it to PowerShell 7 (or your preferred shell).
  4. Go to Profiles > Windows PowerShell (this is version 5).
  5. Scroll down and enable Hide profile from dropdown.
  6. Save the changes and close the settings.

### 2. Install Python
- Download from [python.org](https://www.python.org/downloads/)
- Check the "Add Python to PATH" option during installation
- Verify the installation:
  ```bash
  python --version
  ```
  
### 3. Install Git
- Download from [git-scm.com](https://git-scm.com/) or Winget
  ```powershell
  winget install --id Git.Git -e --source winget
  ```
- During setup:
  - "Use Git from the command line and also from 3rd-party software"
  - "Checkout as-is, commit Unix-style line endings"

- Configure Git:
  1. Open Windows Terminal.
  2. Click the dropdown arrow (˅) next to the tab bar and select GitBash.
     
  ```bash
  git config --global user.name "YourName"
  git config --global user.email "youremail@example.com"
  ```
- Verify config:
  ```bash
  git config list
  ``` 

### 4. Install Anaconda (optional)
- Download from [anaconda.com](https://www.anaconda.com/)
- Create virtual environments using `conda` or use `venv` for a lighter setup

  ➕ Add Anaconda PowerShell Prompt to Windows Terminal (Manual Method)
  1. Search for Anaconda PowerShell Prompt in the Windows Start Menu.
  2. Right-click > Open file location.
  3. In the File Explorer window, right-click on the shortcut > Properties.
  4. Go to the Shortcut tab:
     - Copy the content from Target (this is your launch command).
     - Click Change Icon and copy the path of the icon shown there.
  5. Now open Windows Terminal > Settings.
  6. Add a New Profile:
     - Name: Anaconda PowerShell
     - Command line: Paste the value copied from the Target field.
     - Icon: Paste the path from the Change Icon window.
  7. Save the changes and you're done!
> Repeat the same steps for the Anaconda Prompt (CMD version) if desired.

### 5. Install WSL with Kali Linux
```powershell
wsl --install -d kali-linux
```
> Make sure to restart and open Kali at least once to complete the installation.

---

## 💻 Consoles and Customization

### 6. Install Clink (for CMD)
- Download from [chrisant996/clink](https://github.com/chrisant996/clink/releases)
> Enhances CMD experience and allows the use of Oh-My-Posh

### 7. Install Windows Terminal (recommended)
- From Microsoft Store or [GitHub](https://github.com/microsoft/terminal)

---

## 🎨 Visual Customization

### 8. Install FiraCode Nerd Font
- Download from [Nerd Fonts](https://www.nerdfonts.com/font-downloads)
- Apply in terminals: PowerShell, CMD, WSL

### 9. Install Oh-My-Posh
```powershell
winget install JanDeDobbeleer.OhMyPosh -s winget
```

### 10. Use a Custom Theme
- Save your `.omp.json` file (e.g., `craver-style.omp.json`)

#### PowerShell:
```powershell
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\craver-style.omp.json" | Invoke-Expression
```

#### WSL (bash):
```bash
eval "$(oh-my-posh init bash --config ~/.poshthemes/craver-style.omp.json)"
```

#### CMD + Clink
- Place the command in Clink's startup file (e.g., `~/.clink_profile`)

---

## 🔁 Transient Prompt (Clean Previous Prompts)

Add to your `.omp.json`:
```json
"transient_prompt": {
  "enabled": true
}
```

This hides the previous prompt and keeps your terminal clean after each command.

---

## 🎯 Final Recommendations

- Keep this file updated and synced with your GitHub
- Use VSCode's cloud sync feature by signing in
- Store your `.omp.json` theme in a backup repo

---

> Created with ❤️ by [YourName] for developers who love having a clean and productive environment.

