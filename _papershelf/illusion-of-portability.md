---
layout: paper
title: The Illusion of Portability
---

# The Illusion of Portability

[The Illusion of Portability: On the Cost of Hardware-Specific Performance in Deep Learning](https://arxiv.org/abs/2309.07181)

This paper is a personal favorite because of the fact that it says the quiet part out loud by presenting really solid evidence.

Over the years, multiple hyperscalers have been trying to catch up to Nvidia by proposing alternative hardware architectures for Deep Learning training and inference. Google developed JAX to drive TPU adoption, and AWS has followed suit. Meta has a similar incentive of trying to reduce its compute costs and has been working on PyTorch XLA. 

While TPUs have been gaining traction in recent years, there's a fundamental lock-in when you choose the hardware. This is what allows Nvidia to dominate the market.

Unlike traditional PyTorch, which is extremely well documented, the XLA version and JAX aren't well documented.

JAX and PyTorch XLA are difficult to use and learn as frameworks. If you aren't inside Google, it's really hard to figure out what the problem is when using JAX and PyTorch/XLA. This has been the major reason for low adoption of these custom accelerators.

But, neither of the frameworks is effective on the other category of hardware. When you choose a framework, you get into a vendor/platform lock-in. A simple mental model is:

- PyTorch → General purpose accelerators (GPU)
- JAX or PyTorch/XLA → TPU, Trainium, and other pure ML accelerators

There's a need for a framework or layer of clean abstraction that supports true platform portability for folks who want to build models from scratch and optimize for compute costs.


## Business Implications
Google is already aware of this problem. While there hasn't been a good solution at the software layer, this isn't necessary. There's a meaningfully large segment of the market that runs on JAX. Anthropic and Google both leverage this framework for their models. [OpenAI](https://openai.com/index/introducing-gpt-5-5/) and Meta are the other big model builders with meaningful traffic.

Meta uses a combination of both paradigms. Given the fact that they don't build their own hardware today, this is their best bet to manage capacity. But, this approach is **very expensive due to the portability issue**.

Given the high demand for AI compute and the fact that we will have a limited number of foundational model builders, GCP has been funding engineering teams that convert open-source models into JAX/TPU-compatible options that can be primarily used for inference and fine-tuning use cases by the customer. [Maxtext](https://github.com/AI-Hypercomputer/maxtext) is the library that is being used by Google to power this use case.


Given that a significant amount of AI adoption will be driven in the near future and Google is actively pursuing goals to improve TPU adoption, this space will continue to be highly competitive and critical to watch.

