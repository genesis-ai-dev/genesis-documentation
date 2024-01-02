# What is Translator's Copilot?

Bible translation technology currently struggles with two significant issues: user interfaces are too complex, making it hard for translators to use both new and existing tools, and software tools are isolated, leading to duplication of effort.&#x20;

To address these problems, we propose to create a Translator’s Copilot AI tool that enables users to leverage complex functionality and even external tools through the highly simplified interfaces of chat conversations and contextual suggestions.&#x20;

The functionality of the proposed Translator’s Copilot AI tool can be categorized into two main buckets:

1. [information-management](information-management/ "mention"): This includes answering questions, as well as finding and synthesizing information resources using AI integration of existing data sources and tools.&#x20;
2. [translation-assistance](translation-assistance/ "mention"): This involves providing contextual suggestions for translation and editing, as well as executing basic tasks and workflows for the translator.

To offer the most effective copilot solution for translators, we aim to integrate our tools directly into their existing workspace—the translation editor app (see [Broken link](broken-reference "mention"))—rather than creating a separate context or window. This approach ensures our tools fit seamlessly into translators’ workflows, as the translation editor app is typically their “home” or primary workspace. Our goal is to enhance their productivity by making our tools readily accessible within the translation editor environment.

The Translator’s Copilot, our experimental tool designed to bring together Bible Translation technology and powerful AI capabilities. With integrations like [The Greek Room](https://greekroom.org), [AQuA](https://www.ai.sil.org/Projects/AQuA), [Translation Core](https://www.translationcore.com), [Paratext checks](https://paratext.org/features/translation-checking-tools/), and more, we want to give translators a single-app integrated experience to enhance their work.

### Design Fundamentals

_Translator's Copilot_ (originally named _Polygloss_) is a multi-AI-agent translation loop that leverages the concepts of **few-shot learning** (i.e., populate prompts with the most relevant data available), **generative adversarial networks** (i.e., pit the agents against one another), and **ensemble techniques** (e.g., attempt multiple translations with a small degree of randomness and extract stable features, or simply attempt to iterate on translation drafts). _Translator's Copilot_ is designed for translation into very low-resource languages where conventional machine translation performs poorly due to a lack of data. It is also designed to outperform many traditional methods in quality at the cost of efficiency. _Translator's Copilot_ is also an iterative approach to translation, designed to have humans in the loop to provide additional data as it becomes available, and to reject, approve, or improve translation drafts.&#x20;

The basic structure of a translation loop involves 1) forward translation ([translation-drafting](translation-assistance/translation-drafting/ "mention")) from source to target, 2) literalistic backward translation ([back-translation.md](translation-assistance/back-translation.md "mention")) from target draft to source, 3) AI evaluation (the architecture does not demand a particular kind of evaluation; cf. [quality-checking](translation-assistance/quality-checking/ "mention")), and 4) human feedback.&#x20;

The greatest obstacles to overcome are i) language-specific [tokenization](https://ryder.dev/tokenizing-low-resource-languages/) (whether using phonic or graphic input channels) and ii) seed data. Seed data is critical because AI cannot translate something that has not been translated before.

### Contraints

*   You cannot translate a word that has never been translated before. This constraint implies that

    * You cannot do zero-shot translation, and
    * You cannot translate into a no-resource language.

    > Note: Multilingual embeddings for a language comprise a kind of existing translation.

### Vision

Whether Translator's Copilot is created to function quasi-autonomously (i.e., flexibly following predefined steps on a translation project to some extent), _a translator should be able to interact with any part of a translation project and have that interaction send out ripples to the entire project_. This goal implies two design priorities:

* In-context learning is preferred over fine-tuning language specific models
* AI predictions should always reflect the current state of the translation project
* Feedback loops should be short, with any translator imput improving AI suggestions immediately

For example, few-shot forward translation works by finding the most-similar translated texts. Evaluation could work in reverse: when someone (or an AI bot) makes an edit on one verse, the results should propagate out to all of the most-similar untranslated verses. When someone makes an edit on a verse, the change should propagate out to all of the most similar wordings throughout the project.

The effect of a translator's interacting ought to be like ripples in a pond or electricity moving through circuits. As such, all of the resources relevant to a given translation project, both those of the source and the target languages, must be accessible in something like a GraphQL database (or, an [agile data hub](https://ryder.dev/more-data-less-decisions/)).

Another way to think about this relates to [swarm-based or hive-mind](https://ryder.dev/swarm-translation/) design. Key to this design philosophy is that every action should leave behind a trace in its environment, so that whatever comes along later can pick up at the next logical step. This might involve constantly adding and updating notes, metadata, or tags on project components, sort of like versioning code dependencies, so that any translation suggestions/revisions can account for relevant changes that have happened since the last time the verse was revised.
