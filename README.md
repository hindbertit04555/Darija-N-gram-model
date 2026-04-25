# Darija N-gram Language Model

This project implements a probabilistic N-gram language model for Moroccan Darija using a corpus collected from multiple online sources.

## Project Overview

The goal of this project is to build and evaluate a language model that can:

- Learn patterns from Darija text
- Estimate sentence probabilities
- Generate new sentences
- Compare different N-gram models

## Methodology

### 1. Data Processing
- The dataset contains Darija text from various sources
- Text is cleaned by removing URLs, special characters, and noise
- Tokenization is applied to split text into words

### 2. Language Models
We implemented:
- **Unigram Model** (n = 1)
- **Bigram Model** (n = 2)
- **Trigram Model** (n = 3)

### 3. Smoothing & Backoff
- Laplace (Add-1) smoothing is used to handle unseen words
- Backoff strategy:
  - Trigram → Bigram → Unigram

### 4. Evaluation
The model is evaluated using:
- Log probability of sentences
- Perplexity on test data

## Results

- The trigram model performs better than unigram and bigram models
- Perplexity remains high due to:
  - Noisy and informal nature of Darija text
  - Data sparsity
- The model successfully captures common word patterns

## Visualization

The project includes a visualization of:
- Top 20 most frequent unigrams, bigrams, and trigrams

Saved as:
- `ngram_frequency_plot.png`

## Example Output

Generated sentences from the model:

- salam ana mzyan fin ghadi daba  
- wach nta katdir chi haja daba  

## Files in Repository

- `Darija_notebook.ipynb` → Main notebook
- `ngram_model_results.json` → Model evaluation results
- `ngram_frequency_plot.png` → Frequency visualization
- `README.md` → Project description

## Conclusion

The trigram model captures more contextual information compared to lower-order models.  
However, performance is limited due to the informal and inconsistent nature of Darija text.

