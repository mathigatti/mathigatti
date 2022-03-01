---
title: Spanish GPT-2 at Hugging Face
date: 2021-05-19 12:38:18
tags:
summary: Release of the best text generator systems in spanish up to date 
description: Release of the best text generator systems in spanish up to date
---

For the last year I've been participating into Deep-ESP an NLP community focused on developing tools for the spanish language. This week after several months of work from several members of the community we presented the best public models, to date, for the generation of texts in Spanish.

To train them we use 3 gb of texts from Wikipedia and 6 gb of books (literature, essays and outreach). Although the generations are not always perfect, these models work better than those trained by OpenAI, since the tokenizer of the original models, having been trained with texts in English, creates a bottleneck for Spanish.

The models learned the grammatical rules of Spanish perfectly, and some generations have such an amazing quality that they seem indistinguishable from a human-generated text. However, sometimes the generations do not have semantic coherence.

The work was leaded by Jose Ortiz Fuentes and Alejandro Oñate Latorre, more details [here](https://www.linkedin.com/in/jorgeortizfuentes?miniProfileUrn=urn%3Ali%3Afs_miniProfile%3AACoAACrZzdkBb6YPYGth59X2PssLMpViTZfxZdA&lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_recent_activity_details_shares%3BBxjjVbvFSCKTNGjA%2F5xDbg%3D%3D&licu=urn%3Ali%3Acontrol%3Ad_flagship3_profile_view_base_recent_activity_details_shares-original_share_actor_container&lici=xATHWtMYdR7F8cDxuJqRWw%3D%3D).

You can try the models in [this Colab](https://colab.research.google.com/drive/1O6dii5zQVWON1pTrDYmNdVy4tF9ZqBB0) and you can see more details about the models in this repository at [Hugging Face](https://huggingface.co/DeepESP).

For fine tuning the model I developed a colab notebook, you can see [there](https://colab.research.google.com/drive/1WF-_iiSEueNX4htlhNe2UOd5XjxiIFlC) a test to generate horoscope texts.