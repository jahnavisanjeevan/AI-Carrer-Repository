# AI-Carrer-Repository
# AI-Powered Career Advisor System

## Objective
An intelligent system that helps students make informed career choices based on their academic background, skills, and interests using machine learning.

## Features
- Predict suitable career paths
- Recommend skills and learning platforms
- Analyze real-time job market trends

## Tech Stack
- Python, Flask
- Scikit-learn, Pandas, NumPy
- OpenAI API (for recommendation)
- BeautifulSoup (job scraping)

## How to Run
```bash
pip install -r requirements.txt
python app.py

---

### ✅ 2. `app.py` (Simple Flask App)
```python
from flask import Flask, request, render_template
import pickle

app = Flask(__name__)
model = pickle.load(open('model.pkl', 'rb'))

@app.route('/')
def home():
    return "<h2>AI Career Advisor is Running</h2>"

@app.route('/predict', methods=['POST'])
def predict():
    data = request.form.get('skills')
    prediction = model.predict([data])
    return f"Recommended Career: {prediction[0]}"

if __name__ == "__main__":
    app.run(debug=True)



