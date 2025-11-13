# Cheat Sheet — Run this project on macOS, Windows, and Linux

This file contains concise, copy-paste commands to create, activate, verify, deactivate, and delete Python virtual environments on macOS, Linux, and Windows. It assumes your project root is the repository folder that contains `requirements.txt` and the `notebooks/` folder.

**Prerequisites**
- **Python**: Install Python 3.8+ (3.10–3.12 recommended). Verify with: ``python --version`` or ``python3 --version``.
- **Pip/venv**: The `venv` module comes with CPython. If missing, install `python3-venv` (Linux) or use your package manager.

**Common verification commands**
- **Python executable**: ``python -c "import sys; print(sys.executable)"``
- **PIP packages**: ``pip list``
- **Which python** (macOS/Linux): ``which python``
- **Get-Command python** (PowerShell): ``Get-Command python | Select-Object -ExpandProperty Source``

**macOS / Linux (bash, zsh)**
- Create venv:
```bash
python3 -m venv env
```
- Activate:
```bash
# bash / zsh
source env/bin/activate
```
- Upgrade pip and install requirements:
```bash
pip install --upgrade pip
pip install -r requirements.txt
```
- Run Jupyter notebook (project uses `notebooks/workshop.ipynb`):
```bash
jupyter notebook notebooks/workshop.ipynb
```
- Deactivate:
```bash
deactivate
```
- Delete venv:
```bash
rm -rf env
```

**Windows — PowerShell (recommended)**
- (Optional) allow scripts for this session if blocked:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process -Force
```
- Create venv:
```powershell
python -m venv env
```
- Activate:
```powershell
.\env\Scripts\Activate.ps1
```
- Upgrade pip and install requirements:
```powershell
python -m pip install --upgrade pip
pip install -r requirements.txt
```
- Run Jupyter notebook:
```powershell
jupyter notebook notebooks\workshop.ipynb
```
- Deactivate:
```powershell
deactivate
```
- Delete venv:
```powershell
Remove-Item -Recurse -Force .\env
```

**Windows — Command Prompt (cmd.exe)**
- Activate:
```cmd
.\env\Scripts\activate.bat
```
- Delete venv:
```cmd
rmdir /s /q env
```

**Git Bash on Windows**
- Activate (may need adjustment depending on Git Bash shell):
```bash
source env/Scripts/activate
```

**Using an existing venv in this project**
- This repo contains `env/` and/or `Lang_venv/` folders in some setups. To use one that already exists, activate the matching script:
  - PowerShell: ``.\env\Scripts\Activate.ps1`` or ``.\Lang_venv\Scripts\Activate.ps1``
  - Cmd: ``.\env\Scripts\activate.bat``
  - Bash: ``source env/bin/activate``

**VS Code quick setup**
- Open the project folder in VS Code.
- Use the Command Palette (Ctrl+Shift+P) → `Python: Select Interpreter` → pick the interpreter under ``env\Scripts\python.exe`` or ``env/bin/python``.
- Open the integrated terminal and run the activation commands above (VS Code will usually detect and pick the selected interpreter automatically).

**Troubleshooting & tips**
- If `Activate.ps1` fails due to execution policy, run the PowerShell `Set-ExecutionPolicy` line above (it only affects this session).
- If `python` still points to a system interpreter after activation, ensure you activated in the same shell where you run commands and that no other PATH entries override venv's `Scripts` folder.
- Keep virtual environments out of git: add `env/` and similar to `.gitignore`.

**Recreate environment from scratch**
```bash
# remove (if present)
rm -rf env

# create
python -m venv env

# activate (platform-specific—see above)
source env/bin/activate   # or .\env\Scripts\Activate.ps1 on PowerShell

# install
pip install --upgrade pip
pip install -r requirements.txt
```

**Advanced / alternate**
- Use `python -m venv .venv` or `virtualenv` if you prefer hidden venv folder names.
- Consider `pipx` for globally installed CLI tools and `conda` for complex scientific stacks.