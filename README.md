# Port Waiting Time Predictor

A machine learning web application that predicts ship waiting time at ports based on various operational and environmental factors. Built with Flask and deployed on AWS EC2.

---

## About the Project

Port congestion is a major challenge in maritime logistics. This project uses a trained ML model to predict how long a ship will have to wait before getting a berth — helping ports and shipping companies plan operations more efficiently.

---

## Features

- Predicts waiting time (in hours) based on 7 input parameters
- Clean and responsive web UI
- Flask-based REST API backend
- Pre-trained Gradient Boosting model
- Deployed on AWS EC2

---

## Input Parameters

| Parameter | Description |
|---|---|
| Port | Shanghai / Rotterdam / Singapore |
| Ship Type | Bulk / Container |
| Cargo Size | Size of cargo (numeric) |
| Ships Waiting | Number of ships in queue |
| Weather | Clear / Storm / Fog |
| Berth Availability | Number of available berths |
| Season | Summer / Winter / Spring |

---

## Tech Stack

- **Language:** Python
- **Framework:** Flask
- **ML Model:** Gradient Boosting (scikit-learn)
- **Frontend:** HTML, CSS
- **Deployment:** AWS EC2

---

## Project Structure

```
port-predictor/
│
├── app.py                  # Flask application
├── model.pkl               # Trained ML model
├── encoders.pkl            # Label encoders for categorical features
├── port_encoder.pkl        # Port-specific encoder
├── requirements.txt        # Python dependencies
└── templates/
    └── index.html          # Frontend UI
```

---

## Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-username/port-predictor.git
cd port-predictor
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the application

```bash
python app.py
```

App will start at: `http://localhost:5000`

---

## Deployment on AWS EC2

1. Launch an EC2 instance (Ubuntu)
2. Install Python and pip
3. Clone this repo on the instance
4. Install dependencies using `pip install -r requirements.txt`
5. Run with gunicorn:

```bash
gunicorn -w 4 -b 0.0.0.0:5000 app:app
```

6. Open port 5000 in EC2 Security Group inbound rules
7. Access via `http://<your-ec2-public-ip>:5000`

---

## Model Details

- **Algorithm:** Gradient Boosting Regressor
- **Target Variable:** Waiting Time (hours)
- **Evaluation Metric:** RMSE / R² Score
- **Encoding:** Label Encoding for categorical variables

