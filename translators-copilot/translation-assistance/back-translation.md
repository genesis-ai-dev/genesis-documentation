# Back Translation

A lot of thought needs to go into ways that back-translation can be constrained from hallucinating.

Mechanisms for constraining back-translation and avoiding hallucination will range from rigid to flexible. On the rigid end of the spectrum will be methods like Token matching evaluation and `valid_token` constraints. On the more flexible end, we could try pulling in the most similar verses to the back-translation draft and comparing the target-language 'source' in each case. If the model begins to hallucinate, it will probably not match well with existing translations of similar verses.

Cipher-based completions (see discussion [here](https://ryder.dev/tokenizing-low-resource-languages/)) might be a way we can mask the tokens from the LLM, but we would need to be sure to offer enough in-context data to ensure useful patterns are detected.
