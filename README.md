# NLG — Natural Language Generator

## Purpose
This repository contains the project for Assignment 1 (NLG) used for learning sequence-to-text generation and dataset linearization. It includes the dataset exports, a Jupyter notebook with experiments, and supporting PDFs.

## What you'll find
- `Group_188_PS2_Submission.ipynb` — main notebook with experiments and usage examples.
- `dataset/` — dataset files and token mappings (JSON).
- `Assignment_PS2_NLG.pdf`, `Group_188_PS2_Submission.pdf` — assignment and deliverables.

## Project Structure

- `dataset/` — raw and linearized JSON files:
  - `train.json`, `validation.json`, `test.json` — original splits
  - `linearized_train.json`, `linearized_validation.json`, `linearized_test.json` — linearized inputs for NLG models
  - `vocab.json`, `id_to_token.json`, `token_to_id.json` — vocabulary and mappings

## Quickstart

1. Create and activate a Python virtual environment (macOS/Linux):

```bash
python3 -m venv .venv
source .venv/bin/activate
```

2. Install common tools (adjust as needed):

```bash
pip install jupyter numpy pandas
```

3. Open the notebook:

```bash
jupyter notebook Group_188_PS2_Submission.ipynb
```

Notes: If you rely on a specific model or library (PyTorch/Transformers), add those to your environment before running training/evaluation cells.

## Usage
- The notebook demonstrates data loading, linearization, and baseline experiments. Use the `dataset/` JSON files as inputs for any preprocessing scripts or model training.

## Architecture Diagram

```mermaid
flowchart LR
  U[User / Researcher] --> NB[Notebook]
  NB --> DL[Data Loader]
  DL --> P[Preprocessing]
  P --> L[Linearizer]
  L --> M[Model (NLG)]
  M --> O[Output: Generated Text]
  O --> E[Evaluation]
  subgraph DatasetFolder [dataset/]
    D1[train.json]
    D2[validation.json]
    D3[test.json]
    LD1[linearized_train.json]
  end
  DL --- DatasetFolder
  classDef folder fill:#f9f,stroke:#333,stroke-width:1px
  class DatasetFolder folder
```

## Lessons Learned
- Linearizing structured inputs simplifies mapping input fields to target text.
- Maintaining token<->id mappings ensures reproducible decoding.
- Jupyter notebooks are useful for iterative experiments and visualizing intermediate outputs.

## Next steps (suggested)
- Add a `requirements.txt` with exact dependencies.
- Create modular scripts for preprocessing, training, and evaluation.
- Add unit tests for data loading and linearization logic.

## License & Contact
Feel free to reach me at iosdeveloper.ipa@gmail.com (PavanKumarArepu).
