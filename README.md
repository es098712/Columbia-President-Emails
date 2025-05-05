# Columbia President Emails: Content and Readability Analysis

This project analyzes the structure and thematic content of protest-related emails sent by Columbia University Presidents Minouche Shafik and Katrina Armstrong. Using natural language processing tools—including **Latent Dirichlet Allocation (LDA)** and **Flesch-Kincaid readability metrics**—this repository explores differences in presidential rhetoric, institutional messaging, and the clarity of administrative communications.

---

## Methodology

### 1. Data Collection
- Emails were sourced from publicly available university communications and stored in separate Excel files: one for Shafik, and one for Armstrong.
- Each row corresponds to an individual email.

---

### 2. Preprocessing
Before analysis, all emails were processed using the following steps:

- **Tokenization**: Sentences were broken into word-level tokens using NLTK's `word_tokenize`.
- **Lowercasing**: All tokens were converted to lowercase.
- **Punctuation Removal**: All punctuation characters were stripped from the text.
- **Stopword Removal**: Common English stopwords were removed using NLTK's `stopwords` list.
- **Lemmatization**: Words were reduced to their base form using `WordNetLemmatizer`, improving topic cohesion (e.g., *“students”* → *“student”*).
- **Minimum Word Length Filter**: Words with fewer than 3 characters were discarded.

---

### 3. Topic Modeling (LDA)
To uncover common themes in the emails:

- Texts were vectorized using `CountVectorizer` with frequency thresholds (`max_df=0.95`, `min_df=2`)
- A **Latent Dirichlet Allocation (LDA)** model was trained using `sklearn.decomposition.LatentDirichletAllocation`.
- **Five topics** were extracted, each defined by its top contributing words.
- Each email received a topic distribution. The **average topic proportions** were calculated per president.
- A **t-test** was performed to determine whether any topics were statistically more emphasized by one president over the other.
- Topics were labeled manually using ChatGPT (e.g., *“Student Activism and Encampments”*, *“Institutional Mission and Values”*).

---

### 4. Readability Analysis (Flesch-Kincaid)
To assess the accessibility of each president’s writing style:

- The `textstat` Python library was used to compute:
  - **Flesch Reading Ease** (0–100 scale: higher = easier to read)
  - **Flesch-Kincaid Grade Level**
  - **Average Sentence Length**
  - **Average Syllables per Word**
- These metrics were averaged for all emails sent by each president.
- Results were compared to assess overall clarity and audience accessibility.

---

## License

📄 This project is licensed under [CC BY-NC-ND 4.0](LICENSE).  
Feel free to cite, analyze, or use the material for academic and journalistic purposes. Modifications or commercial use are not permitted.
