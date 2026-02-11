# 🏡 House Price Prediction API

A production-ready machine learning API that predicts house prices based on 13 key features using Linear Regression and FastAPI.

## 📋 Overview

This project implements an end-to-end machine learning pipeline that trains a predictive model on the Boston Housing dataset and deploys it as a RESTful API for real-time predictions.

## ✨ Features

- **Machine Learning Model**: Linear Regression trained on 506 housing samples
- **RESTful API**: FastAPI backend for instant predictions
- **Data Validation**: Pydantic models ensure input integrity
- **Model Persistence**: Serialized model using joblib for efficient deployment
- **13 Feature Analysis**: Comprehensive housing characteristics evaluation

## 🛠️ Tech Stack

- **Python 3.x**
- **Scikit-learn** - Machine learning model
- **FastAPI** - Web framework
- **Pydantic** - Data validation
- **Uvicorn** - ASGI server
- **Joblib** - Model serialization

## 📊 Dataset Features

| Feature | Description |
|---------|-------------|
| CRIM | Per capita crime rate by town |
| ZN | Proportion of residential land zoned for lots over 25,000 sq.ft. |
| INDUS | Proportion of non-retail business acres per town |
| CHAS | Charles River dummy variable (1 if tract bounds river; 0 otherwise) |
| NOX | Nitric oxides concentration (parts per 10 million) |
| RM | Average number of rooms per dwelling |
| AGE | Proportion of owner-occupied units built prior to 1940 |
| DIS | Weighted distances to five Boston employment centres |
| RAD | Index of accessibility to radial highways |
| TAX | Full-value property-tax rate per $10,000 |
| PTRATIO | Pupil-teacher ratio by town |
| B | 1000(Bk - 0.63)^2 where Bk is the proportion of Black residents by town |
| LSTAT | % lower status of the population |

**Target Variable**: MEDV (Median value of owner-occupied homes in $1000's)

## 🚀 Installation

1. **Clone the repository**
```bash
git clone <repository-url>
cd "Predicting House pricing"
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

## 💻 Usage

### Running the API

```bash
uvicorn app:app --reload
```

The API will be available at `http://127.0.0.1:8000`

### API Documentation

Access interactive API docs at:
- Swagger UI: `http://127.0.0.1:8000/docs`
- ReDoc: `http://127.0.0.1:8000/redoc`

### Making Predictions

**Endpoint**: `POST /predict`

**Request Body**:
```json
{
  "CRIM": 0.00632,
  "ZN": 18.0,
  "INDUS": 2.31,
  "CHAS": 0,
  "NOX": 0.538,
  "RM": 6.575,
  "AGE": 65.2,
  "DIS": 4.09,
  "RAD": 1,
  "TAX": 296,
  "PTRATIO": 15.3,
  "B": 396.9,
  "LSTAT": 4.98
}
```

**Response**:
```json
{
  "predicted_price": 24.0
}
```

### Example with cURL

```bash
curl -X POST "http://127.0.0.1:8000/predict" \
  -H "Content-Type: application/json" \
  -d '{
    "CRIM": 0.00632,
    "ZN": 18.0,
    "INDUS": 2.31,
    "CHAS": 0,
    "NOX": 0.538,
    "RM": 6.575,
    "AGE": 65.2,
    "DIS": 4.09,
    "RAD": 1,
    "TAX": 296,
    "PTRATIO": 15.3,
    "B": 396.9,
    "LSTAT": 4.98
  }'
```

## 📁 Project Structure

```
Predicting House pricing/
│
├── app.py              # FastAPI application
├── House.ipynb         # Model training notebook
├── Data.csv            # Boston Housing dataset
├── lr_model.pkl        # Trained model (serialized)
├── requirements.txt    # Project dependencies
├── .gitignore         # Git ignore file
└── README.md          # Project documentation
```

## 🔧 Model Training

The model is trained in `House.ipynb` using:
1. Data loading and exploration
2. Feature engineering and preprocessing
3. Linear Regression model training
4. Model evaluation
5. Model serialization with joblib

## 📈 Model Performance

The Linear Regression model provides baseline predictions for house prices based on the 13 input features. Performance metrics are available in the training notebook.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is open source and available under the MIT License.

## 👤 Author

**Your Name**
- LinkedIn: [Your LinkedIn Profile]
- GitHub: [Your GitHub Profile]

## 🙏 Acknowledgments

- Boston Housing Dataset from the UCI Machine Learning Repository
- FastAPI framework for modern API development
- Scikit-learn for machine learning capabilities

---

⭐ Star this repository if you find it helpful!
