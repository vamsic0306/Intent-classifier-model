# Intent Classifier Model

This small project demonstrates:
- Training a tiny text classifier.
- Saving the model artifact.
- Serving predictions via a Flask API (`/predict`).

## Quick start (local)
1. Create a virtualenv and install:
    python3 -m venv .venv
    source .venv/bin/activate
    pip install -r requirements.txt

2. Train the model:
    python model/train.py
    This will create `model/artifacts/intent_model.pkl`.

3. Run the API:
    python app.py
    The API will be available at http://127.0.0.1:6000


   # Intent Classifier Model

This small project demonstrates:
- Training a tiny text classifier.
- Saving the model artifact.
- Serving predictions via a Flask API (`/predict`).

## Quick start (local)
1. Create a virtualenv and install:
    python3 -m venv .venv
    source .venv/bin/activate
    pip install -r requirements.txt

2. Train the model:
    python model/train.py
    This will create `model/artifacts/intent_model.pkl`.

3. Run the API:
    python app.py
    The API will be available at http://127.0.0.1:6000

4. Example request:
    curl -X POST http://127.0.0.1:6000/predict -H "Content-Type: application/json" -d '{"text":"I want to cancel my subscription"}'

    Response:
    {
        "intent": "complaint",
        "probabilities": {"complaint": 0.85, "question": 0.05, ...}
    }


   # 🚀 Intent Classifier Model

A machine learning-based API that classifies user input into different intents such as **complaint, question, request, and feedback**.

---

## 📌 Features

* 🔍 Text classification using ML model
* ⚡ Fast API for real-time predictions
* 📦 Simple training and deployment pipeline
* 🧠 Outputs intent with probability scores

---

## 🏗️ Project Structure

```
.
├── model/
│   ├── train.py
│   └── artifacts/
│       └── intent_model.pkl
├── app.py
├── requirements.txt
└── README.md
```

---

## 🚀 Quick Start (Local Setup)

### 1️⃣ Create Virtual Environment & Install Dependencies

```bash
python3 -m venv .venv
source .venv/bin/activate   # Linux / Mac
.venv\Scripts\activate      # Windows

pip install -r requirements.txt
```

---

### 2️⃣ Train the Model

```bash
python model/train.py
```

➡️ This will generate:

```
model/artifacts/intent_model.pkl
```

---

### 3️⃣ Run the API

```bash
python app.py
```

🌐 API will be available at:

```
http://127.0.0.1:6000
```

---

### 4️⃣ Test the API

#### Example Request

```bash
curl -X POST http://127.0.0.1:6000/predict \
  -H "Content-Type: application/json" \
  -d '{"text": "I want to cancel my subscription"}'
```

#### Example Response

```json
{
  "intent": "complaint",
  "probabilities": {
    "complaint": 0.85,
    "question": 0.05
  }
}
```

---

## 🧠 How It Works

1. Text input is received via API
2. Preprocessing is applied
3. Trained model predicts intent
4. Output includes intent + probability scores

---

## ⚙️ Requirements

* Python 3.8+
* pip

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## 🐳 Docker (Optional)

```bash
# Build image
docker build -t intent-classifier .

# Run container
docker run -p 6000:6000 intent-classifier
```

---

## ☸️ Kubernetes (Optional)

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: intent-classifier
spec:
  replicas: 2
  selector:
    matchLabels:
      app: intent-classifier
  template:
    metadata:
      labels:
        app: intent-classifier
    spec:
      containers:
      - name: intent-classifier
        image: intent-classifier:latest
        ports:
        - containerPort: 6000
```

---

## 📌 Notes

* Ensure model is trained before running API
* Update `requirements.txt` if dependencies change
* Model artifacts are stored in `model/artifacts/`

---

## 🚀 Future Improvements

* Add model versioning (MLflow / DVC)
* Add authentication to API
* Deploy using CI/CD pipeline
* Improve model accuracy

---


5. Example request:
    curl -X POST http://127.0.0.1:6000/predict -H "Content-Type: application/json" -d '{"text":"I want to cancel my subscription"}'

    Response:
    {
        "intent": "complaint",
        "probabilities": {"complaint": 0.85, "question": 0.05, ...}
    }
