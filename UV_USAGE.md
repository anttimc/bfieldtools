# Using UV Package Manager with bfieldtools

## Quick Start

### Main Development Environment
```bash
uv venv .venv --python 3.11
source .venv/bin/activate
uv pip install -e .
```

### Documentation Environment
```bash
uv venv .venv-docs --python 3.11
source .venv-docs/bin/activate
uv pip install -e ".[docs]"
```

## What Changed

- **pyproject.toml**: Modern Python packaging standard (replaces setup.py)
  - Main dependencies defined in `[project.dependencies]`
  - Documentation dependencies in `[project.optional-dependencies.docs]`
  
- **.python-version**: Specifies Python 3.10 for uv to use automatically

- **Old files preserved**: `requirements.txt`, `requirements_docs.txt`, and `setup.py` remain for backward compatibility but are not needed with uv

## Common Tasks

### Installing new dependencies
Edit `pyproject.toml` under `[project.dependencies]`, then:
```bash
uv pip install -e .
```

### Running tests
```bash
source .venv/bin/activate
python -m pytest tests/
```

### Building documentation
```bash
source .venv-docs/bin/activate
cd docs && make html
```
