---
date: 2026-01-16
authors: [riad]
categories:
  - Thesis
  - AI Development
  - LLM
---

# Sometimes getting your hands dirty with GPT is necessary!

After 7 days of trial and error with a GPT agent, I finally restored my text extraction model accuracy from **57% to 85%**. And guess what, the solution is simple as getting your hands wet.
<!-- more -->

## ⏱️ The Problem
This is related to my thesis. A month ago, my extraction model was solid at 85%. After finishing my word localization model, I went back to extraction only to find it had mysteriously dropped to a dismal **47-54%**. 

## 👷 The Struggle
I spent several days trying everything:

* **Retraining:** Ran the dataset through multiple loops.
* **Manual Checks:** Verifying outputs line-by-line.
* **Data Augmentation:** Tried to "pump" the numbers up with synthetic data.

**Result:** Nothing worked. The accuracy stayed flat.

## ⚡️ The "Aha!" Moment
Finally, I stopped asking the GPT agent to "fix it" and decided to **manually design the data generation pipeline.**
I just manually alighend the data generation pipeline to this

* Dataset Pre-processing
* Word extraction
* Train test validation split
* Train set augmentation

And it jumped to 85% 🫠!

!!! success "Lesson Learned"
    Sometimes, models can't even join together scripts they generated themselves! By taking manual control of