# Penguin Species Predictor

This Streamlit application provides a professional interface for classifying Palmer Penguin species using a Random Forest or similar supervised learning model. It translates morphological measurements and geographical data into accurate species predictions in real-time.

## Overview

The application serves as a deployment wrapper for a classification model trained on the Palmer Penguins dataset. It bridges the gap between raw machine learning scripts and an end-user interface, allowing researchers or hobbyists to input physical attributes and receive an immediate classification.

## Technical Features

*   **Feature Engineering:** Automatically maps categorical variables (Island and Sex) to numerical values (0, 1, 2) required for model inference.
*   **Dynamic Controls:** Utilizes Streamlit's sidebar sliders and dropdowns for precise input parameter selection.
*   **State Management:** Efficiently handles input dataframes and triggers model prediction only upon user confirmation via action buttons.
*   **Optimized Loading:** Uses `joblib` for high-performance deserialization of the trained estimator.

## Project Architecture

```text
.
├── app.py                 # Core application logic and Streamlit UI
├── penguin_model.pkl      # Serialized machine learning estimator
├── requirements.txt       # Version-controlled dependency list
├── dataset/               # Optional: Source data for reference
└── README.md              # Project technical documentation
```

## Input Specifications

The model processes six primary features to determine the species:


| Feature | Type | Range / Options |
| :--- | :--- | :--- |
| **Island** | Categorical | Biscoe, Dream, Torgersen |
| **Culmen Length** | Numerical | 32.1mm - 59.6mm |
| **Culmen Depth** | Numerical | 13.1mm - 21.5mm |
| **Flipper Length**| Numerical | 172.0mm - 231.0mm |
| **Body Mass** | Numerical | 2700.0g - 6300.0g |
| **Sex** | Categorical | Male, Female |

## Installation and Deployment

### 1. Prerequisites
Ensure you have Python 3.8+ installed on your system.

### 2. Environment Setup
Clone the repository and create a virtual environment:
```bash
git clone <repository-url>
cd penguin-predictor
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Dependency Installation
Install the necessary libraries:
```bash
pip install streamlit pandas joblib scikit-learn
```

### 4. Executing the Application
Launch the local web server:
```bash
streamlit run app.py
```

## Performance & Scaling
The application is designed to be lightweight and can be deployed via **Streamlit Cloud**, **Heroku**, or **Docker** containers. The inference time is sub-millisecond, making it suitable for real-time demonstrations.

---
**Maintained and Developed by:** Gyanankur23

