
# Install Requirements
---
Kali Linux is blocking `pip install -r requirements.txt` because Python is in an **externally-managed environment** (PEP 668).

You have **3 safe ways** to fix this:

---

### ✅ Option 1: Use Virtual Environment (recommended)

This avoids breaking system Python.

Install venv if missing
```bash
sudo apt install python3-venv -y
```
Create virtual environment
```bash
python3 -m venv venv
```
Activate it
```bash
source venv/bin/activate
```
Install requirements
```bash
pip install -r requirements.txt
```

Later, whenever you want to use the tool:

```bash
source venv/bin/activate
```

---

### ✅ Option 2: Use `--break-system-packages` (quick but riskier)

If you don’t want to use venv and want to force-install globally:

```bash
sudo pip install -r requirements.txt --break-system-packages
```

⚠️ Warning: This can mess with Kali’s system Python, so use only if you know what you’re doing.

---

### ✅ Option 3: Use `pipx` (clean isolation for apps)

If Sublist3r is meant to be used like a tool:

```bash
sudo apt install pipx -y
```
```bash
pipx install -r requirements.txt
```

This way, it keeps things isolated without breaking system packages.

---

