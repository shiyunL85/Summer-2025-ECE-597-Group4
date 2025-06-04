# Phishing Email Analysis Project

This project is a **comprehensive forensic and behavioral analysis** of phishing emails. It uses a rich set of natural language processing, statistical, and machine learning techniques to find patterns in phishing content, identify technical tactics, linguistic signatures, and emotional cues that are commonly used in such attacks.

---

## Dataset

- **Primary dataset**: `CaptstoneProjectData_2025.csv` — Raw phishing email data (subject, body).
- **Generated datasets**:
  - `phishing_analyzed_dataset.csv` — Processed data with features.
  - `signature_matrix.csv` — Feature summary across the dataset.

---

## Objectives

- Analyze the structure and language used in phishing emails.
- Quantify urgency and emotion-based manipulation tactics.
- Extract linguistic and technical signatures used in malicious messages.
- Provide clustering and statistical summaries for campaign detection.

---

##  Technologies Used

- Python
- Pandas, NumPy
- NLTK
- Seaborn, Matplotlib
- Scikit-learn
- TextStat
- WordCloud
- Regex, Re
- TfidfVectorizer
- KMeans Clustering

---

## Key Analyses

### 1. **Initial Cleaning & Stats**
- Removed null rows
- Parsed character and word lengths
- Visualized distribution of body lengths and word counts

### 2. **Linguistic Feature Extraction**
- Tokenization with NLTK
- Removed stopwords and punctuation
- Counted top subject/body words
- Tagged parts of speech and extracted top:
  - Verbs (e.g., update, verify)
  - Nouns (e.g., account, message)
  - Adjectives (e.g., urgent, limited)

### 3. **Urgency and Emotion Analysis**
- Urgency score based on high-pressure terms like "urgent", "suspended"
- Emotion density: proportion of emotionally manipulative words
- Flesch Reading Ease and Gunning Fog readability scores

### 4. **Technical Tactics Identification**
- Detection of:
  - Base64 encoding
  - Suspicious attachments (`.exe`, `.zip`, etc.)
  - IP-based links
  - Free hosting usage (e.g., wixsite.com)
  - Shortened URLs (bit.ly, tinyurl)
- Count of HTML tags (anchor, script, form, etc.)

### 5. **Phishing Signature Construction**
- Created a signature matrix with percentage of emails using specific deceptive traits
- Saved matrix as `signature_matrix.csv`

### 6. **Textual Structure**
- Link extraction and count
- Entropy computation (Shannon entropy)
- Greeting type detection: Generic, Personalized, None
- Passive voice detection via regex
- Image-only emails flagged

### 7. **Bigrams & Trigrams**
- Identified most frequent 2-word and 3-word phrases in phishing messages

### 8. **Clustering**
- TF-IDF vectorization of subject lines
- Cosine similarity matrix (heatmap of top 25)
- KMeans clustering for subject classification (campaign detection)

---

## Files and Outputs

| File Name                        | Description                                           |
|----------------------------------|-------------------------------------------------------|
| `CaptstoneProjectData_2025.csv` | Original raw dataset of phishing emails (deleted for security purposes)             |
| `phishing_analyzed_dataset.csv` | Final dataset with all computed features (deleted for security purposes)            |
| `signature_matrix.csv`          | Summary matrix of deceptive traits by percentage     |
| `Final dataset analysis.ipynb`  | Jupyter Notebook with full step-by-step processing   |
| `README.md`                     | Project documentation                                |

---

## Example Insights

- **Most common verbs**: click, update, confirm
- **Most frequent themes**: urgency, reward, threat
- **41% of messages** use passive voice - likely for deflection
- **13% of emails** contain suspicious attachments
- **6.6% of messages** use shortened URLs
- **Reward words** found in ~14% of samples
- **Threat language** found in ~11% of samples

---

## How to Run

1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd <your-repo-folder>
   ```

2. Install requirements:
   ```bash
   pip install -r requirements.txt
   ```

3. Open the notebook and run:
   ```bash
   jupyter notebook "Final dataset analysis.ipynb"
   ```

> The notebook processes the dataset, extracts features, generates charts, and saves final `.csv` outputs.

---

## License

**MIT License** – © 2025 Alpar Arman

Feel free to use, modify, and distribute – a citation or star is always appreciated!
This project is intended for educational and research purposes only.
