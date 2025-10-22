# Lang Chain Workshop

A beginner-friendly workshop repository showing how to explore and experiment with LangChain-style projects in Python. This repo contains example notebooks, a small local environment, and a Chromadb database to get you started quickly.

This README will guide you through the essentials: what this project is, how to set up the environment on Windows (PowerShell), how to open and run the included notebook, and quick troubleshooting tips.

## What is in this repository

- `notebooks/workshop.ipynb` — A Jupyter notebook containing the workshop walkthrough and runnable examples.
- `data/` — Sample data used by the workshop (if any).
- `chroma_db/chroma.sqlite3` — A small SQLite database used by Chroma (vector DB) examples.
- `requirements.txt` — Python dependencies for the project.
- `env/` — An optional virtual environment included for convenience (already contains many packages). You can use it or create your own.

## Goals

- Learn how to run a Python notebook locally on Windows.
- Understand how to install and manage dependencies using a virtual environment.
- Explore a simple example using a local ChromaDB SQLite instance.

## Quick start (Windows, PowerShell)

These steps assume you have Python 3.10+ installed. If you don't, download it from https://www.python.org/downloads/.

1. Open PowerShell and change to the project folder:

   cd '~/Lang_Chain_workshop/Lang_Chain_Workshop'

2. Create a fresh venv, follow the create steps below.

   # Create and activate a new venv
   python -m venv .venv; .\.venv\Scripts\Activate.ps1

3. Install dependencies:

   python -m pip install --upgrade pip; pip install -r requirements.txt

4. Start Jupyter and open the notebook (If not using VsCode):

   python -m notebook

   Then open `notebooks/workshop.ipynb` in the browser that opens.

5. Run cells sequentially in the notebook. If a cell requires creating or connecting to the vector DB, follow any prompts printed in the notebook.

## Troubleshooting

- If Python isn't found: ensure Python is installed and added to PATH. Close and reopen PowerShell after installation.
- Permission error when activating the script: run `Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned -Force` in PowerShell once to allow local activation scripts.
- If Jupyter notebook doesn't start: ensure `notebook` is installed (`pip install notebook`) and try `python -m notebook` again.
- If package installation fails: confirm you're in the correct venv and run `pip --version` to check which Python it's attached to.

## Quick verification steps

1. Activate your venv.
2. Run `python -V` — you should see Python 3.10+.
3. Run `pip list` — verify packages from `requirements.txt` are installed.
4. Start `python -m notebook` and successfully open `notebooks/workshop.ipynb`.

## Next steps and resources

- Try editing the notebook and adding a new cell that queries the Chroma DB.
- Learn more about LangChain: https://python.langchain.com/
- Learn about ChromaDB: https://www.trychroma.com/

## Contributing

If you'd like to add examples, fixes, or improvements, please open a pull request or submit issues describing what you'd like to change.

---

If anything in this README is unclear or you want additional step-by-step screenshots or commands tailored to your setup, tell me what OS/terminal and I'll update it.
