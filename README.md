# FIFA World Cup Intelligence: EDA, Machine Learning & GenAI Assistant

An interactive football analytics portfolio project that combines exploratory data analysis (EDA), synthetic-scenario machine-learning experiments, team-profile clustering, and an optional Gemini-powered natural-language assistant.

## Project overview

The notebook explores three CSV datasets at team, player, and match level. It audits data quality, summarizes performance statistics, visualizes patterns, evaluates several classifiers on deliberately synthetic match scenarios, clusters hypothetical team profiles, and provides an optional GenAI interface for asking questions about the available data and general football topics.

### Main components

- **Data quality:** column types, missing values, duplicate rows, and unique-value checks.
- **Match analysis:** match outcomes, scorelines, goals, and available match-level statistics.
- **Team analysis:** scoring, goals conceded, possession, and other available team metrics.
- **Player analysis:** goals, assists, age, position, minutes, and per-90 statistics where available.
- **Machine learning:** baseline and classifier comparison, cross-validation, holdout evaluation, and tree-based feature importance.
- **Clustering:** K-means exploration of hypothetical team profiles.
- **GenAI assistant:** optional question-answering with the Google Gemini API, using notebook context and without live results access.

## Repository structure

```text
FIFA_World_Cup_Intelligence_GitHub_Ready/
├── FIFA_World_Cup_Intelligence_EDA_GenAI.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── data/
    ├── teams.csv
    ├── players.csv
    └── matches.csv
```

## Dataset inventory

| File | Rows | Columns | Purpose |
|---|---:|---:|---|
| `teams.csv` | 48 | 136 | Team-level aggregate statistics |
| `players.csv` | 1,248 | 72 | Player-level statistics |
| `matches.csv` | 104 | 42 | Match-level results and statistics |

The notebook loader searches the project root and the `data/` directory. Keep the notebook and `data/` folder together and launch Jupyter from the project root.

> **Dataset provenance and redistribution:** Before making the repository public, confirm the original source, attribution requirements, and license/permission for redistributing these CSV files. Do not imply official FIFA affiliation. If redistribution is not permitted, remove the CSVs from the public repository and document how users can obtain them lawfully.

## Setup

Python 3.10 or newer is recommended.

1. Clone or download this repository.
2. From the project root, create and activate a virtual environment if desired.
3. Install dependencies:

   ```bash
   python -m pip install -r requirements.txt
   ```

4. Start Jupyter:

   ```bash
   jupyter notebook
   ```

5. Open `FIFA_World_Cup_Intelligence_EDA_GenAI.ipynb` and run cells from top to bottom.

The notebook includes a dependency-installation cell as well. Use either that cell or `requirements.txt`; you do not need to install the dependencies twice. Restart the kernel if you install packages into an environment while Jupyter is already running.

## Optional Gemini assistant

The analysis and synthetic ML sections can be run without a Gemini API key. The assistant is optional and does not make an API request automatically.

To enable it, provide a valid Gemini API key using an environment variable named `GEMINI_API_KEY`, or enter the key when the notebook securely prompts for it. Do not write the key into the notebook, commit it to Git, or share it in screenshots.

PowerShell example for the current terminal session:

```powershell
$env:GEMINI_API_KEY = "YOUR_API_KEY_HERE"
```

Then set `RUN_GENAI_DEMO = True` in the optional demo cell, or call `ask_football_assistant("Which players scored the most goals?")` after the assistant function is defined.

API availability, quota, and supported model names can change; if a request fails, check the Google Gemini API documentation and your account's model access.

## Important interpretation limits

- EDA findings describe only the included CSV files and their coverage. Verify source provenance and coverage before treating them as authoritative historical facts.
- The ML target labels are generated from a documented synthetic rule. Model scores measure how well models reproduce that rule on generated scenarios; **they are not evidence of real-world World Cup match-prediction accuracy**.
- The clustered team profiles are hypothetical synthetic profiles, not real national-team clusters.
- The assistant has no live scores or real-time football data. General-knowledge responses may be outside the supplied datasets.
- Statistical associations in the notebook do not by themselves establish causation.

## Tools and libraries

Python · Jupyter Notebook · Pandas · NumPy · Matplotlib · Seaborn · Plotly · SciPy · Scikit-learn · Joblib · Google GenAI SDK

## Outputs

Running the notebook may create generated scenario data, model comparison CSV files, cross-validation results, and a serialized synthetic classifier in the working directory. These are reproducible outputs and are excluded from Git by `.gitignore` unless you choose to version them intentionally.

## Suggested next steps

- Add source citations and a dataset license/attribution note.
- Validate a predictive model on real historical data with a clear time-based split before making real-world prediction claims.
- Add screenshots or selected visualizations to the repository README after running the notebook.
