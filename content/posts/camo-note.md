---
author: "Milad"
title: "I Built a Writing App That Hides Text While You Type - Stay Private in Public"
date: "2026-04-07"
description: "My experience with creating Camo Note"
FAtags: ["web", "app"]
FAcategories: ["web"]
FAseries: ["Themes Guide"]
aliases: ["migrate-from-jekyl"]
ShowToc: true
TocOpen: false
weight: 2
---

## [Try it now → Camo Note](https://camonote.miladggg.com/editor)  
#### A fast and free demo is available on my site!

<!--more-->


## Camo Note - How it works
[Camo Note](https://camonote.miladggg.com/editor) is my web app solution to shoulder surfing.


### Text Masking
As you type in Camo Note, your words are *masked*. Your text will always mimic an innocent-looking document.

![Masking demo](/posts/masking.gif)

### Context
Of course, if everything is always masked, then it would be quite difficult to flow your thoughts properly.  
That's where context comes in. Around your caret, words in a small radius will discreetly light up and reveal themselves. You can choose how much you want to reveal at any time. Also, at any time you can reveal the entire document by holding the tidle key (\`).  
This way, you can see your thoughts without having them exposed to others.

![Styles demo](/posts/context.gif)

### Styles
Masking styles alter what onlookers will see when they look over at your screen. You could choose to disguise your text as: a scientific report, a news article, a legal document and more.  
People glancing at your screen will assume you are just getting some boring routine work done (unless you chose Pirate mode 🏴‍☠️).

![Styles demo](/posts/styles.gif)

### Word Processor
Camo Note was built to visually mimic other popular word processors. In a space full of people working away at their devices, you'll blend right in.

![Camo Note screenshot](/posts/camo1.png)




## Why?
I spend a lot of time on my laptop at my university's library. And in between doing assignments and writing up lecture notes, I like to type out some self reflections or journal entries.  
But heres the issue, theres a lot of people at the library. Some walking past, some sitting beside you, some sitting with a direct line of sight to your screen. And it becomes very difficult to type out a self-reflection, especially if you want to get personal.  

To stop any wandering eyes from reading my personal documents, I tried writing in tiny font sizes, using code names for sensitive words and turning my laptop brightness to the lowest possible brightness. And at that point, typing at a black screen while frantically checking behind you looks quite strange.  

So as a programmer, I had to build a solution so that I could write in peace, in plain sight.

### The Codebase
The second reason I set out to build this project was to strengthen some Web Development skills that I believe are valuable such as:
- TypeScript (rather than JavaScript)
- Next.js
- Tailwind CSS
- TDD (Test Driven Development)

Overall it was a very rewarding project to build and I learned quite a bit 😁.
