# Stock Analytics & Predictions — Codveda Data Analytics

Internship project: **data cleaning**, **EDA**, **regression**, and **classification** on historical stock OHLCV data, with an interactive **Streamlit** UI.

---

## Problem statement

Work with a real-world **stock prices** dataset that may contain **missing values**, **duplicate rows**, and **inconsistent formats**. Deliver:

1. **Cleaning & preprocessing** before modeling.
2. **Exploratory analysis** (summary stats, distributions, correlations, relationships).
3. **Regression** to predict **close** from **open, high, low, volume**.
4. **Classification** to predict whether **the next day’s close** is **higher** than **today’s close** (`Target` = 1 vs 0), using **logistic regression**.

This repo also includes **Jupyter notebooks** (`level1_basic.ipynb`, `level2_intermediate.ipynb`, `level3_advanced.ipynb`) aligned with Codveda task levels.

---

## Dataset

| Item | Detail |
|------|--------|
| **File** | `dataset/2) Stock Prices Data Set.csv` |
| **Columns** | `symbol`, `date`, `open`, `high`, `low`, `close`, `volume` |
| **Notes** | Panel data (many symbols × dates). The app lets you pick one **symbol** at a time for EDA and models. |

Place the CSV at the path above relative to the project root.

---

## Steps (Cleaning → EDA → Model)

1. **Cleaning**
   - Parse `date` to datetime; coerce OHLC and `volume` to numeric.
   - **Remove duplicate** rows; **drop** rows still missing required fields after coercion.
2. **EDA**
   - `describe()` for summary statistics.
   - **Histogram** (e.g. close), **correlation heatmap**, **open vs close** scatter (see **Data cleaning & EDA** tab in the app).
3. **Regression**
   - **Linear regression**: `close` ~ `open`, `high`, `low`, `volume` (with `StandardScaler`).
   - Metrics: **R²**, **MSE** on a time-ordered holdout split.
4. **Classification**
   - `Target = (close.shift(-1) > close).astype(int)`.
   - **Logistic regression** on scaled features; metrics: **accuracy**, **precision**, **recall**, **F1**; display **P(up)** for the latest row.

---

## How to run

```bash
cd /path/to/internship-project
python -m pip install -r requirements.txt
python -m streamlit run app.py
```

Open the URL shown in the terminal (usually `http://localhost:8501`).

**Notebooks:**

```bash
jupyter notebook
```

---

## Screenshots (add your own)

Replace or add images under `docs/screenshots/` and link them here for your report / GitHub / LinkedIn.

| Screenshot | What to capture |
|------------|-----------------|
| `docs/screenshots/01_eda.png` | **Data cleaning & EDA** tab — histogram, scatter, heatmap |
| `docs/screenshots/02_regression.png` | **Predict close** tab — model explanation + predicted value |
| `docs/screenshots/03_classification.png` | **Predict next day ↑** tab — metrics + probability |

If the folder does not exist yet, create it:

```text
docs/screenshots/
```

*(GitHub will display these images in the README once you commit the PNG files.)*

---

## Results (fill in after you run)

| Stage | Result |
|-------|--------|
| Cleaning | e.g. missing cells removed/dropped: ___; duplicates removed: ___ |
| EDA | Key correlation (e.g. open–close): ___; distribution notes: ___ |
| Regression | Example test **R²** / **MSE** for symbol `AAPL`: ___ / ___ |
| Classification | Example test **accuracy** / **F1** for symbol `AAPL`: ___ / ___ |

*Copy actual numbers from the Streamlit UI after training.*

---

## Repository layout

```text
internship project/
├── app.py                 # Streamlit UI
├── requirements.txt
├── dataset/
│   └── 2) Stock Prices Data Set.csv
├── level1_basic.ipynb
├── level2_intermediate.ipynb
├── level3_advanced.ipynb
└── README.md
```

---

## Disclaimer

Models are for **learning and internship demonstration** only, not financial or investment advice.
