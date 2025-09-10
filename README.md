# uv-jupyter-kernel

Register your [uv](https://github.com/astral-sh/uv) project environments as Jupyter kernels with a single command.  
This makes your project’s environment available in JupyterLab, Jupyter Notebook, or VS Code without extra setup.

---

## Features

- 🪄 Automatically detects the project name and creates a kernel with a clear display name  
- 📦 Ensures `ipykernel` (and optionally Jupyter) is installed in the environment  
- ⚡ Non-interactive mode (`-y`) and forced overwrite (`-f`)  
- 🧩 Works with any uv-managed Python project  

---

## Installation

Clone the repo and put the script somewhere on your `$PATH` (e.g. `~/bin`):

```bash
git clone https://github.com/YOURNAME/uv-jupyter-kernel.git
cd uv-jupyter-kernel
chmod +x uv-jupyter-kernel
mkdir -p ~/bin
cp uv-jupyter-kernel ~/bin/
