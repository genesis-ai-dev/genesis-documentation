# Project Philosophy

There are a number of principles we are trying to stick to with this project.

1. **User-focused development:** Our priorities and processes for a project proposal are centred around user-focused development, ensuring that the primary focus is on meeting the needs of those who will be using the product. To achieve this, we will start from the Codex app (forked and adapted from VS Code), using it as a base application and reference implementation. This allows us to build upon an already successful tool, making our project’s foundation strong, and enabling users to test new functionality on an already complete editor.
2. **Rapid progress:** How can we get 80% there with 20% effort
3. **No Compromises with Informed Leadership:** Adopting the 'Informed Captain' philosophy, this principle underscores the importance of informed and decisive leadership in our decision-making process. The Informed Captain, fully versed with the situation's intricacies, may choose to advance their own idea or, alternatively, endorse a team member's suggestion. The critical aspect is that once a decision is made, it is the captain's responsibility to determine the direction. Thereafter, the principle of _"I disagree, but I commit to doing it your way"_ comes into play. This means, irrespective of personal viewpoints, the entire team unites in their effort to make the chosen path successful. This approach ensures that decisions are not just based on thorough understanding and collective wisdom, but are also executed with full commitment and cohesion, aligning with our project's vision and values.
4. **More features and less decisions:** This one comes from Amazon: There are _two-way door decisions_ and _one-way door decisions_. For a two-way door decision, the consequences of reversing the decision down the road seem to be relatively low. You only need to escalate one-way door decisions.
5. **Shotgun approach:** Similar to the previous point, we will attempt to have many simultaneous paths of development moving in the same direction, with the same big-picture milestones in view.
6. **Offline accessibility:** Offline usage will also be a crucial part of the project, and we will consider it throughout all stages of the development process. Having offline access ensures that users will not need to rely on consistent or expensive internet access, since this may not be available or affordable. At the same time, using VS Code allows us to provide completely online web access to the editor, so that users who have internet access but do not have high-end devices can also make use of these emerging tools for their projects. VS Code’s minimum operating requirements will be our target for device support (i.e., 1.6 GHz processor and 1 GB RAM—a low bar to entry).
7. **Localization:** Targeting the top-ten strategic languages for localization is essential for this project to serve emerging translation projects. VS Code is already localized into 14 “core” languages (English, French, Italian, German, Spanish, Russian, Chinese simp. and trad., Japanese, Korean, Czech, Portuguese, Turkish, Polish, and “Pseudo Language”, which helps with further localization development). We will need to carefully develop AI tool localization strategies to complement the already localized UI. We expect significant challenges relating to right-to-left scripts in the user interface (i.e., the main app controls), though VS Code does support RTL scripts in the main text editor, which means we can still support scripture editing for RTL languages even if the user interface itself is one of the LTR localizations.
8. **Multimodality:** In addition, we aim to enable multimodal inputs and outputs (primarily audio), as well as handling of multimodal language resources that include images and potentially videos. VS Code has affordances for rendering such resources, and there are a growing number of multimodal AI models that may be leveraged to query and discuss these resources directly with users, along with additional functionalities such as populating a dictionary.