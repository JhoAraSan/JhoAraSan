# 🧰 Manual de Configuración de Consolas Post-Formateo
[Volver](README:MD)
Guía para restaurar y personalizar tu entorno de trabajo en Windows con soporte para WSL, PowerShell, CMD y Oh-My-Posh. Ideal para desarrolladores y entusiastas que desean un setup eficiente y visualmente atractivo.

---

## 📦 Orden de Instalación

### 1. Instalar Python
- Descarga desde [python.org](https://www.python.org/downloads/)
- Marcar "Add Python to PATH" durante la instalación
- Verifica la instalación:
  ```bash
  python --version
  ```

### 2. Instalar Git
- Descargar desde [git-scm.com](https://git-scm.com/)
- Durante el asistente:
  - "Use Git from the command line and also from 3rd-party software"
  - "Checkout as-is, commit Unix-style line endings"

- Configurar Git:
  ```bash
  git config --global user.name "TuNombre"
  git config --global user.email "tucorreo@example.com"
  ```

### 3. Instalar Anaconda (opcional)
- Descargar desde [anaconda.com](https://www.anaconda.com/)
- Crear entornos virtuales con `conda` o usar `venv` si prefieres mayor ligereza

### 4. Instalar WSL con Kali Linux
```powershell
wsl --install -d kali-linux
```
> Asegúrate de reiniciar y abrir Kali al menos una vez para completar la instalación.

---

## 💻 Consolas y Personalización

### 5. Instalar PowerShell 7
- Descargar desde [GitHub Releases](https://github.com/PowerShell/PowerShell/releases)
- Verificar con:
  ```bash
  pwsh
  ```

### 6. Instalar Clink (para CMD)
- Descargar desde [chrisant996/clink](https://github.com/chrisant996/clink/releases)
> Mejora la experiencia del CMD y permite usar Oh-My-Posh

### 7. Instalar Windows Terminal (recomendado)
- Desde Microsoft Store o [GitHub](https://github.com/microsoft/terminal)

---

## 🎨 Personalización Visual

### 8. Instalar FiraCode Nerd Font
- Descargar desde [Nerd Fonts](https://www.nerdfonts.com/font-downloads)
- Aplicar en las terminales: PowerShell, CMD, WSL

### 9. Instalar Oh-My-Posh
```powershell
winget install JanDeDobbeleer.OhMyPosh -s winget
```

### 10. Usar Tema Personalizado
- Guardar tu archivo `.omp.json` (ej: `craver-style.omp.json`)

#### PowerShell:
```powershell
oh-my-posh init pwsh --config "$env:POSH_THEMES_PATH\craver-style.omp.json" | Invoke-Expression
```

#### WSL (bash):
```bash
eval "$(oh-my-posh init bash --config ~/.poshthemes/craver-style.omp.json)"
```

#### CMD + Clink
- Colocar el comando en el archivo de inicio de Clink (ej: `~/.clink_profile`)

---

## 🔁 Transient Prompt (Limpieza Automática del Prompt)

Agrega al `.omp.json`:
```json
"transient_prompt": {
  "enabled": true
}
```

Esto oculta el prompt anterior y mantiene el terminal limpio después de ejecutar comandos.

---

## 🎯 Recomendaciones Finales

- Mantén este archivo actualizado y sincronizado con tu GitHub
- Puedes exportar tus configuraciones VSCode en la nube iniciando sesión
- Almacena tu tema `.omp.json` en un repo de respaldo

---

> Creado con ❤️ por [TuNombre] para desarrolladores que aman tener su entorno impecable.

