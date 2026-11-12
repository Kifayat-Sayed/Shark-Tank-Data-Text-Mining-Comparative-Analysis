# Shark Tank Data – Exploratory Text Mining & Comparative Analysis

### An NLP-Based Investigation of Business Descriptions and Investment Deal Outcomes

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/NLP-Text%20Mining-orange" alt="NLP"/>
  <img src="https://img.shields.io/badge/Analysis-Exploratory%20Data%20Analysis-green" alt="EDA"/>
  <img src="https://img.shields.io/badge/Visualization-WordCloud-purple" alt="WordCloud"/>
  <img src="https://img.shields.io/badge/Status-Completed-success" alt="Status"/>
</p>

## 1. Project Overview

How do entrepreneurs describe their businesses, and can differences in their language be observed between businesses that successfully secure investment and those that do not?

This project explores that question using **Natural Language Processing (NLP) and exploratory text-mining techniques** applied to the Shark Tank Companies Dataset.

The analysis examines 495 entrepreneur records and focuses on the textual descriptions of their businesses. The descriptions are separated into two groups according to their recorded investment outcomes:

- **Deal:** Businesses that successfully secured an investment deal.
- **No Deal:** Businesses that did not secure an investment deal.

Using Python and NLTK, the textual descriptions are cleaned and processed through lowercasing, stop-word removal, punctuation removal, and lemmatization. The resulting corpora are examined through word-frequency analysis and separate word-cloud visualisations.

The project identifies frequently occurring vocabulary, compares common and distinctive terms across both groups, and investigates the appearance of device-related terminology in unsuccessful deal descriptions.

The objective is to demonstrate how unstructured business information can be transformed into interpretable textual patterns using fundamental NLP techniques.

> **Project focus:** Exploratory text mining and comparative vocabulary analysis. This is a descriptive NLP project, not a trained investment-outcome prediction model.

---

## 2. Business Problem

Entrepreneurs appearing on Shark Tank communicate their business concepts through descriptions of their products, services, target customers, and intended value propositions.

These descriptions contain unstructured textual information that can be explored to understand recurring terminology and differences in how businesses communicate their offerings.

However, comparing raw descriptions directly is difficult because they contain inconsistent capitalisation, punctuation, common words, and variations of the same term.

The business problem addressed in this project is:

**Can text-mining techniques identify differences in the vocabulary patterns of business descriptions associated with successful and unsuccessful investment outcomes?**

The investigation focuses on identifying:

- Frequently occurring words in successful business descriptions.
- Frequently occurring words in unsuccessful business descriptions.
- Shared vocabulary across both groups.
- Terms that are more prominent in one group.
- Potential patterns involving device-related terminology.

The findings provide exploratory insights into the language used to describe businesses. They do not establish the actual factors responsible for investor decisions.

---

## 3. Project Objectives

The key objectives of this project are:

1. Explore and understand the Shark Tank Companies Dataset.
2. Select relevant variables for comparative textual analysis.
3. Separate business descriptions according to investment deal outcomes.
4. Apply NLP preprocessing techniques to standardise textual data.
5. Calculate aggregate word and character counts for both corpora.
6. Identify the most frequently occurring words in each group.
7. Generate word clouds to visualise vocabulary distributions.
8. Compare common and distinctive terminology across the two groups.
9. Investigate the occurrence of device-related terminology.
10. Interpret findings while recognising the limitations of frequency-based text analysis.

---

## 4. Dataset Description

The project uses the **Shark Tank Companies Dataset**, containing information about 495 entrepreneur and business pitch records.

Each record includes business-related information, textual descriptions, investment details, episode information, and associated investor details.

The original dataset contains structured and unstructured variables. For this analysis, two attributes are selected:

| Variable | Description | Role |
|---|---|---|
| `deal` | Indicates whether the entrepreneur secured an investment deal. | Grouping variable |
| `description` | Textual description of the entrepreneur's business, product, or service. | NLP input |

### Dataset Characteristics

| Attribute | Details |
|---|---|
| Dataset | Shark Tank Companies Dataset |
| Total records | 495 |
| Observation unit | Entrepreneur/business pitch record |
| Data type | Structured and unstructured |
| Target/grouping variable | `deal` |
| Primary text variable | `description` |
| Analysis type | Exploratory text mining |
| Main objective | Comparative vocabulary analysis |

### Data Dictionary

The following attributes are present in the dataset:

| Column | Description |
|---|---|
| `deal` | Indicates whether the entrepreneur secured a deal. |
| `description` | Description of the business, product, or service. |
| `episode` | Episode number associated with the pitch. |
| `category` | Business or industry category. |
| `entrepreneurs` | Name or names of the entrepreneur(s). |
| `location` | Location associated with the entrepreneur or business. |
| `website` | Business website, where available. |
| `askedFor` | Investment amount requested. |
| `exchangeForStake` | Equity percentage offered in exchange for investment. |
| `valuation` | Implied business valuation. |
| `season` | Shark Tank season number. |
| `shark1`–`shark5` | Shark names associated with the episode. |
| `title` | Business or product pitch title. |
| `episode-season` | Combined episode and season identifier. |
| `Multiple Entreprenuers` | Indicates whether multiple entrepreneurs are involved. |

Only `deal` and `description` are used in the current text-mining workflow. The other attributes provide additional contextual information but are not incorporated into the analysis.

---

## 5. Technology Stack

| Technology | Application |
|---|---|
| **Python** | Primary programming language |
| **Pandas** | Dataset loading, selection, and manipulation |
| **NumPy** | Numerical and array operations |
| **NLTK** | Natural Language Processing |
| **NLTK Stopwords** | Removal of common English stop words |
| **WordNetLemmatizer** | Text lemmatization |
| **Regular Expressions** | Punctuation and character cleaning |
| **Matplotlib** | Data visualisation |
| **Seaborn** | Statistical visualisation support |
| **WordCloud** | Word-cloud generation |

---

## 6. Methodology and Analytical Workflow

The project follows a structured text-mining workflow.

### Step 1 – Data Loading and Selection

The dataset is imported using Pandas.

The `deal` and `description` columns are extracted to create a focused analytical dataset.

### Step 2 – Corpus Separation

The selected descriptions are divided into two independent corpora.

**Deal Corpus**

Contains business descriptions for which `deal = True`.

**No-Deal Corpus**

Contains business descriptions for which `deal = False`.

This separation enables independent analysis and comparison of the two groups.

### Step 3 – Text Preprocessing

The raw descriptions undergo several preprocessing operations.

| Technique | Implementation | Purpose |
|---|---|---|
| Lowercasing | Python string processing | Standardise capitalisation |
| Stop-word removal | NLTK English stop words | Remove common words |
| Custom stop-word removal | Additional predefined words | Reduce irrelevant vocabulary |
| Punctuation removal | Regular expressions | Remove punctuation and non-alphabetic characters |
| Lemmatization | WordNetLemmatizer | Reduce supported word forms to base forms |

The additional custom stop words used are:

`also`, `made`, `makes`, `make`, `like`, `this`, `even`, `company`.

The regular-expression cleaning operation removes characters outside lowercase English letters and whitespace.

### Step 4 – Text Volume Analysis

The total word count and non-whitespace character count are calculated independently for both corpora.

This provides an initial understanding of the aggregate volume of textual information available for comparison.

### Step 5 – Word-Frequency Analysis

The cleaned text is used to calculate word-frequency distributions.

The ten most frequently occurring terms are identified independently for the deal and no-deal corpora.

### Step 6 – Word-Cloud Visualisation

Separate word clouds are generated to represent the vocabulary distributions of both groups.

Larger words represent higher frequencies within the corresponding corpus.

### Step 7 – Comparative Analysis

The frequency tables and word clouds are examined to identify:

- Shared vocabulary.
- Distinctive terminology.
- Differences in frequently occurring terms.
- Potential patterns requiring further statistical investigation.

### Workflow Summary

```text
             Shark Tank Dataset
                      |
                      v
          Select Deal and Description
                      |
                      v
              Corpus Separation
                 /         \
                /           \
          Deal Corpus    No-Deal Corpus
                \           /
                 \         /
                      v
              Text Preprocessing
                      |
          ---------------------------
          |            |            |
       Lowercase   Stop Words   Punctuation
          |            |            |
          ---------------------------
                      |
                      v
                 Lemmatization
                      |
                      v
              Frequency Analysis
                      |
             ------------------
             |                |
          Deal Word       No-Deal Word
          Frequencies     Frequencies
             |                |
             ------------------
                      |
                      v
               Word Clouds
                      |
                      v
           Comparative Interpretation
                      |
                      v
               Key Observations
```

---

## 7. Text Preprocessing Details

Text preprocessing is essential for reducing inconsistencies in raw descriptions and preparing the data for meaningful vocabulary analysis.

### 7.1 Lowercasing

All descriptions are converted into lowercase.

For example:

```text
Product
PRODUCT
product
```

are standardised as:

```text
product
```

### 7.2 Stop-Word Removal

Common English stop words are removed using the NLTK stop-word collection.

Additional custom stop words are included to reduce terms that are considered less useful for this particular comparison.

### 7.3 Punctuation Removal

Regular expressions are used to remove punctuation and non-alphabetic characters.

This helps standardise textual tokens before frequency calculations.

### 7.4 Lemmatization

WordNetLemmatizer is applied to reduce certain words to their dictionary base forms.

The current implementation uses its default noun-based behaviour rather than explicit part-of-speech-aware lemmatization.

### 7.5 Final Corpus

After preprocessing, the cleaned descriptions are used for word counting, frequency calculations, and word-cloud generation.

---

## 8. Results and Key Findings

The following results are obtained from the executed notebook.

### 8.1 Aggregate Text Volume

| Metric | Deal Corpus | No-Deal Corpus |
|---|---:|---:|
| Total words | **10,399** | **7,727** |
| Non-whitespace characters | **53,910** | **39,697** |

**Observations:**

- The deal corpus contains 10,399 words.
- The no-deal corpus contains 7,727 words.
- The deal corpus has a greater aggregate volume of textual information.
- The same pattern is observed in the non-whitespace character counts.

These values represent aggregate corpus totals, not average description lengths. They do not independently establish that successful businesses have longer descriptions.

### 8.2 Top 10 Words – Deal Corpus

The following table presents the most frequently occurring words in business descriptions associated with successful investment outcomes.

| Rank | Word | Frequency |
|---:|---|---:|
| 1 | product | **34** |
| 2 | design | **22** |
| 3 | line | **20** |
| 4 | child | **20** |
| 5 | designed | **19** |
| 6 | way | **18** |
| 7 | easy | **18** |
| 8 | keep | **18** |
| 9 | without | **18** |
| 10 | offer | **18** |

**Key observations:**

- `product` is the most frequently occurring word, with 34 occurrences.
- `design` ranks second, with 22 occurrences.
- `line` and `child` both occur 20 times.
- Terms such as `designed`, `easy`, and `offer` also appear prominently.

The results indicate that product-related and design-related terminology is prominent in the deal corpus.

### 8.3 Top 10 Words – No-Deal Corpus

The following table presents the most frequently occurring words in business descriptions associated with unsuccessful investment outcomes.

| Rank | Word | Frequency |
|---:|---|---:|
| 1 | product | **28** |
| 2 | help | **20** |
| 3 | device | **17** |
| 4 | water | **17** |
| 5 | use | **17** |
| 6 | system | **16** |
| 7 | service | **16** |
| 8 | designed | **15** |
| 9 | online | **15** |
| 10 | without | **14** |

**Key observations:**

- `product` is again the most frequently occurring word, with 28 occurrences.
- `help` ranks second, with 20 occurrences.
- `device`, `water`, and `use` each occur 17 times.
- `system` and `service` occur 16 times each.

The no-deal corpus prominently features terminology related to products, devices, systems, and services.

### 8.4 Comparative Vocabulary Analysis

The following table compares selected words appearing in the top-ten frequency lists of both groups.

| Word | Deal Frequency | No-Deal Frequency |
|---|---:|---:|
| product | 34 | 28 |
| designed | 19 | 15 |
| without | 18 | 14 |

**Shared vocabulary:**

The term `product` is the most frequent word in both corpora. The words `designed` and `without` also appear among the top-ten terms of both groups.

This indicates that certain descriptive terms are common across both successful and unsuccessful business descriptions.

**Distinctive vocabulary:**

| Deal Corpus | No-Deal Corpus |
|---|---|
| design | help |
| line | device |
| child | water |
| way | use |
| easy | system |
| keep | service |
| offer | online |

These differences illustrate variation in the frequently occurring vocabulary across the two groups.

### 8.5 Word-Cloud Analysis

Two separate word clouds are generated from the cleaned textual corpora.

**Deal Corpus Word Cloud**

The prominent terms include:

- Product
- Design
- Line
- Child
- Designed
- Way
- Easy
- Keep
- Without
- Offer

**No-Deal Corpus Word Cloud**

The prominent terms include:

- Product
- Help
- Device
- Water
- Use
- System
- Service
- Designed
- Online
- Without

The visualisations provide a compact representation of the vocabulary patterns identified through word-frequency analysis.

They also help communicate shared and distinctive terminology across the two groups.

> **Visual interpretation:** Word size represents frequency within each corpus. It does not represent statistical significance, business importance, or the probability of securing investment.

### 8.6 Device-Related Terminology Investigation

One of the exploratory questions concerns whether device-related terminology is more prominent among businesses that did not secure investment.

The analysis identifies the following:

| Corpus | Frequency of `device` | Top-Ten Status |
|---|---:|---|
| Deal | Not in top ten | Not listed |
| No Deal | **17** | Included |

**Observation:**

The term `device` appears 17 times in the no-deal corpus and is among its ten most frequently occurring words. It does not appear among the ten most frequent words in the deal corpus.

This provides an interesting direction for further investigation.

However, this finding must be interpreted carefully. Word occurrences are not equivalent to the number of businesses classified as device-related.

A business may mention the word multiple times, while another device-related business may use different terminology.

Additionally, the corpora contain different total word counts, making direct comparisons of raw frequencies potentially misleading.

**Conclusion:** The current analysis identifies a vocabulary pattern but does not establish that device-related businesses are less likely to secure investment.

A business-level classification, comparison of deal rates, contingency-table analysis, and statistical testing would be required to investigate that hypothesis properly.

---

## 9. Consolidated Findings

The major findings of the project can be summarised as follows:

| Area | Finding |
|---|---|
| Dataset | 495 entrepreneur records |
| Deal corpus | 10,399 words |
| No-deal corpus | 7,727 words |
| Deal corpus character count | 53,910 non-whitespace characters |
| No-deal corpus character count | 39,697 non-whitespace characters |
| Most frequent deal-corpus term | `product` – 34 occurrences |
| Most frequent no-deal-corpus term | `product` – 28 occurrences |
| Shared vocabulary | `product`, `designed`, `without` |
| Distinctive deal vocabulary | `design`, `line`, `child`, `easy` |
| Distinctive no-deal vocabulary | `help`, `device`, `water`, `system` |
| Device-related observation | `device` appears 17 times in the no-deal corpus and is not in the deal corpus's top ten |

### Overall Analytical Outcome

The analysis successfully demonstrates how basic NLP techniques can be used to extract and compare vocabulary patterns from unstructured business descriptions.

The results reveal both shared and distinctive terminology across the two deal-outcome groups, providing a foundation for further business-oriented text analysis.

---

## 10. Limitations

The results should be interpreted within the limitations of the current methodology.

### 10.1 Dataset Size

The analysis uses 495 records, which limits the extent to which findings can be generalised.

### 10.2 Description-Based Analysis

The project analyses business descriptions rather than complete pitch transcripts or investor discussions. Consequently, it cannot capture all the information that may influence investment decisions.

### 10.3 Raw Word Frequencies

Raw frequencies are affected by differences in corpus size. Normalised frequencies per 1,000 words would provide a more suitable basis for comparison.

### 10.4 Lack of Contextual Analysis

The current approach analyses individual word occurrences and does not fully capture sentence meaning or semantic relationships.

### 10.5 Stop-Word Removal

The removal of terms such as `not` and `no` may eliminate important contextual information, particularly for future sentiment-analysis tasks.

### 10.6 Basic Lemmatization

The current implementation uses default noun-based lemmatization rather than explicit part-of-speech-aware processing.

### 10.7 No Statistical Validation

The analysis does not perform inferential statistical testing. The observed vocabulary differences should therefore not be interpreted as statistically significant relationships.

### 10.8 No Predictive Model

No machine-learning model is trained to predict investment outcomes. The project is exploratory rather than predictive.

---

## 11. Conclusion

This project applies exploratory text mining and Natural Language Processing to the Shark Tank Companies Dataset to investigate vocabulary patterns associated with successful and unsuccessful investment outcomes.

By selecting the `deal` and `description` variables, the dataset is divided into two independent corpora and processed through lowercasing, stop-word removal, punctuation cleaning, and WordNet lemmatization.

The resulting frequency distributions reveal that `product` is the most frequently occurring term in both groups. The deal corpus prominently features terms such as `design`, `line`, and `child`, whereas the no-deal corpus includes terms such as `help`, `device`, `water`, and `system`.

Separate word-cloud visualisations provide an intuitive comparison of these vocabulary patterns.

The investigation of device-related terminology identifies a higher prominence of the term `device` in the no-deal corpus's top-ten vocabulary. However, this observation requires further business-level classification and statistical validation before any broader conclusion can be established.

Overall, the project demonstrates the practical application of fundamental NLP techniques in transforming unstructured textual information into interpretable patterns.

It also highlights the importance of distinguishing descriptive findings from statistically validated associations and causal explanations.

---

## 12. Key Learnings

### Technical Skills

- Dataset manipulation using Pandas.
- Text extraction and corpus separation.
- NLP preprocessing using NLTK.
- Lowercasing and stop-word removal.
- Regular-expression-based text cleaning.
- WordNet lemmatization.
- Word-frequency calculations.
- Word-cloud generation.
- Exploratory visualisation using Python.

### Analytical Skills

- Working with unstructured textual data.
- Comparing vocabulary across different outcome groups.
- Interpreting frequency distributions.
- Identifying shared and distinctive terminology.
- Understanding the limitations of raw word-frequency comparisons.
- Distinguishing exploratory observations from statistical conclusions.

---

## 13. Future Scope and Improvements

The current implementation provides a foundation for several more advanced NLP and business analytics applications.

| Enhancement | Proposed Approach | Expected Benefit |
|---|---|---|
| Normalised word frequencies | Frequency per 1,000 words | Fairer comparison between corpora |
| N-gram analysis | Bigrams and trigrams | Identification of meaningful word combinations |
| TF-IDF | Term Frequency–Inverse Document Frequency | Identification of distinctive terms |
| Sentiment analysis | NLP sentiment techniques | Exploration of evaluative language |
| Topic modelling | Latent Dirichlet Allocation (LDA) | Discovery of underlying business themes |
| Statistical validation | Chi-square / Fisher's exact test | Investigation of vocabulary-related associations |
| Predictive text classification | Logistic Regression, Naive Bayes, SVM | Exploration of deal-outcome prediction |
| Interactive dashboard | Streamlit / Power BI | Interactive exploration of results |

### Potential Predictive Modelling Extension

A future version could use TF-IDF features and machine-learning algorithms such as:

- Logistic Regression
- Multinomial Naive Bayes
- Support Vector Machine (SVM)

The objective would be to investigate whether textual descriptions contain useful information for distinguishing deal outcomes.

Given the relatively small dataset, appropriate cross-validation, baseline comparisons, and leakage prevention would be essential.

---

## 14. Repository Structure

The recommended repository structure is:

```text
Shark-Tank-Text-Mining/
│
├── SharkTankData-TextMining.ipynb
│
├── SharkTankCompanies.csv
│
├── README.md
│
└── requirements.txt
```

**Note:** The CSV dataset is expected by the notebook but should only be included in the repository if its redistribution is permitted. If it is not included, provide the appropriate dataset access instructions.

---

## 15. Installation and Execution

### Prerequisites

- Python 3.x
- Jupyter Notebook or JupyterLab
- pip package manager

### Step 1 – Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/Shark-Tank-Text-Mining.git

cd Shark-Tank-Text-Mining
```

Replace `YOUR-USERNAME` with the relevant GitHub username.

### Step 2 – Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn nltk wordcloud jupyter
```

### Step 3 – Download Required NLTK Resources

Run the following in Python:

```python
import nltk

nltk.download('stopwords')
nltk.download('wordnet')
nltk.download('omw-1.4')
nltk.download('punkt')
```

### Step 4 – Place the Dataset

Ensure that `SharkTankCompanies.csv` is available in the notebook's working directory.

### Step 5 – Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
SharkTankData-TextMining.ipynb
```

Execute the notebook cells sequentially to reproduce the preprocessing, word-frequency analysis, and visualisations.

---

## 16. Acknowledgements and Attribution

The project uses the Shark Tank Companies Dataset and builds upon the original notebook material.

**Original notebook author:** Sudhanshu Singh.

The original source material is acknowledged as the foundation of this exercise. Any subsequent code modifications, additional analysis, interpretations, and documentation should be attributed accurately.

### References and Documentation

- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [NumPy Documentation](https://numpy.org/doc/)
- [NLTK Documentation](https://www.nltk.org/)
- [WordCloud Documentation](https://amueller.github.io/word_cloud/)
- [Matplotlib Documentation](https://matplotlib.org/stable/)
- [Seaborn Documentation](https://seaborn.pydata.org/)

---

## 17. Project Summary

| Category | Details |
|---|---|
| Project | Shark Tank Data – Exploratory Text Mining |
| Domain | NLP and Business Analytics |
| Dataset size | 495 records |
| Main input | Business descriptions |
| Grouping variable | Investment deal outcome |
| Core techniques | Text preprocessing, lemmatization, frequency analysis |
| Visualisation | Comparative word clouds |
| Main output | Comparative vocabulary patterns |
| Predictive modelling | Not implemented |
| Statistical hypothesis testing | Not implemented |

**Final Takeaway**

This project demonstrates how Python-based text mining can be applied to real-world business descriptions to identify recurring vocabulary, compare textual patterns, and extract exploratory insights.

It establishes a practical foundation for extending basic NLP analysis into more advanced applications involving semantic analysis, statistical validation, topic discovery, and predictive modelling.

---

<p align="center">
  <b>Exploring the language behind business ideas, one description at a time.</b>
</p>
