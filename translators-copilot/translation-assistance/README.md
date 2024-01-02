# Translation Assistance

For any machine translation technique to succeed requires lots of data. When it comes to low-resource languages, you simply don't have lots of data. For this reason, we need to explore other methods and techniques that are somewhat orthogonal to&#x20;

Many AI or machine translation techniques, in addition, function like a black box. Some source sequence goes in, and a target sequence comes out.&#x20;

Our vision for translation assistance is intended to be much more iterative and interactive. What we are looking for includes:

* AI predictions and reports that are always based on the current state of the entire translation project
* The ability to provide instant feedback on the AI predictions (e.g., by rejecting them and opting for a manual translation)
* The ability to leverage arbitrary new resources provided by the translator, such as PDFs, Word docs, markdown files, email threads, etc.

In order to archieve this vision, we need to leverage in-context learning (i.e., prompt engineering that dynamically includes relevant data and approved examples in prompts).&#x20;

Read more [here](https://ryder.dev/translating-with-ai/).

### Looping the translation process

If we can leverage AI predictions and reports at each phase of the process, then we should be able to create virtual cycles and bootstrap helpful predictions even from very few examples.
