# 📩 SMS & Email Spam Classifier

An end-to-end Machine Learning web application that classifies SMS messages and emails as **Spam** or **Not Spam (Ham)** in real time using Natural Language Processing (NLP) and a Multinomial Naive Bayes model.

Built with **Python**, **Scikit-Learn**, **NLTK**, and **Streamlit**.

---

## 🚀 Features

- **Text Preprocessing Pipeline:**
  - Lowercasing
  - Tokenization (`nltk.word_tokenize`)
  - Alphanumeric filtering (removing special characters)
  - Stopwords and punctuation removal
  - Porter Stemming (`PorterStemmer`)
- **Feature Extraction:** TF-IDF Vectorizer with top 3,000 features.
- **Classification Model:** Multinomial Naive Bayes (high precision for text classification).
- **Interactive UI:** Clean and responsive web interface powered by Streamlit.

---

## 📁 Project Structure

```text
├── app.py                     # Streamlit web application
├── model.pkl                  # Trained Multinomial Naive Bayes model
├── vectorizer.pkl             # Trained TF-IDF Vectorizer
├── spam.csv                   # Dataset used for training and evaluation
├── sms-spam-detection.ipynb   # Jupyter Notebook with exploratory data analysis & model training
├── nltk.txt                   # NLTK dependencies for cloud deployment (stopwords, punkt)
├── requirements.txt           # Python package dependencies
└── README.md                  # Project documentation
```

---

## 🛠️ Installation & Local Setup

### 1. Clone or Navigate to the Repository
```bash
git clone <your-repository-url>
cd sms-spam-classifier-main
```

### 2. (Optional) Create and Activate a Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

> **Note:** If installing `sklearn` raises issues on newer Python versions, install via:
> ```bash
> pip install scikit-learn streamlit nltk
> ```

### 4. Download Required NLTK Data
Run Python in your terminal and download the required NLTK datasets (only needed once):
```python
import nltk
nltk.download('punkt')
nltk.download('punkt_tab')
nltk.download('stopwords')
```

### 5. Run the Streamlit App
```bash
streamlit run app.py
```
Open your browser and navigate to `http://localhost:8501`.

---

## 🧪 Example Test Cases

| Message | Expected Result |
| :--- | :--- |
| `Hey, are you free this evening to catch up over coffee?` | **Not Spam** |
| `Can you please send me the notes from today's class? Thanks!` | **Not Spam** |
| `WINNER!! As a valued network customer you have been selected to receive a £900 prize reward! Call 09061701461 to claim now.` | **Spam** |
| `URGENT! Your mobile number won a 2000 cash prize. Reply CLAIM to 87575 to receive your reward.` | **Spam** |

---

## 🌐 Cloud Deployment (Streamlit Community Cloud)

This repository is pre-configured for one-click deployment on [Streamlit Community Cloud](https://share.streamlit.io):
1. Push this repository to GitHub.
2. Log in to Streamlit Cloud and click **"New app"**.
3. Select your repository, branch, and set main file path to `app.py`.
4. Deploy! The [`nltk.txt`](nltk.txt) file automatically installs required NLTK corpora during the build process.

---

## 🧰 Tech Stack

- **Frontend:** [Streamlit](https://streamlit.io/)
- **Machine Learning:** [Scikit-Learn](https://scikit-learn.org/) (MultinomialNB, TfidfVectorizer)
- **Natural Language Processing:** [NLTK](https://www.nltk.org/)
- **Data Analysis:** Pandas, NumPy
