# TF-IDF

TF-IDF (Term Frequency–Inverse Document Frequency) represents text with numerical weights. It gives higher weight to terms that appear often in a document but are uncommon across the corpus, and lower weight to terms shared by many documents.

## How it works

- **Term Frequency (TF):** `TF(t, d)`= how often a term t appears in a document d.
- **Inverse Document Frequency (IDF):** how rare the term is across the corpus. A common form is `IDF(t) = log(N / df(t))`, where `N` is the number of documents and `df(t)` is the number of documents containing term `t`.
- **TF-IDF:** `TF(t, d) × IDF(t)`.

## Example calculation

Consider two documents: `D1 = "cat sat cat"` and `D2 = "dog sat"`. Use raw term counts for TF and the natural logarithm for IDF.

There are `N = 2` documents. The term `cat` appears in one document, so `IDF(cat) = ln(2 / 1) ≈ 0.693`. In D1, `TF(cat, D1) = 2`, giving `TF-IDF(cat, D1) = 2 × 0.693 ≈ 1.386`.

| Term | TF in D1 | Documents containing term (`df`)  | IDF `ln(2 / df)` | TF-IDF in D1 |
|------|----------|-----------------------------------|------------------|--------------|
| cat  | 2        | 1                                 | 0.693            | 1.386        |
| sat  | 1        | 2                                 | 0                | 0            |
| dog  | 0        | 1                                 | 0.693            | 0            |

The shared term `sat` gets an IDF of zero in this unsmoothed formula, while the rarer term `cat` receives a higher weight.

For example, a word repeated in one document but absent from most others receives a higher weight than a word such as “the” that appears in nearly every document.

## Why use it?

TF-IDF is a weighted version of Bag of Words: it reduces the influence of common terms while highlighting terms that help distinguish documents. Like Bag of Words, it ignores word order and context, and produces sparse vectors.
