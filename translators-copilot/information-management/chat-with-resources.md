# Chat with Resources

The Translator's Copilot should enable users to interact with their resources in a chat conversation, as well as via traditional methods such as simply opening various file types and interacting with them.&#x20;

The overall aim is to provide powerful interaction opportunity through [the simplest possible user interface](https://ryder.dev/simplest-possible-ui-for-ai/).

### Development Plan

What’s involved in getting this into working order is:

1. Some way of retrieving resources. This could be:
   1. Embedding functionality (i.e., vectorization)
      1. `sentence_transformers` model
      2. global vector based retrieval
   2.

* We should have a cloud instance (for faster connections) and a local instance of any given same sentence\_transformers model
* Vectorstore - must be local
* Chat UI - vs code web view
* LLM - API connection or local model (ideally both: one in the cloud on a powerful computer and the other local  )
