# Linguistic Anomaly Detection (LAD)

Linguistic Anomaly Detection is a technique for similarity scoring (compression-based, embedding-based, or traditional NLP-based) between source-source and target-target pairs.&#x20;

This involves comparing the similarity of source texts and their corresponding target texts. Rather than being scored against a baseline, however, it has the essential feature of being _relativized_ to the current state of the translation project, such that only the verses a human has already translated/edited serve as the gold standard.

Here's an idea for how LAD might work in a translation project

1. Suppose you have a source1-target1 pair that has been manually vetted and is considered the gold standard.
2. You also have a source2-target2 pair that has not been vetted yet.
3. Compare the similarity of source1 and source2. This could involve comparing the compression results or similarity between the sources and between the targets, doing TF-IDF intersection scoring against your current project, or some other method.
4. If the similarity between source1 and source2 is `0.8`, then the similarity between target1 and target2 should be within a standard deviation of `0.8`. (This is my suspicion at least.)
5. Provide Scores or Reports on Estimated Consistency: The above technique (or a variation thereof) could be used to provide scores or reports on the estimated consistency for the unvetted target text (target2). This allows for a quantitative measure of the translation's internal consistency, and by implication it should indicate something about its overall quality.

See cleaned up post with additional thoughts [Linguistic Anomaly Detection](https://ryder.dev/linguistic-anomaly-detection/).
