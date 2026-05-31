**1. Install Neovim** (if not already there):
```powershell
winget install Neovim.Neovim
```

**2. Extract the zip and copy files:**
```powershell
# Adjust path to wherever you extracted it
$src = "$env:USERPROFILE\Downloads\nvim-databricks\nvim-databricks\nvim"
$dst = "$env:LOCALAPPDATA\nvim"

mkdir "$dst\lua\core" -Force
mkdir "$dst\lua\plugins" -Force
mkdir "$dst\databricks-web" -Force

Copy-Item "$src\*" "$dst\" -Recurse -Force
Copy-Item "$env:USERPROFILE\Downloads\nvim-databricks\nvim-databricks\databricks-web\*" "$dst\databricks-web\" -Force
```

**3. Open Neovim — plugins auto-install on first launch:**
```powershell
nvim
```

**4. Web UI — just open in browser, no install needed:**
```
C:\Users\<yourname>\AppData\Local\nvim\databricks-web\index.html
```
