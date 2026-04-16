# Copilot instructions for this repository

Purpose
- Provide Copilot sessions concise, repo-specific guidance so suggestions are accurate and safe.

Build / test / lint commands (detected)
- No build, test, or lint scripts detected in repo root (no requirements.txt, pyproject.toml, setup.py, or tests directory present).
- Primary artifact: `ml_final_project.ipynb` (Jupyter notebook).

How to run the project
- Open the notebook with Jupyter: `jupyter notebook ml_final_project.ipynb` or `jupyter lab` and open the file.
- If a user adds dependencies, typical commands to install would be:
  - `python -m venv .venv && source .venv/bin/activate` (macOS/Linux)
  - `pip install -r requirements.txt` (if a requirements file is later added)
- No automated test runner detected. When tests are added, run a single test using pytest: `pytest -k "pattern"` or `pytest path/to/test_file.py::test_name`.

High-level architecture
- Notebook-first ML project. All data exploration, preprocessing, modeling, and evaluation live inside `ml_final_project.ipynb`.
- No packaged Python module or CLI. Typical workflow is iterative notebook edits and outputs (figures, pickled models).
- Data files are not checked into the repo (no data/ folder detected). Expect external data sources or user-local data files.

Key conventions & important repo files
- Jupyter notebooks are the source of truth; changes to analysis should be made in the notebook.
- .gitignore includes standard Python ignores plus Jupyter checkpoint exclusion (`.ipynb_checkpoints`) — avoid committing large virtualenvs, .env, or generated artifacts.
- AI assistant config found: `.claude/settings.local.json` with these allowed Bash actions:
  - "Bash(git add:*)", "Bash(git commit -m ':*)", "Bash(git push:*)", "Bash(git revert:*)", "Bash(git reset:*)", "Bash(git commit:*)", "Bash(claude:*)", "Bash(npm show:*)".
  - Copilot sessions should respect these local assistant permissions when proposing automated commits or git operations.

Notes for Copilot sessions
- Prefer suggestions that operate on the notebook: small, incremental code cells or helper Python modules imported by the notebook.
- Avoid proposing repository-wide build-system changes (no packaging config detected). If user requests packaging, ask for desired tool (poetry/poetry.lock, pip, pipenv) first.
- When asked to run or test code, recommend local Jupyter execution steps rather than assuming a CI exists.

Checks performed
- Looked for typical Python project files and AI assistant configs; incorporated `.claude/settings.local.json` permissions into guidance.

If you want, add: 
- `requirements.txt` or `pyproject.toml` (helps Copilot propose concrete install/test commands)
- A small `tests/` folder with pytest to enable test-running suggestions

---
Created by repository assistant. If you'd like tweaks (more detail about the notebook contents, adding test/run examples, or integrating other AI assistant configs), say what to include.
