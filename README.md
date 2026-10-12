# Mushroom Classification — Edible or Poisonous

**A scikit-learn random forest trained on the mushroom attributes dataset, with a Streamlit form that takes 19 mushroom features and reports "edible" or "poisonous".**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) ![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white) ![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white) ![pandas](https://img.shields.io/badge/pandas-150458?style=flat&logo=pandas&logoColor=white) ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white) ![seaborn](https://img.shields.io/badge/seaborn-4C72B0?style=flat&logo=python&logoColor=white)

## Overview

This is a small classification project: explore the mushroom dataset in a notebook (`mainn.ipynb`), train a random forest, save it as `mushroom_model.pkl`, and wrap it in a web form (`app.py`).

Please read this before using it: it is a learning project, **not a tool for deciding whether a mushroom is safe to eat**. The dataset is not included in the repo (the notebook reads `mushrooms.csv` from a local Windows path), the notebook was committed without outputs I can quote, so I report no accuracy figures. There is also a likely encoding mismatch between the notebook and the app, described under How It Works. Treat the app's output as unverified until that is fixed.

## Key Features

- **Notebook workflow** — loading, `info()`, null counts, `describe()`, dropping three columns (`cap-shape`, `gill-attachment`, `veil-type`), label-encoding the remaining 19 feature columns and the target, and a 70/30 train/test split with `random_state=73`.
- **Random forest model** — `RandomForestClassifier(n_estimators=200, max_depth=6, class_weight='balanced', random_state=42)`.
- **Evaluation code** — default accuracy, a confusion matrix and classification report at an adjusted 0.3 probability threshold, a feature-correlation heatmap, feature importances, and train versus test accuracy.
- **Streamlit form** — 19 dropdowns inside an `st.form` with a Predict button, pink-themed custom CSS, and a green or red result message.
- **Saved model** — the trained forest is pickled to `mushroom_model.pkl` and loaded by the app.

## How It Works

1. **Training (notebook).** The target `class` and each feature column are encoded with scikit-learn's `LabelEncoder`. The forest is fitted on the training split and pickled. Only the model is saved; the fitted encoders are not.
2. **Serving (app).** `app.py` loads the pickle, shows the 19 selectboxes, and on submit converts each choice to an integer using a dictionary of mappings written by hand in the file (for example `'cap-surface': {'smooth': 0, 'scaly': 1, 'fibrous': 2, 'grooves': 3}`). The integers go into a one-row DataFrame, the model predicts, and the app shows "edible" if the prediction equals 1 and "poisonous" otherwise.

Two things I could not confirm from the repo and that look wrong:

- **Feature encoding.** `LabelEncoder` numbers categories alphabetically by the values in the CSV, and the app's hand-typed numbers follow the readable names instead. Unless the two orderings happen to agree for every feature, the app feeds the model different numbers than it was trained on. I cannot check this without the CSV.
- **Label direction.** If the target column uses the usual `e` (edible) and `p` (poisonous) values, `LabelEncoder` makes edible 0 and poisonous 1, while the app treats 1 as edible. That would invert the result.

The old README also mentions a scaler and a `train_model.py` script; neither exists in the code, and the app does no scaling.

## Tech Stack

- **Language:** Python
- **Modelling:** scikit-learn (`RandomForestClassifier`, `LabelEncoder`, metrics), pandas, NumPy
- **Exploration:** matplotlib, seaborn, Jupyter
- **App:** Streamlit

## Getting Started

### Prerequisites

- Python 3 and `pip`

### Installation

```bash
git clone https://github.com/Danushika06/Mushroom-Classification.git
cd Mushroom-Classification
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
pip install streamlit jupyter
```

`requirements.txt` pins numpy, pandas, scikit-learn, matplotlib, seaborn and joblib but does not list Streamlit, so install it separately as above. The pickle was made with scikit-learn, and `requirements.txt` pins `scikit-learn==1.3.1`; keep that version so the file loads.

### Running

```bash
streamlit run app.py
```

To retrain, obtain a `mushrooms.csv` of the standard mushroom attributes dataset, change `csv_path` in the first notebook cells to its location (it currently points to a folder on my old machine), and run `mainn.ipynb` top to bottom, which rewrites `mushroom_model.pkl`.

## Usage

Open the local URL Streamlit prints, choose a value for each of the 19 features (cap surface and colour, bruises, odor, gill and stalk properties, veil colour, ring number and type, spore print colour, population, habitat), and press Predict. Do not rely on the result for real foraging decisions.

## Project Structure

```
Mushroom-Classification/
├── app.py                 # Streamlit form, hand-written encodings, prediction
├── mainn.ipynb            # data exploration, training, evaluation, model export
├── mushroom_model.pkl     # pickled RandomForestClassifier
├── requirements.txt
└── README.md
```

---

## Contact

<table>
  <tr><td><b>GitHub:</b> <a href="https://github.com/Danushika06">Danushika06</a></td><td><b>LinkedIn:</b> <a href="https://www.linkedin.com/in/danushika-n-323b4628b/">danushika-n</a></td></tr>
  <tr><td colspan="2" align="center"><b>Email:</b> <a href="mailto:danushikanagarajan@gmail.com">danushikanagarajan@gmail.com</a></td></tr>
</table>

Built by **Danushika N**
