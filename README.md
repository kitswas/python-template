# python-template

A template for Python projects.  
Includes basic project structure, a test suite, a code formatter and linter, and a dependency manager.

## How to use

You need the UV package/project manager to install the dependencies.  
You can get it from [here](https://docs.astral.sh/uv/getting-started/installation/).

Set up the environment. (Only once)

```bash
uv venv
.venv/Scripts/activate
uv sync --link-mode=symlink # Install the dependencies
```

If you want Pytorch (with or without CUDA), you can install it using the `--extra` flag.

```bash
uv sync --link-mode=symlink --extra=torch-cpu   # for CPU only
uv sync --link-mode=symlink --extra=torch-cu124 # for CUDA support
```

You can add other dependencies use `uv add`.

```bash
uv add numpy # Similar to pip install numpy
```

To run any script, append `uv run` before the `python` command. (If the environment is inactive)

```bash
uv run python src/hello.py
```

Run tests:

```bash
uv run python -m unittest discover
```

## Code Formatting and Linting

We have [ruff](https://docs.astral.sh/ruff/) for code formatting and linting.
Install the [VSCode extension](https://marketplace.visualstudio.com/items?itemName=charliermarsh.ruff)
and enable `Format on Save` for a better experience.

To sort imports:

```bash
uv run ruff check --select I src --fix
```

To check for linting errors:

```bash
uv run ruff check --select ALL src # Use --fix to fix the errors
```

To format the code:

```bash
uv run ruff format src
```
