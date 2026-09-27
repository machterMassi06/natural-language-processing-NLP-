# Bag of Words (BoW)

## Introduction

Bag of Words (BoW) is one of the simplest and most widely used text representation methods in Natural Language Processing (NLP). It transforms text into a numerical vector by counting how many times each word appears in a document.

The name comes from the idea that the order of words is ignored: we only keep the presence and frequency of terms, not their sequence in the sentence.

---

## Main idea

A document is represented as a vector whose length equals the size of the vocabulary of the corpus.

For example, consider these two sentences:

- Document 1: "I love NLP and I love machine learning"
- Document 2: "NLP is useful for machine learning"

The vocabulary is:

- I
- love
- NLP
- and
- machine
- learning
- is
- useful
- for

The Bag of Words representation is then built by counting occurrences of each term in each document.

### Example

| Word | Doc 1 | Doc 2 |
|------|-------|-------|
| I    | 2     | 0     |
| love | 2     | 0     |
| NLP  | 1     | 1     |
| and  | 1     | 0     |
| machine | 1   | 1     |
| learning | 1  | 1     |
| is   | 0     | 1     |
| useful | 0    | 1     |
| for  | 0     | 1     |

So the document vectors become:

- Doc 1: [2, 2, 1, 1, 1, 1, 0, 0, 0]
- Doc 2: [0, 0, 1, 0, 1, 1, 1, 1, 1]

---
## Advantages

- simple and easy to implement
- works well with classical machine learning algorithms
- interpretable: each feature corresponds to a word
- effective for small to medium text datasets

---

## Limitations

Even though BoW is useful, it has important drawbacks:

- it ignores word order
- it ignores context and semantics
- it loses information about syntax and grammar
- it can produce very large sparse vectors
- common words such as "the", "is", or "and" may dominate the counts without adding much meaning

This is why more advanced techniques such as TF-IDF or word embeddings are often preferred in modern NLP systems.
