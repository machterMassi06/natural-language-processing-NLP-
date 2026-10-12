# Bag-of-N-Grams

## Definition

**Bag-of-N-Grams** is a text representation technique used in Natural Language Processing (NLP) to convert text into numerical vectors.

It extends the Bag-of-Words (BoW) model by representing sequences of consecutive words instead of considering only individual words.

An **N-gram** is a sequence of `n` consecutive words in a text.

## Types of N-Grams

Consider the sentence:

```text
I love natural language processing
```

| Type | N | Examples |
|---|---|---|
| Unigram | 1 | `I`, `love`, `natural` |
| Bigram | 2 | `I love`, `love natural` |
| Trigram | 3 | `I love natural`, `love natural language` |
| 4-gram | 4 | `I love natural language` |

For a sentence containing `m` words, the number of N-grams of size `n` is:

\[
N = \max(0, m-n+1)
\]

## How It Works

The Bag-of-N-Grams approach follows these steps:

1. Tokenize the text into words.
2. Extract N-grams of the desired size.
3. Build a vocabulary of unique N-grams.
4. Represent each document as a vector of N-gram frequencies.

### Example

Consider two documents:

```text
Document 1: I love machine learning
Document 2: I love deep learning
```

Using bigrams (`n = 2`), we obtain:

```text
Document 1: I love, love machine, machine learning
Document 2: I love, love deep, deep learning
```

The resulting vocabulary is:

```text
[
    "I love",
    "love machine",
    "machine learning",
    "love deep",
    "deep learning"
]
```

The documents can then be represented as frequency vectors:

| Document | I love | love machine | machine learning | love deep | deep learning |
|---|---:|---:|---:|---:|---:|
| Document 1 | 1 | 1 | 1 | 0 | 0 |
| Document 2 | 1 | 0 | 0 | 1 | 1 |

Each value represents the frequency of an N-gram in the corresponding document.


## Bag-of-Words vs. Bag-of-N-Grams

| Feature | Bag-of-Words | Bag-of-N-Grams |
|---|---|---|
| Representation | Individual words | Consecutive word sequences |
| Word order | Ignored | Partially preserved |
| Expressions | Limited representation | Can capture multi-word expressions |
| Vocabulary size | Generally smaller | Often larger |
| Complexity | Lower | Can be higher |

**Key difference:** Bag-of-Words treats words independently, whereas Bag-of-N-Grams captures local word sequences.
