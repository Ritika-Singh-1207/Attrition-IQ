# 🧠 AttritionIQ — HR Employee Attrition Prediction System

> An end-to-end Machine Learning web application designed to predict employee attrition using deep learning. Powered by an Artificial Neural Network (ANN) trained on the IBM HR Analytics dataset, AttritionIQ provides actionable flight-risk assessments with real-time probability scoring.

🔗 **GitHub:** [Ritika-Singh-1207/Attrition-IQ](https://github.com/Ritika-Singh-1207/Attrition-IQ)  
🌐 **Live Demo:** [Live Application](https://employee-attrition-predictor.netlify.app)

---

## 📌 Overview

**AttritionIQ** is a full-stack HR analytics platform that bridges predictive machine learning with an interactive interface. By evaluating key organizational and job-related parameters, the platform calculates an employee's probability of leaving, enabling proactive retention strategies.

---

## ⚙️ Tech Stack

| Component | Technology |
|---|---|
| 🤖 Model Architecture | TensorFlow / Keras (Artificial Neural Network) |
| ⚖️ Class Balancing | SMOTE (`imbalanced-learn`) |
| 🔧 Backend API | Flask (Python), Flask-CORS |
| 🎨 Frontend | React.js, Recharts, Modern CSS |
| 📐 Data Processing | Scikit-learn (StandardScaler, OneHotEncoder) |
| 📊 Dataset | IBM HR Analytics (1,470 records, 35 features) |

---

## 🏗️ Architecture & Pipeline

```
📂 Raw Dataset (1,470 rows)
    → 🔄 Preprocessing & Encoding (OHE + StandardScaler)
        → ✂️ Train/Test Split (80/20)
            → ⚖️ SMOTE Oversampling (Minority Class Balancing)
                → 🧠 ANN Training (128 → 64 → 32 → 1 Sigmoid)
                    → 📊 Evaluation (Precision, Recall, F1-Score)
                        → 🚀 Flask REST API Inference
```

---

## 🧠 Model Details

### Neural Network Design
- **Input & Hidden Layers:** Dense layers with ReLU activation (`128 → 64 → 32`)
- **Regularization:** Dropout layers (`0.3, 0.3, 0.2`) to mitigate overfitting
- **Output Layer:** Single neuron with Sigmoid activation for binary classification
- **Optimization:** Adam optimizer, Binary Cross-Entropy loss, EarlyStopping (patience = 10)
- **Exported Pipeline Artifacts:** `attrition_model.h5`, `scaler.pkl`, `label_encoder.pkl`, `model_columns.pkl`

---

## 📊 Model Evaluation

| Metric | Class 0 (Stays) 🟢 | Class 1 (Leaves) 🔴 |
|---|---|---|
| **Precision** | 89% | 58% |
| **Recall** | 91% | 40% |
| **F1-Score** | 90% | 47% |
| **Overall Accuracy** | **83%** | — |

> 💡 **Key Data Insights:**
> - **Overtime:** Strongest indicator of attrition — employees logging regular overtime show 3x higher turnover risk.
> - **Demographics:** Age group 18–25 experiences the highest turnover rate (~37%).
> - **Departmental Trends:** Sales roles demonstrate the highest attrition rate across departments.
> - **Business Travel:** Frequent travel positively correlates with attrition probability.

---

## 📁 Repository Structure

```
AttritionIQ/
├── 🔧 backend/
│   ├── app.py                  # Flask REST API
│   ├── attrition_model.h5      # Serialized Keras ANN Model
│   ├── scaler.pkl              # Fitted StandardScaler
│   ├── label_encoder.pkl       # Fitted LabelEncoder
│   └── model_columns.pkl       # Aligned feature column schemas
├── 🎨 src/
│   └── components/
│       ├── Dashboard.js        # Organizational analytics dashboard
│       ├── Predictor.js        # Employee risk prediction form
│       ├── Insights.js         # Feature importance & model insights
│       ├── Hero.js             # Landing page
│       ├── Navbar.js
│       └── Footer.js
├── 📓 notebooks/
│   └── attrition_training.ipynb  # End-to-end data pipeline & training
├── public/
├── package.json
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/Ritika-Singh-1207/Attrition-IQ.git
cd Attrition-IQ
```

### 2. Backend Setup
```bash
cd backend
pip install flask flask-cors tensorflow scikit-learn imbalanced-learn
python app.py
# Server starts on http://localhost:5000
```

### 3. Frontend Setup
```bash
# In the project root directory
npm install
npm start
# Client starts on http://localhost:3000
```

---

## 🔭 Roadmap & Future Improvements

- [ ] Integrate SHAP (SHapley Additive exPlanations) for real-time feature contribution breakdown.
- [ ] Optimize decision threshold from 0.5 → 0.3 for improved minority class recall.
- [ ] Implement comparative benchmarking against XGBoost and Random Forest.
- [ ] Cloud deployment pipeline setup on Render / Railway.

---

## 👤 Author

- **GitHub:** [@Ritika-Singh-1207](https://github.com/Ritika-Singh-1207)

---

## 📄 License & Attribution
- Dataset source: [IBM HR Analytics Employee Attrition & Performance](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
git push -u origin main
