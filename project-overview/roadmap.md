---
description: This is a "living roadmap," which we will adapt based on user feedback!
---

# Roadmap

The following milestones are grouped into categories and roughly ordered by priority within each category, though note that we are following a shotgun-based approach as per our [project-philosophy.md](project-philosophy.md "mention").

### Codex Milestones

* [ ] Package [Broken link](broken-reference "mention") for user downloading\
  _We have a downloadable, compiled app, with a pre-packaged and compliled 'hello world' extension._
* [ ] Create UI strategy \
  _For now, perhaps just serif font, black on white, hide or decorate line numbers, etc.?_
* [ ] Project standards to support initially\
  _ORG plaintext project extracted from Paratext? Use a USJ underlying representation for Paratext export?_
  *   [ ] Support plaintext project with ORG verse referencing (i.e., [eBible corpus](https://github.com/BibleNLP/ebible/tree/main/corpus) projects)\
      `|-- project`\
      `|   |-- scripture`\
      `|   |   |-- matthew.txt`\
      `|   |   |-- mark.txt`

      `|   |-- resources`\
      `|   |   |-- my_resource.pdf`\
      `|   |   |-- another_resource.md`
  * [ ] Support USJ project with extensible metadata and Paratext export
* [ ] Determine whether it is easier to implement language diagnostics in an RCL custom rich text editor, or else adapt the display of the native VS Code editor to function or simply look more like a rich text editor
* [ ] Implement audio mode PoC (cf. [multimodality.md](../codex-base-app/multimodality.md "mention"))

### Translator's Copilot Milestones

* [ ] Implement initial [chat-with-resources.md](../translators-copilot/information-management/chat-with-resources.md "mention") functionality\
  _Currently this will probably be a fork of the_ [_Continue extension_](https://continue.dev)
* [ ] Curate initial offline and online source text resources for [greek-hebrew-insights.md](../translators-copilot/information-management/greek-hebrew-insights.md "mention")
* [ ] Create initial orchestrated translation [quality-checking](../translators-copilot/translation-assistance/quality-checking/ "mention") functionality\
  _Quality checking functionality will be a_ [_language server extension_](https://code.visualstudio.com/api/language-extensions/language-server-extension-guide) _for text content analysis._
  * [ ] Basic scripture checking (e.g., verse order, etc.)
  * [ ] [Greek Room spell checking](https://greekroom.org/spell/) and normalization
  * [ ] (?) UnfoldingWord TranslationCore Notes checks
  * [ ] Abstract functionality into shared repository with SIL/ScriptureForge team
* [ ] Implement initial [translation-drafting](../translators-copilot/translation-assistance/translation-drafting/ "mention") functionality

### General Project Milestones

* [x] Non-public documentation of translators interested in testing
* [ ] Create translator-feedback and testing workflow
