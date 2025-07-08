# Car Rental Feedback Analyzer (Watson AI) 🚗

A **Streamlit** web app that uses **IBM Watson Natural Language Understanding (NLU)** to analyze customer reviews, detect overall sentiment, and highlight common issues.

## 📂 Project Structure

```text
car_rental_feedback_analyzer/
├── app.py                     # Main Streamlit application
├── requirements.txt           # Python dependencies
├── README.md                  # This file
└── .streamlit/
    └── secrets_template.toml  # Rename to secrets.toml & add Watson creds
```

## 🔧 Prerequisites

1. **Python 3.9+** installed
2. An **IBM Cloud** account  
3. A **Natural Language Understanding** service instance  
4. Your service **API key** and **URL**

## ⚙️ Setup

```bash
# Clone / unzip the project
cd car_rental_feedback_analyzer_watson.ai

# Create a virtual environment (optional but recommended)
python -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Configure Watson Credentials

Rename the secrets template and paste your credentials:

```bash
mv .streamlit/secrets_template.toml .streamlit/secrets.toml
```

Edit `.streamlit/secrets.toml`:

```toml
[default]
WATSON_API_KEY   = "xxxxxxxxxxxxxxxxxxxxxxxxxxxx"
WATSON_SERVICE_URL = "https://api.us-south.natural-language-understanding.watson.cloud.ibm.com/instances/xxxxx"
```

> **Tip:** You can find the key & URL in **IBM Cloud Console** → your NLU service → **Manage** → *API Keys & Endpoints*. citeturn0search3

## 🚀 Run the App

```bash
streamlit run app.py
```

Open the local URL shown in your terminal (default: `http://localhost:8501`).  
Upload a CSV (`review`, optional `rating`) **or** tick *Use demo data* to test.

## 📝 Using Watsonx.ai Studio (Optional)

If you prefer IBM **watsonx.ai** Studio:

1. Create / open a project in **watsonx.ai**.  
2. Add a *Python* environment & copy the repo files.  
3. Add the **Natural Language Understanding** service to your project (Services → *Add service instance*).  
4. In *Manage* → *Service credentials*, copy API Key & URL and export them as env variables or keep them in `secrets.toml`.  
5. From a *Terminal* in watsonx.ai, run:

```bash
pip install -r requirements.txt
streamlit run --server.port 8080 app.py
```

Expose port **8080** via the *Expose App* button to access the UI.

---

Made with ❤️ & IBM Watson.
