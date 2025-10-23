# Price Prediction Model

## Overview
This repository contains a machine learning project for predicting house prices using Random Forest and Linear Regression models. It includes data preprocessing, model training, a Flask backend server, and a Next.js frontend client for making predictions.

## Features
- Predict house prices using:
  - Linear Regression (lr)
  - Random Forest (rf)
- Preprocessing steps for cleaning and preparing datasets.
- Flask backend server (`server.py`) with REST API endpoint `/predict`.
- Next.js frontend for a user-friendly interface.
- Organized structure for datasets, models, notebooks, and dependencies.

## Repository Structure
```
price-prediction/
│
├── client/                 # Next.js frontend
├── dataset/                # Raw and processed datasets
├── models/                 # Saved trained models
├── model.ipynb             # Notebook for model training
├── preprocess.ipynb        # Notebook for data preprocessing
├── server.py               # Flask backend server for predictions
├── util.py                 # Utility functions
└── requirements.txt        # Python dependencies
```

## Installation
### Backend (Flask)
1. Clone the repository:
```bash
git clone https://github.com/maajid7ahmed/house_price-predict.git
cd house_price_predictio
```
2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```
3. Install Python dependencies:
```bash
pip install -r requirements.txt
```
Dependencies include: Flask, pandas, scikit-learn, numpy, joblib

4. Run the Flask server:
```bash
python server.py
```
The server will run by default on `http://localhost:8000`.

### Frontend (Next.js Client)
1. Navigate to the client folder:
```bash
cd client
```
2. Install dependencies:
```bash
npm install
# or
yarn
```
3. Create a `.env.local` file in the client folder with the backend URL:
```
NEXT_PUBLIC_API_URL=http://localhost:8000
```
4. Start the Next.js development server:
```bash
npm run dev
# or
yarn dev
```
The client will run on `http://localhost:3000` and make API calls to your Flask backend.

## API Endpoint
**`/predict`**
- Method: POST
- Query Parameter: `model=lr|rf` (lr = Linear Regression, rf = Random Forest)
- Expected JSON Body:
```json
{
  "Bathrooms": 2,
  "Bedrooms": 3,
  "Location": "City",
  "Size_sqft": 1500,
  "YearBuilt": 2010
}
```
- Response Example:
```json
{
  "prediction": 350000
}
```
- Message:
```json
{
  "message": "House Price Prediction API"
}
```

## Usage
**Backend (Flask)**
- `preprocess.ipynb`: Clean and preprocess your dataset.
- `model.ipynb`: Train models and save them in the `models/` folder.
- `server.py`: Run the Flask server to handle `/predict` requests.

**Frontend (Next.js)**
- Access the web app via `http://localhost:3000`.
- Input features and get predicted house prices in real-time.

## Models
- Linear Regression (lr): Simple and interpretable for linear relationships.
- Random Forest (rf): Handles non-linear relationships and generally gives higher accuracy.

## Dependencies
**Backend (Flask):**
- Python 3.x
- Flask
- pandas
- scikit-learn
- numpy
- joblib

**Frontend (Next.js):**
- Node.js / npm
- Next.js
- React

## Author
- maajid7ahmed
- GitHub: https://github.com/maajid7ahmed

## License
MIT License
