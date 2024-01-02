# Multi-Agent Simulations

It ought to be possible, in some scenarios (particularly resource constraints and model availability) to run a continuous multi-agent simulation to iteratively improve a draft translation.&#x20;

One example I've implemented involves the following basic loop (each step is not necessarily blocked by the prior step):

* Main translation loop
  * Forward translation bot drafts a new translation instance using few-shot learning based on the available example translations drafted so far by humans
  * Back-translation bot provides a back-translation of the new instance
  * Evaluation bot provides feedback on how to improve, correct, or revise the instance
  * repeat process until the translation draft stabilizes (if it does!)
* Linguist bot builds and updates language resources, such as a multilingual project lexicon, a working grammar, machine grammar rules for output token biasing with the LLM, etc.
* Project manager bot brings stable drafts to human translation team for input, feedback, and correction. Corrected drafts are added to the pool of examples available to the main translation loop.

{% embed url="https://youtu.be/gUi-mhk6D7g" %}
Early POC sample using GPTeam library
{% endembed %}
