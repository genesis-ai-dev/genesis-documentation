# Frequently Asked Questions

### How does this project relate to Paratext?

> Thanks for the description Ryder. I hadn't heard you were using a fork of VS Code. I was a bit confused because I thought the description was saying that you were planning to integrate the AI tools into existing translation software (ie. Paratext, or whatever). This sounds like moving away from Paratext as the core translation tool and using "Codex" instead. Is my understanding correct?

Paratext is making a new platform right now, platform.bible, but it won’t be ready for some time. Its extension system will be very similar to VS Code, so our thinking is that this path allows us to start iterating right now with the full functionality of VS Code for leveraging AI integrations and innovations in a highly experimental manner, with the hopes of integrating with Paratext in a fairly natural way when our functionality is stabilized and platform.bible is further along.

### How does this project relate to Scribe Scripture Editor?

The team at Scribe is going to be using the Codex base as the base for their next iteration, so we are very excited to be collaborating with them directly on Project Accelerate!

### How does this project relate to ScriptureForge?

We are also planning to work with ScriptureForge to ensure we can achieve some degree of cross compatibility in the tools we are developing, at least in terms of some core functionality in the form of shared library of functions we can both draw from.

### How do you handle low-quality outputs from LLMs?

We aim to use LLMs specifically for things that traditional programming does not handle well. LLMs are not a magic ingredient that can make everything work the first time, rather, they are a tool to harness programmatic _creativity_ in the same way a search engine harnesses programmatic _accuracy_.&#x20;

We use a number of techniques such as few-shot learning, ensemble techniques, and adversarial approaches to get LLMs to work well for translators.

LLMs hallucinate, but this is fundamentally indistinguishable from truly creative uses of language.

> If someone translates something that has never been translated before, wouldn’t that be identical to a hallucination, since there is no benchmark for it? 🧐🙃
