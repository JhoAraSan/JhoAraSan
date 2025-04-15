# 🧰 Post-Format Console Configuration Manual

Guide to restoring and customizing your work environment on Windows with support for WSL, PowerShell, CMD, and Oh-My-Posh. Ideal for developers and enthusiasts who want an efficient and visually appealing setup.

> [Return](README.md)

---

## 📦 Installation Order

### 1. Install Python
- Download from [python.org](https://www.python.org/downloads/)
- Check the "Add Python to PATH" option during installation
- Verify the installation:
  ```bash
  python --version
  ```

### 2. Install Git
- Download from [git-scm.com](https://git-scm.com/)
- During setup:
  - "Use Git from the command line and also from 3rd-party software"
  - "Checkout as-is, commit Unix-style line endings"

- Configure Git:
  ```bash
  git config --global user.name "YourName"
  git config --global user.email "youremail@example.com"
  ```

### 3. Install Anaconda (optional)
- Download from [anaconda.com](https://www.anaconda.com/)
- Create virtual environments using `conda` or use `venv` for a lighter setup

### 4. Install WSL with Kali Linux
```powershell
wsl --install -d kali-linux
```
> Make sure to restart and open Kali at least once to complete the installation.

---

## 💻 Consoles and Customization

### 5. Install PowerShell 7
- Download from [GitHub Releases](https://github.com/PowerShell/PowerShell/releases)
- Verify with:
  ```bash
  pwsh
  ```

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

