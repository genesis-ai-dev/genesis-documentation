# Multimodality

We will almost certainly need to use a custom editor component for multimodal projects.

### Links/Resources

[Custom editor learnings](https://timheuer.com/blog/resx-editor-for-visual-studio-code/)

#### Audio

See [SIL Transcriber](https://software.sil.org/siltranscriber/) app

[Audio editing plugin](https://marketplace.visualstudio.com/items?itemName=chocolate-pie.sound-editor\&ssr=false#overview) (though double check license, and it’s not super functional at this point.)

![Screenshot 2023-12-20 at 8.08.17 AM.png](blob:https://app.gitbook.com/418f3b3f-84e3-44a7-a319-c2a4dbe0ca00)

We should explore how we might integrate AVTT software into VS Code as rendered components.&#x20;

#### Image

Klappy has made a simple POC plugin generating images using scripture prompts.&#x20;

I suspect there are a number of image editing plugins. We could use these to mark up images before processing with a multimodal LLM.

Cf. [Custom editor sample extension for image editing](https://github.com/microsoft/vscode-extension-samples/blob/main/custom-editor-sample/README.md)
