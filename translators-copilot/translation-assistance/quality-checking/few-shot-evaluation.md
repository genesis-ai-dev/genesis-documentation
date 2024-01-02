# Few-shot evaluation

Keeping things simple, and sticking with only the resources at hand, what if the evaluation stage involved the following:

1. Take the draft translation and find the most similar translation pairs to the paired prediction
2. Try to evaluate if any of the words seem misused
   1. Perhaps you could have a rules-based matcher that identifies any tokens in the source+prediction pair that only occur in EITHER the source OR the target in any of the similar examples
   2. It might also be worth examining whether any words seem to be mistranslated based on the gold standard examples
   3. POSaligning these examples would probably help
3. Pass the task back to the translate bot with special notes about any seemingly mistranslated words.

Essentially: \[ most similar examples ] --> \[ prediction ] --> \[ most similar examples ]
