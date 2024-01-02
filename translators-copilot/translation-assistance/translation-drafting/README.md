# Translation Drafting

## LLMs and Translation drafting

When using an LLM for translation drafting, it is crucial to keep in mind that _there is no difference between translation and hallucination for an LLM_. We need to design systems that account for that fact by _iteratively refining the context_ of any prompt to reduce the probability of a low-value output for the purposes of translation drafting.

### Forward translation

The forward translation step will ideally be approached as a multi-step process by which an AI bot builds up an ideal prompt to translate the current source sentence. This process could involve:

* Provisioning relevant data
  * Similar translation pair examples
  * Relevant lexical entries
  * Potentially relevant human-feedback notes
* Preprocessing those examples (e.g., phrase chunking and alignment if verse has not been aligned yet) \[could this be done asynchronously?]
* Identifying and excluding never-before-translated tokens (see constraints above about zero-shot translating)
* \[etc.?]

The result of this process is a prompt loaded with the most relevant data points. The theoretical reason for not simply translating at every step is, for example, some retrieved sentences might be similar to lexical items that might relate to previous human feedback about a different verse. Translating without all of the most relevant context is likely to be prone to less-valuable hallucination.

In addition, after a draft is generated (or several, given some level of randomness), post-processing can happen via an LLM:

* Reorder translated phrases according to most-similar examples for each phrase (check how similar phrases are ordered in existing translation pairs)
* Evaluate stable prediction from ensemble (rule-based or LLM-based evaluation)
* \[etc.?]

{% embed url="https://youtu.be/EX0KUbEG6-8" %}
Example of few-shot translation
{% endembed %}

### Tokenization

Tokenization of the target language will be a crucial step in getting the LLMs to handle the text correctly.

One option for improving tokenization is creating a `sentencepiece` model of all of the target language strings available so far. Another option is treating all whitespace-delimited words as tokens initially, and manually identifying sub-word tokens for a lookup table. It may be possible to create an bot (LLM-powered, I would think) tasked with identifying ngrams using conventional tools and building up a lookup table in this manner.

