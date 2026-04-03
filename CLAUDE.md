# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

MLE study repository — a personal scratchpad for implementing math, linear algebra, classical ML, deep learning, and MLE topics from scratch. Content lives in numbered topic directories (`01_*/`, `02_*/`, etc.) containing Jupyter notebooks and occasional `.py` scripts. Notebooks are the primary artifact — they combine implementation, experimentation, and notes.

## Development Setup

- **Package manager**: [uv](https://docs.astral.sh/uv/)
- **Python version**: 3.14 (managed via `.python-version`)
- **Virtual environment**: `.venv/` (managed by uv)

## Common Commands

```bash
uv sync                  # Install/sync dependencies
uv run jupyter notebook  # Launch Jupyter for notebooks
uv add <package>         # Add a new dependency
```

## Linting

```bash
uv run ruff check .        # Lint (E/F/I rules)
uv run ruff check --fix .  # Lint and auto-fix
uv run ruff format .       # Format
```

Ruff is configured to lint `.ipynb` files as well. nbstripout is installed as a git filter to strip notebook outputs on commit. CI (`.github/workflows/lint.yml`) runs ruff and checks for unstripped notebook outputs on push/PR to main.

## Conventions

- Topic directories are numbered and ordered by learning progression (e.g., `01_math_foundations/`, `02_classical_ml/`).
- Notebooks focus on from-scratch implementations and hands-on experimentation rather than using high-level library APIs.
- Dependencies are added incrementally as new topics require them.
