---
summary: ""
draft: false
author: admin
slug: ai_prompt_engineering
title: AI Prompt Engineering
date: 2023-05-10T19:05:07.172Z
tags:
  - AI
categories:
  - AI
---
### 1. [Start with an instruction](https://platform.openai.com/docs/quickstart/start-with-an-instruction)

Try making your instruction more specific. e.g: Suggest one name for a black horse.

### 2. [Add some examples](https://platform.openai.com/docs/quickstart/add-some-examples)

It’s helpful to both show and tell the model what you want. Adding examples to your prompt can help communicate patterns or nuances. Try submitting this prompt which includes a couple examples.

```
Suggest three names for an animal that is a superhero.

Animal: Cat
Names: Captain Sharpclaw, Agent Fluffball, The Incredible Feline
Animal: Dog
Names: Ruff the Protector, Wonder Canine, Sir Barks-a-Lot
Animal: Horse
Names:
```

Nice! Adding examples of the output we’d expect for a given input helped the model provide the types of names we were looking for.

### 3. Adjust your settings


Prompt design isn’t the only tool you have at your disposal. You can also control completions by adjusting your settings. One of the most important settings is called temperature.

You may have noticed that if you submitted the same prompt multiple times in the examples above, the model would always return identical or very similar completions. This is because your temperature was set to 0.

Try re-submitting the same prompt a few times with temperature set to 1.