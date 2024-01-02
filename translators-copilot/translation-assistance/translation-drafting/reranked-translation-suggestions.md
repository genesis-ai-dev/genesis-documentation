# Reranked Translation Suggestions

Semantic similarity between source verses as a tool for suggesting a disambiguated rendering from multiple possible options.

Would work best with semantic units, not just words, but we can initially implement with words only.

* Source verse 1: “Jesus walked on the water”
* Source verse 2: “Jesus said, give me some water to drink”
* Source word ‘water’ - translated as ‘big blue wet thing’ in target rendering for source 1
* Source word ‘water’ translated as ‘drinking stuff’ in source 2

Dictionary updated to note that there are two possible renderings of the ‘water’ entity in the source, and it notes the verse context for each rendering.

Later, when we want to suggest a rendering for ‘water’, we first check our new source verse, and see whether it is most similar to the verse that says ‘big blue wet thing’ in it, or else the verse that says ‘drinking stuff’ in it.&#x20;

Suggest the most likely option accordingly.

> Note: Semantic units - previous glosses apply to the largest entity in nested entities AND all children until there is a separate case where there’s only partial overlap between source and target

\
