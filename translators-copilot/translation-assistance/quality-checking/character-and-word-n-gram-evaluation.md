# Character and word n-gram evaluation

The basic idea here is to use the chrF++ algorithm to evaluate against a known translation. Shifting the β value (where β=1 means precision \[hypothesis overlap normalized by hypothesis length] and recall \[hypothesis overlap normalized by reference length] are equally weighted) may be significant.

The problem here is that you always need a reference. So this might be useful for fine-tuning a model, or else just naively scoring a model, but exposing the non-overlap would be very interesting in terms of data an LLM can use, especially

### How the chrF++ algorithm works

The chrF++ algorithm is a metric used in machine translation to evaluate the quality of translated text. It is an extension of the chrF metric, which is based on character n-gram precision and recall. The chrF++ algorithm adds word n-gram precision and recall to the mix, providing a more comprehensive evaluation of translation quality.

Let's break down how the chrF++ algorithm works using a toy example.

Suppose we have a reference sentence (the correct translation) and a hypothesis sentence (the translation produced by a machine translation system) as follows:

Reference: "The cat sat on the mat." Hypothesis: "A cat is sitting on the mat."

We'll use bigrams (2-grams) for simplicity in this example.

1.  **Character n-gram precision and recall**:

    First, we calculate the character n-gram precision and recall. For bigrams, we look at pairs of characters.

    Reference bigrams: {"Th", "he", "e ", " c", "ca", "at", "t ", " s", "sa", "at", "t ", " o", "on", "n ", " t", "th", "he", "e ", " m", "ma", "at", "."}

    Hypothesis bigrams: {"A ", " c", "ca", "at", "t ", " i", "is", "s ", " s", "si", "it", "tt", "ti", "in", "ng", "g ", " o", "on", "n ", " t", "th", "he", "e ", " m", "ma", "at", "."}

    Precision (P) is the number of bigrams in the hypothesis that are also in the reference, divided by the total number of bigrams in the hypothesis.

    Recall (R) is the number of bigrams in the hypothesis that are also in the reference, divided by the total number of bigrams in the reference.
2.  **Word n-gram precision and recall**:

    Next, we calculate the word n-gram precision and recall. For bigrams, we look at pairs of words.

    Reference bigrams: {"The cat", "cat sat", "sat on", "on the", "the mat"}

    Hypothesis bigrams: {"A cat", "cat is", "is sitting", "sitting on", "on the", "the mat"}

    Again, precision (P) is the number of bigrams in the hypothesis that are also in the reference, divided by the total number of bigrams in the hypothesis.

    Recall (R) is the number of bigrams in the hypothesis that are also in the reference, divided by the total number of bigrams in the reference.
3.  **Combine the scores**:

    The final chrF++ score is a combination of the character and word n-gram scores. The formula is as follows:

    chrF++ = β \* (1 + (P\_char + R\_char) / 2) \* (1 + (P\_word + R\_word) / 2)

    where β is a parameter that controls the balance between precision and recall. A common choice is β = 1, which gives equal weight to precision and recall.

In this toy example, the numbers are made up, but in a real scenario, you would calculate the precision and recall values based on the actual overlap between the reference and hypothesis n-grams. The chrF++ score gives a measure of how similar the hypothesis is to the reference, taking into account both the character and word level information.
