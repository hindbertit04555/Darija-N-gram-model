# Darija N-gram Language Model

A probabilistic trigram language model implemented from scratch on a multi-source Moroccan Darija corpus.

This project focuses on modeling natural language using statistical methods without relying on external NLP libraries.

---

## Features

- Unigram, Bigram, and Trigram models
- Laplace (Add-1) smoothing
- Backoff strategy (Trigram → Bigram → Unigram)
- Sentence log-probability computation
- Perplexity evaluation
- Random sentence generation
- N-gram frequency visualization

---

## Project Structure
assignment3/
├── data/ # (not included in repo)
├── Darija_notebook.ipynb # main notebook
├── ngram_model_results.json # results and metrics
├── ngram_frequency_plot.png # visualization
└── README.md

---

## Dataset

The dataset is not included due to size limitations.

It contains Darija text collected from:

| Source       | Description                  |
|--------------|-----------------------------|
| Wikipedia    | Darija articles             |
| News sites   | Moroccan news content       |
| Twitter      | Informal user text          |
| Stories      | Narrative content           |
| YouTube      | Comments and discussions    |

To run the project, place your dataset inside a `data/` folder in the root directory.

---

## Methodology

### 1. Preprocessing
- Lowercasing text
- Removing URLs and special characters
- Tokenization into words

---

### 2. N-gram Modeling

We construct:

- **Unigram model:** P(w)
- **Bigram model:** P(w₂ | w₁)
- **Trigram model:** P(w₃ | w₁, w₂)

---

### 3. Laplace Smoothing

To avoid zero probabilities:
P(w) = (C(w) + 1) / (N + |V|)
P(w₂|w₁) = (C(w₁,w₂) + 1) / (C(w₁) + |V|)
P(w₃|w₁,w₂) = (C(w₁,w₂,w₃) + 1) / (C(w₁,w₂) + |V|)

---

### 4. Backoff Strategy

if trigram exists → use trigram probability
elif bigram exists → λ × bigram probability
else → λ² × unigram probability

Where λ = 0.4

---

### 5. Evaluation

#### Log Probability
Measures how likely a sentence is under the model.

#### Perplexity
PP = exp( -1/N * Σ log P(wᵢ | context) )

Lower perplexity indicates better performance.

---

## Results

- Trigram model captures more context than lower-order models
- Perplexity is relatively high due to:
  - Noisy real-world data
  - Informal Darija spelling variations
  - Large vocabulary

- The model still learns meaningful patterns and generates readable sequences

---

## Visualization

The project includes a plot showing:

- Top 20 Unigrams
- Top 20 Bigrams
- Top 20 Trigrams

Saved as:

ngram_frequency_plot.png

---

## Example Generated Sentences

- salam ana mzyan fin ghadi daba  
- wach nta katdir chi haja daba  
- ana ghadi nshouf chi film lyoum  

---

## Conclusion

The trigram model captures more contextual information compared to lower-order models.  
However, performance is limited due to the informal and inconsistent nature of Darija text.
