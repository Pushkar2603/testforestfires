# Forest Fire Prediction Web App

This project is a Flask-based web application that predicts forest fire risk using a trained machine learning model. It uses weather and environmental features from the Algerian Forest Fires dataset and serves a simple browser interface for making predictions.

## Overview

The application loads a saved Ridge Regression model and StandardScaler from the `models/` directory and exposes a prediction endpoint that accepts user-supplied values such as temperature, humidity, wind speed, rainfall, FFMC, DMC, ISI, class, and region.

## Features

- Flask web interface
- Machine learning-based forest fire prediction
- Input form for environmental parameters
- Model serving via a simple REST-like form submission flow
- Ready for deployment with a WSGI-compatible app object

## Project Structure

```text
Deploy/
├── application.py          # Flask app and prediction logic
├── requirements.txt        # Python dependencies
├── models/
│   ├── ridge.pkl           # Trained Ridge Regression model
│   └── scaler.pkl          # Saved preprocessing scaler
├── templates/
│   ├── index.html          # Landing page
│   └── home.html           # Prediction result page
├── notebooks/
│   ├── 2.0-EDA And FE Algerian Forest Fires.ipynb
│   ├── 3.0-Model Training.ipynb
│   └── Algerian_forest_fires_dataset_UPDATE.csv
└── README.md
```

## Tech Stack

- Python 3
- Flask
- NumPy
- Pandas
- scikit-learn

## Setup

1. Clone the repository or open the project folder.
2. Create a virtual environment (optional but recommended):

```bash
python -m venv venv
source venv/bin/activate   # Linux/macOS
venv\Scripts\activate      # Windows
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

## Run the Application

From the project root, start the Flask app:

```bash
python application.py
```

Then open:

```text
http://localhost:5000/
```

The app exposes the main page at `/` and the prediction handler at `/predictdata`.

## Usage

- Visit the home page.
- Enter the required environmental and fire-related values.
- Submit the form to get the model prediction.

## Notes

- The app is configured with `application = Flask(__name__)` and `app = application`, which makes it suitable for deployment on WSGI servers such as Gunicorn.
- The model files must remain in the `models/` directory relative to the application runtime.

## License

This project is provided for educational and demonstration purposes.
