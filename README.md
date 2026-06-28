# Cancer Predictor

A small breast cancer prediction project using Streamlit and scikit-learn.

## Project structure

- `ML/`
  - `app/main.py` - Streamlit web application for entering cell nuclei measurements and predicting benign vs malignant.
  - `assets/style.css` - CSS used by the Streamlit app.
  - `data/data.csv` - Breast cancer dataset used for training and slider bounds.
  - `model/main.py` - Script to train the logistic regression model and save model artifacts.
  - `model/model.pkl` - Serialized trained model.
  - `model/scaler.pkl` - Serialized `StandardScaler` used to scale input values.
  - `requirements.txt` - Python package dependencies.

## Requirements

- Python 3.11+ (or compatible Python 3.x)
- Install the project dependencies:

```bash
cd ML
pip install -r requirements.txt
```

## Train the model

If you need to retrain the model or the `model.pkl` / `scaler.pkl` files are missing:

```bash
cd ML
python model/main.py
```

This script reads `ML/data/data.csv`, trains a logistic regression classifier, and writes:
- `ML/model/model.pkl`
- `ML/model/scaler.pkl`

## Run the Streamlit app

From the `ML/app` directory:

```bash
cd ML/app
streamlit run main.py
```

Then open the URL printed by Streamlit in your browser.

## Notes

- The app loads data, model, scaler, and CSS using paths relative to `ML/app/main.py`.
- `data/data.csv` must remain in `ML/data/`.
- `model/model.pkl` and `model/scaler.pkl` must remain in `ML/model/`.

## What the app does

- Displays input sliders for breast cancer cell nucleus measurements.
- Scales values using the same preprocessing used during training.
- Predicts whether the sample is benign or malignant.
- Shows prediction probabilities and a radar chart visualization.
