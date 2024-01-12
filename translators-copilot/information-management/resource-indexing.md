# Resource Indexing

Whenever a new document or file is added to the `resources/` directory, we should automatically generate some new, low-level indexes, and optionally or more slowly generate semantic embeddings for the documents.&#x20;

Low-level indexes might include TF-IDF indexing, topic models, or LSI indexes. Additionally, we could use tokenization-like methods such as gzip compression.&#x20;

Keyword indexing is handled automatically by VS Code, so we don't need to worry about that.&#x20;

The reason we don't solely want to rely on semantic indexes is that we may not have an embedding model that works well for the language of the document. Token-based indexes, by contrast, will work consistently across all languages.
