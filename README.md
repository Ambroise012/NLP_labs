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

## Lab 2: Character Based Genereation
Goals: train a character language model (predict next char given previous characters) and experiment with different generation strategies: greedy, temperature sampling, top-k, top-p (nucleus), beam search; also compare one-hot input vs embedding.

1. Build vocabulary and mappings / Vectorize data

2. Basic LSTM model (one-hot inputs)
   - single LSTM layer that consumes one-hot vectors for each char in the input sequence 
   and predicts distribution over next character

3. Greedy generation
   - generate_next uses at each step (choose most likely char every time)
   - deterministic and tends to produce safe, repetitive text — low diversity.

4. Temperature sampling
   - T < 1 sharpens distribution → more conservative, repetitive, more “safe”.
   - T > 1 flattens distribution → more creative, but more errors/gibberish.

5. Top-k sampling
   - sample_top_k keeps only the top k candidates (highest log-prob)

6. Top-p / nucleus sampling
   - sorts probabilities descending and keeps the smallest set whose cumulative probability ≥ p
   - keeps a dynamic number of candidates depending on how “peaked” the distribution is 
   - balance of diversity and fidelity

7. Beam search
   - deterministic search that tries to maximize sequence probability
   - better global coherence than greedy argmax because it explores multiple next-char sequences and selects the highest overall probability path. 
   - But it can produce conservative text and is more expensive.

8. Embedding model
   - instead of huge one-hot vectors per position, the model learns a dense 32-dim vector per char. 
   - reduces input dimensionality and lets the network learn character relationships (e.g., digits vs letters vs punctuation).
