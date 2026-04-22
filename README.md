# fikl3course — NLP Homework: Sentiment Analysis & POS Tagging

Jupyter notebooks for a university computational linguistics course, focused on sentiment analysis of hotel reviews and POS-tagging comparison on a Russian social media corpus.

## Notebooks

### [HW1 — Sentiment Analysis of Hotel Reviews](hw1_sentiment_analysis_hotel_reviews.ipynb)
Scrapes Russian hotel reviews from 101hotels.com and classifies them as positive or negative using a rule-based approach.
- Web scraping with BeautifulSoup (positive/negative review sections)
- Class balancing and dataset construction
- Text preprocessing and tokenization
- Three classification approaches:
  1. Unique unigram word sets (intersection removal + frequency filtering)
  2. Bigram-based classification
  3. Bag-of-words + k-NN with Euclidean distance

**Libraries:** `requests`, `beautifulsoup4`, `nltk`, `sklearn`, `numpy`, `pandas`

---

### [HW1 Improved — Chunker-Based Bigram Extraction](hw1_improved_chunker_bigrams.ipynb)
Extension of HW1 adding Natasha-based chunker for morphologically-aware bigram extraction.
- Chunker extracting patterns: `ADV+ADJ`, `ADJ+NOUN`, `не+VERB`
- Bigrams appended to the unigram word set
- Accuracy improved from 0.84 → 0.87 on test set

**Libraries:** `natasha`, `pymorphy2`, `sklearn`

---

### [HW2 — POS Tagging Comparison](hw2_pos_tagging_comparison.ipynb)
Compares three Russian POS-taggers against a manually annotated gold standard using a mini-corpus of HSE dormitory community posts.
- Corpus: informal student posts with local slang, abbreviations, and colloquialisms
- Manual gold standard annotation using Universal Dependencies tagset (ru_syntagrus)
- Taggers evaluated: pymorphy2, Natasha, spaCy
- Token alignment algorithm to handle different tokenization strategies
- Natasha achieved the best accuracy; results used to motivate chunker choice in HW1 Improved

**Libraries:** `pymorphy2`, `natasha`, `spacy`, `pandas`, `sklearn`

---

## Data Files

| File | Description |
|------|-------------|
| `corpus_hse_dormitory.txt` | Mini-corpus: Russian social media posts from HSE Dubki dormitory community |
| `hotel_reviews_dataset.csv` | Hotel review dataset with sentiment labels (0 = negative, 1 = positive) |
| `gold_pos_tags.csv` | Manually annotated gold standard POS tags (337 tokens, UD tagset) |
| `pos_tagging_results.csv` | POS-tagger comparison results across pymorphy2, Natasha, spaCy |

---

## Requirements

```
requests
beautifulsoup4
nltk
scikit-learn
numpy
pandas
pymorphy2
natasha
spacy
```
