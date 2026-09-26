# Named Entity Recognition (NER)

Named Entity Recognition (NER) is a fundamental task in Natural Language Processing (NLP) that identifies and classifies important entities in text. These entities can be names of people, organizations, locations, dates, monetary values, percentages, products, and other specific terms.

In simple terms, NER helps a machine understand which parts of a sentence are meaningful and what type of information they represent.

## What is NER?

NER is usually performed as a sequence labeling task. The model reads a text and assigns a label to each token or sequence of tokens.

Examples of entity types include:

- Person: "Tim Cook"
- Organization: "Apple"
- Location: "Paris"
- Date: "September 20, 2026"
- Money: "$1,000"
- Product: "iPhone"


## Why is NER important in NLP?

NER is important because it transforms raw text into structured (in term of tokens) information. This is a critical step for many NLP applications because it allows systems to extract meaningful facts instead of working only with unstructured text.

Without NER, a machine may read text but still fail to distinguish between a person, a company, a date, or a location.

## Main use cases of NER

### 1. Information extraction
NER is used to extract key facts from large amounts of text, such as names of people, companies, countries, dates, and products.

Example:
- Extracting company names from financial reports
- Extracting disease names from medical notes
- Extracting locations from news articles

### 2. Search and recommendation systems
NER helps search engines understand the entities in a query and improve ranking.

Example:
- Searching for "Apple CEO in 2026" should match articles about Tim Cook and Apple.
- E-commerce platforms can identify product brands and categories in customer reviews.

### 3. Customer support and chatbots
NER can identify customer names, products, order IDs, dates, and locations in support messages.

Example:
- "My order from Amazon arrived in Paris on October 5."
- The system can detect: Amazon (Organization), Paris (Location), October 5 (Date).

### 4. Healthcare and biomedical research
In medicine, NER is used to identify diseases, drugs, symptoms, treatments, and patient data from clinical records.

Example:
- "The patient was diagnosed with diabetes and treated with insulin."
- Entities: diabetes (Disease), insulin (Drug)

### 5. Financial analysis
Financial institutions use NER to extract companies, markets, currencies, and transaction data from text.

Example:
- Detecting the names of banks, stock symbols, and currencies in news articles and annual reports.

### 6. Legal and compliance
NER helps legal systems identify parties, laws, jurisdictions, dates, and case names in contracts or court documents.

Example:
- Extracting organization names and legal references from contracts and rulings.

### 7. Media and journalism
News organizations use NER to detect people, organizations, events, and locations in articles.

Example:
- Automatically tagging article entities to build recommendation systems or knowledge graphs.

## Example NER  with Python and spaCy

```python
import spacy

nlp = spacy.load("en_core_web_sm")
text = "Apple announced the new iPhone in Cupertino on September 20, 2026. Tim Cook spoke to journalists."

doc = nlp(text)

for ent in doc.ents:
    print(ent.text, "->", ent.label_)
```

Possible output:

```python
Apple -> ORG
iPhone -> PRODUCT
Cupertino -> GPE
September 20, 2026 -> DATE
Tim Cook -> PERSON
```

This shows how NER can automatically identify entities from unstructured text.

## Challenges in NER

Even though NER is very useful, it can be difficult in some cases:

- Ambiguous names: "Paris" can be a city or a person name.
- New entities: brand names or emerging startups may not be in training data.
- Entity variations: "Dr. Smith", "Smith", and "John Smith" may refer to the same person.
- Multilingual text: names and formats differ across languages.
- Domain-specific vocabulary: medical or legal terms may be hard to recognize without specialized models.

## Conclusion

In short, NER helps computers understand not just words, but also the meaning and significance behind them.
