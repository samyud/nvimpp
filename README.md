# Installation
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

# How to use Web UI Notebook Editor 
Open this path in Chrome or Edge:

```
C:\Users\<your-username>\AppData\Local\nvim\databricks-web\index.html
```

Just copy and paste that directly into the browser address bar and hit Enter.

**Once it opens:**

**1. Connect to Databricks:**
- Click the **"Not Connected"** badge in the top right
- Enter your workspace URL: `https://adb-xxxx.azuredatabricks.net`
- Enter your Personal Access Token
- Click **Fetch Clusters** to load your clusters
- Select your cluster and click **Connect**

**2. Edit notebook cells:**
- Each box is a cell — click inside to edit
- Change language with the dropdown (Python, SQL, MD, Scala, Shell)
- The `%python`, `%sql` etc. magic commands show automatically

**3. Run code:**
- **Ctrl+Enter** — run current cell
- **Shift+Enter** — run all cells
- Or click the **▶ Run** button on any cell

**4. Add cells:**
- Click **+ Add cell** between any two cells
- Or use the toolbar buttons: **+ Python**, **+ SQL**, **+ MD**

**5. Export:**
- Click **Export** in the toolbar to download as a `.py` file in Databricks native format
- Click **Upload** to push directly to your Databricks workspace

Even if there is no Databricks Connection, it still works — it simulates execution locally so you can edit and export notebooks offline.
