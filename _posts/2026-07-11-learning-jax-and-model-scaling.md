---
layout: post
title: Learning JAX and Model Scaling
---

[Vlad Feinberg's blog on concrete skills](https://vladfeinberg.com/2026/05/10/how-to-land-a-job-at-a-frontier-lab.html) required for succeeding at a frontier AI lab prompted me to close gaps in my skillset. I have tinkered around with Keras, scikit-learn, and PyTorch in the past, but JAX is a different beast. Since I have very limited experience working with the framework, this seems like a direction worth pursuing.

During my time in the ACI org, we were working primarily on making XLA work well with TPUs, and the lagging performance benefits on GPUs are [an open secret](https://arxiv.org/abs/2309.07181). So why even learn it?

## Reasons to Learn JAX
- Scales well on alternate accelerators that are based on systolic arrays. As GPU costs keep increasing, these (TPUs, Trainium, etc.) will become valuable.
- The blog reckons a research engineer should have the ability to pick up JAX fairly easily with all the latest documentation. I had last worked minimally with JAX in early 2025, and it was pretty poor in terms of documentation. Things seem to have improved marginally and there's some community adoption prompting me to give it another shot.

## Resources
- [A First Taste of JAX](https://github.com/google/flax/blob/main/docs/notebooks/a_first_taste_of_jax.ipynb) - This seems like a good place to start. It covers the basics of JAX and how to use it for machine learning.
