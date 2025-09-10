# uv-jupyter-register

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
git clone https://github.com/YOURNAME/uv-jupyter-register.git
cd uv-jupyter-register
chmod +x uv-jupyter-register
mkdir -p ~/bin
cp uv-jupyter-register ~/bin/
````

Then make sure `~/bin` is on your `PATH`:

```bash
echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bashrc
# or for zsh
echo 'export PATH="$HOME/bin:$PATH"' >> ~/.zshrc
```

Restart your shell, and you’re ready to go.

---

## Usage

Run the command inside any uv-managed project folder (i.e. containing a `pyproject.toml`, `uv.lock`, or `.venv`):

```bash
uv-jupyter-register
```

Example output:

```
Registering Jupyter kernel:
  Kernel name : uv-myproject
  Display name: Python (uv - myproject)
  Interpreter : /…/python
Proceed? (y/n)
```

### Options

```text
-y            Non-interactive (assume "yes")
-f            Overwrite existing kernel with same name (--force)
-n NAME       Kernel name (default: uv-<folder_name>)
-d DISPLAY    Kernel display name (default: Python (uv - <folder_name>))
-h            Show help
```

### Examples

```bash
# Register with default name
uv-jupyter-register -y

# Register with a custom name
uv-jupyter-register -y -n mykernel -d "My Project (uv)"
```

---

## How it works

* Uses `uv run` to execute the project’s Python interpreter
* Ensures `ipykernel` is installed
* Registers a Jupyter kernel pointing to your uv environment

Once registered, the kernel will appear in the JupyterLab / Notebook / VS Code kernel selector.
