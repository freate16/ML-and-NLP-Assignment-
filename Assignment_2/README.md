# 📊 Summary

| Method              | What it captures                                                                       | Word Score Example (`'the'`)                                   |
|---------------------|-----------------------------------------------------------------------------------------|----------------------------------------------------------------|
| **CountVectorizer** | Raw frequency of each word per document                                                | High score if `'the'` appears often                            |
| **Manual TF-IDF**   | Adjusts frequency by how common the word is across documents                           | Lower score for `'the'` if it appears in most documents        |
| **TfidfVectorizer** | Same as manual TF-IDF (but optimized; includes smoothing & normalization)              | Very low or zero for `'the'` (especially if using stopwords)   |

> 📌 *Note:* Scikit-learn’s `TfidfVectorizer` uses a slightly different formula with smoothing and normalization.  
> This is why values may differ from manually calculated TF-IDF.

---

### ⚠️ Why Common Words Like `'the'` Get Low TF-IDF Scores

- **CountVectorizer** treats all words equally → `'the'` gets a high score if it appears often.
- **TF-IDF** downweights common words → `'the'` appears in every document → high document frequency → low IDF → **low TF-IDF score**.

