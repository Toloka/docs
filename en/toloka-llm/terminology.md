# Terminology

{{ llm-name }} uses the following terminology in its interface and documentation.

#### Dataset {#dataset}

A set of text to classify with optional labels.

#### Deployment {#deployment}

Making a variant available for use either through API or file-upload UI.

#### Project {#project}

A set of parameters, prompts, and datasets which result in different variants you can deploy and use for labeling. This is also a separate business goal you want to achieve with {{ llm-name }}.

#### Prompt {#prompt}

An instruction that LLM uses to provide a correct answer for your dataset.

#### Variant {#variant}

A combination of a model, its settings and a prompt. Our tool facilitates the process of finding the best variant for your task in a measured way. Once you have a variant that satisfies you, it can be deployed.