# Token matching evaluation

In Microsoft guidance, you can use the \{{select\}} syntax to select a specific value. PERHAPS what I should be doing (at least for back-translation), is populating a list of valid tokens, and then only allowing the model to back-translate any given word from one of the valid tokens.

Since a few-shot translation case involves sample translation pairs, the set of valid tokens would include words and phrases that have appeared in these pairs (in the English glosses, for example).

This way, the output translation will more likely align with the sample translations provided in the prompt. Any tokens not in the set of valid tokens are simply retained in their translated form in \[square brackets] to indicate they have not been back-translated because they are unknown.

It might also make sense to gather samples based on whether or not they help cover the missing tokens. So perhaps there is an initial set of 5 semantically similar examples, and then a second set of 5 more sentences that include the english glosses not represented in the first five examples.

1. Populate a list of valid tokens for back-translation.
2. Only allow the model to back-translate any given word from one of the valid tokens.
   1. Use the for chunk of 6 tokens, \{{select options=valid\_tokens n=6\}} syntax to select a specific value.
   2. Include words and phrases that have appeared in sample translation pairs in the set of valid tokens.
      1. **assumption is**: if a word hasn't even been translated once by a human, then any attempt would effectively be indistinguishable from a hallucination (i.e., it has to correspond to reality)
      2. example:
         1. I need to translate english 'Jerusalem'
         2. I find 5 sentences with 'Jerusalem' in them
         3. Those sentences have Abanyom renderings, like 'Yerusalem'
         4. The only valid renderings must be contained in the sample sentences
   3. Retain any tokens not in the set of valid tokens in their translated form in \[square brackets] to indicate they have not been back-translated because they are unknown.
      1. Have an agent send out messages on WhatsApp to the translation team, or use a simple gamified app (or ask Michael Marshall what is involved here?)
3. Consider gathering samples based on whether or not they help cover the missing tokens.
   1. Start with an initial set of 5 semantically similar examples.
   2. Follow with a second set of 5 more sentences that include the English glosses not represented in the first five examples.

{% embed url="https://youtu.be/EX0KUbEG6-8" %}
Token matching evaluation at the end (yellow tokens are not in prompt's few shot examples)
{% endembed %}
