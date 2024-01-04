# Custom Notebooks

### How We Can Leverage Notebooks as a Scripture Editor

VS Code has an API for custom notebooks. A notebook mixes together embedded code editors (i.e., Monaco code editors) as executable cells with output fields. There are also Markdown cells that can be edited and rendered.

<figure><img src="../../.gitbook/assets/Screenshot 2024-01-04 at 3.04.03 PM.png" alt=""><figcaption><p>Custom notebooks might be a key solution for our use case</p></figcaption></figure>

It turns out that you can render custom React components as the cell output or (I believe) as a custom cell type. Imagine, for example, a custom WYSIWYG Markdown or USFM editor cell.&#x20;

Custom notebook editors can be configured to operate with certain file types, such as `.usfm` files or other common formats.

With some modification of the default display conventions for notebooks to make them look more translator-friendly, I can imagine the following scenario:

1. User clicks 'new translation unit' cell (instead of `+Code` or `+Markdown` cell).
2. User can set metadata for the new cell. For example `Type: Passage` or `Type: Verse` or `Type: Story`, and perhaps `Range: Genesis 1:1-3`, `Modality: Text` or `Audio`, etc. \
   [_Such metadata would not need to be constantly set for every new translation unit, but I don't see why it couldn't be mixed and matched._\
   ](#user-content-fn-1)[^1]_Scripture ranges, for example, could be populated by default based on the next unit of whatever type the previous cell uses. E.g., if the user just populated the `passage`_ _`Matthew 5-7`, then the next cell would default to something like `Matthew 8`._ &#x20;
3. User populates new translation cell using [translation-drafting](../../translators-copilot/translation-assistance/translation-drafting/ "mention") functionality we provide (such as audio recording or translation suggestions). Suggestions and contextual data are provided based on the selected `Range` property. `Matthew 5-7` would call up suggestions relating to the entire Sermon on the Mount. VS Code's embedded Monaco cell editor provides static [quality-checking](../../translators-copilot/translation-assistance/quality-checking/ "mention") tools to the translator such as [spell checking](https://greekroom.org/spell/).
4. User can "execute" the new translation draft, triggering an orchestrated evaluation using more dynamic checks such as [Translation Core Notes](https://www.translationcore.com), or [Linguistic Anomaly Detection](https://ryder.dev/linguistic-anomaly-detection/). This is essentially a "report" on possible ways to improve the draft, and the user is able to trigger a revision workflow whereby an AI agent attempts to implement some of the changes, clearly marked with a Git diff line-by-line suggestion.
5. User then reviews the evaluation and, when satisfied with the draft, adds a 'new translation unit' cell or a 'new paratextual information unit' cell (for adding additional titles, headlines, footnotes, accompanying images, etc.

I believe that using custom notebooks provides us with a way to handle many of the potential issues that arise through strict reliance on the native VS Code editor alone (since it doesn't look enough like Microsoft Word) or else on rendered WYSIWYG editors alone (since they don't have the same off-the-shelf functionality of the VS Code editor). This proposed approach may enable us to avoid many of the tradeoffs of other approaches, since notebooks inherently combine the best features from both other options.

### Links and Resources

[VS Code Notebook API reference](https://code.visualstudio.com/api/extension-guides/notebook)

[Sample custom notebook with a React wrapper](https://github.com/microsoft/vscode-extension-samples/tree/main/notebook-renderer-react-sample)

[Deepdive video walkthrough of the Notebook API](https://learn.microsoft.com/en-us/shows/vs-code-livestreams/notebooks-deep-dive)

[^1]: 
