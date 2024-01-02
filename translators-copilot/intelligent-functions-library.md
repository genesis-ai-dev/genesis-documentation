# Intelligent Functions Library

We are planning to collaborate with SIL on a library of intelligent functions including:

* Translation suggestion functions
* Quality-checking functions
* Basic checking functionality

This library will likely be a Lerna + yarn + TypeScript stack, installable as a simple JS package.

We might use some of the proposed functionality in this proposed shared project from the Parnership for Applied Biblical NLP: [bible-ai-endpoints-test](https://github.com/BibleNLP/bible-ai-endpoints-test/blob/main/README.md#list-of-endpoints)

#### Simpler tasks

* [ ] &#x20;Language Identification Endpoint: An endpoint that takes a string as an input and outputs the detected language. This could be useful for tasks where the language of the text isn’t known beforehand.
  * [ ] &#x20;I have text in Yoruba, don’t know the code, but some endpoint requires an ISO-2 or -3 code
  * [ ] &#x20;Get ISO-3 code for Yoruba
  * [ ] &#x20;Allows LLMs to take natural language query “... Yoruba …” and retrieve ISO code
  * [ ] &#x20;Not necessarily trivial - Armenian has 2 ISO codes for sub-dialects, etc.
  * [ ] &#x20;Input = string
  * [ ] &#x20;Output = list of 2-character ISO codes, and 3-character iso codes
* [ ] &#x20;BLEU Scoring Endpoint: An endpoint that accepts a reference translation and a candidate translation and returns a BLEU score (via NLTK).
* [ ] &#x20;Romanizing Text Endpoint: An endpoint that converts text from one script to another. This would be particularly useful for languages with non-Latin scripts. See Ulf’s library [uroman](https://github.com/isi-nlp/uroman/issues/9).
* [ ] &#x20;Keyword List Retrieval Endpoint: An endpoint that can extract the list of key content words or names from the text for further alignment tasks.

#### More complex tasks

* [ ] &#x20;FastAlign Endpoint: An endpoint that attempts to align two sentences using a simple, efficient model like FastAlign. This would likely require access to pre-trained models (do these exist? Do we need to make these?) or an ability to train models from provided datasets.&#x20;
  * [ ] &#x20;Pretrained models
  * [ ] &#x20;Endpoints for specific language pairs/sets
* [ ] &#x20;Statistical Alignment Endpoint: An endpoint that takes two strings as an input and attempts to statistically align them. It can use models like IBM Model 1 to 4, HMM, etc. Are there tools in SIL Machine for this?
  * [ ] &#x20;Input: parallel sentences
  * [ ] &#x20;Function trains model
  * [ ] &#x20;Output word-by-word alignment
* [ ] &#x20;Syntax-Aware Alignment Endpoint: An endpoint that aligns considering the syntax of the languages. We could leverage MACULA data for source-text syntax chunking.
* [ ] &#x20;Multilingual Alignment Endpoint: An endpoint that can take multiple sentences in different languages and align them all together. We would need to specify the alignment method, or this could be an LLM-powered tool.
* [ ] &#x20;Preprocessing before alignment: merged vrefs in one language, etc.
* [ ] &#x20;E-Bible endpoints: what services could we expose relevant to this data?
  * [ ] &#x20;Endpoint to get multiple versions for a given verse or range
  * [ ] &#x20;Resolve versification between versions (using ParaText “original” versification?)

