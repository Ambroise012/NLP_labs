# NLP_lab

## Lab 1: Textual Data Preprocessing and Visualization Lab

### Lab Overview
* Preprocess raw text data for machine learning tasks.
* Transform text into numerical features using BoW and TF-IDF.
* Apply PCA to reduce dimensionality of textual features.
* Visualize and interpret text data in reduced feature spaces.

1. **Data Loading & Cleaning**

   * Importing textual datasets
   * Basic text preprocessing (tokenization, stopword removal, stemming/lemmatization, etc.)

2. **Feature Extraction**

   * Bag-of-Words (BoW) representation
   * **TF-IDF (Term Frequency–Inverse Document Frequency)** for weighting terms based on importance

3. **Dimensionality Reduction**

   * Applying **Principal Component Analysis (PCA)** to reduce feature space
   * Visualizing reduced data in 2D/3D for better interpretation

4. **Data Visualization**

   * Frequency distributions
   * Word clouds
   * Scatter plots of embeddings or PCA projections

### Key Concepts

#### TF-IDF (Term Frequency–Inverse Document Frequency)

* **Term Frequency (TF):** Counts how often a word appears in a document.
* **Inverse Document Frequency (IDF):** Reduces the weight of frequent/common words across documents.
* **TF-IDF score:** Highlights words that are important in a specific document but not frequent across the whole corpus.

#### PCA (Principal Component Analysis)

* A **dimensionality reduction** technique that projects high-dimensional data into fewer dimensions while preserving variance as much as possible.
* Useful in textual data when working with large feature vectors (e.g., TF-IDF matrices).
* Allows **visualization of patterns** (e.g., clustering of documents) in 2D or 3D space.

---

## Lab 2:


