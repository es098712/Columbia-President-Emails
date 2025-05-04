
# Columbia-President-Emails

This project analyzes the content, tone, and thematic structure of official protest-related emails sent by Columbia University Presidents Minouche Shafik and Katrina Armstrong. Using natural language processing techniques—including LDA topic modeling and Flesch-Kincaid readability scoring—the repository explores the readability of our most recent presidential communications, and how they reflect administrative priorities.

## Methodology

### 1. Data Collection
- Protest-related emails were collected from official university communications and loaded from Excel files for each president.

### 2. Preprocessing
- All emails were converted to lowercase.
- Punctuation was removed.
- Words with fewer than 3 characters were filtered out.
- The resulting clean text corpus was used for both topic modeling and readability analysis.

### 3. Topic Modeling (LDA)
- Emails were vectorized using `CountVectorizer` with stopword removal and frequency thresholds (`max_df=0.95`, `min_df=2`).
- A Latent Dirichlet Allocation (LDA) model was applied using `sklearn.decomposition.LatentDirichletAllocation`.
- Five topics were extracted based on co-occurring terms.
- Each email was assigned a topic distribution, and average topic proportions were calculated for each president.
- Visualizations compare topic prevalence across Shafik and Armstrong's emails.

### 4. Readability Analysis
- The `textstat` library was used to compute:
  - Flesch Reading Ease Score (0–100)
  - Flesch-Kincaid Grade Level
  - Average sentence length
  - Average syllables per word
- These metrics were averaged across all emails for each president.

### 5. Visualization
- Matplotlib was used to plot topic distributions and readability metrics.
- Side-by-side bar graphs and statistical comparisons were used to highlight rhetorical trends and complexity in presidential communications.

## License
This project is for academic and journalistic use. Please cite the repository if using the data or analysis for publication.
