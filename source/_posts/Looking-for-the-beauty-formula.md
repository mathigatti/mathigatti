---
title: Looking for the formula of beauty
date: 2019-08-05 18:41:46
tags: cellular-automata
cover_image: images/pattern2.jpg
description: Automatic aesthetic classification for massive art production using generative systems
---

Some time ago I created [this](https://gist.github.com/mathigatti/439a0e81556f2698c7db4f41189d201f) small script to convert numbers into patterns. I'm not going to explain how the script works in detail but it's inspired on [Stephen Wolfram's Elementary Cellular Automatas](https://en.wikipedia.org/wiki/Elementary_cellular_automaton) which converts numbers like 30 into binary (00011110) and then interprets the digits as turning ON or OFF of 8 different basic rules (In that case there are 4 rules activated, rule 4, 5, 6 and 7) that define when to turn ON and OFF a pixel in the image.

<img src="https://ucarecdn.com/a4323adb-4c13-4c4f-a32d-97f86468a1f0/" width="100%" border="5" />

Using this I can generate an infinite number of different patterns, the problem is that most of them are not really interesting and I have no time to check them one by one. That's why in this post I explain how I tried to automate the process of finding out the most interesting/beautiful cellular automatas.

## Clusterization
My goal is to group the patterns by its beauty. I do this using a clustering algorithm based on features frequently attributed to beauty such as fractal dimensionality and compression efficiency. You can read more about these features here: [Forsythe, Alex, et al. "Predicting beauty: fractal dimension and visual complexity in art." British journal of psychology 102.1 (2011): 49-70](https://www.researchgate.net/publication/49761486_Predicting_beauty_Fractal_dimension_and_visual_complexity_in_art).

### The Code
The full code is [here](https://github.com/mathigatti/CellularAutomataClassification) but I also uploaded it into colab [here](https://colab.research.google.com/drive/1FFNRZuRW7lkKi1LnbMR-d8KI0EADl871) so you can run everything from your web browser.

### Defining clustering attributes
First I define the previously mentioned attributes, fractal dimension (Code taken from [here](https://gist.github.com/rougier/e5eafc276a4e54f516ed5559df4242c0)) and compression score (The weight of a raw tiff image over its weight compressed as a gif image).

### Clustering
There are several clustering algorithms, you can choose the one that best fits your use case.

<img src="https://ucarecdn.com/a6d86443-9072-44f0-b032-ccede2fe4073/" width="100%" border="5" />

In my case I ended up using Agglomerative Clustering which captures better the clusters generated by this dataset.

You need to specify the number of clusters, I tried with different numbers, at the end I chose 5 since it grouped them well from null patterns to crazy and chaotic ones.

<img src="https://ucarecdn.com/4fe8f003-2d3f-4296-8c24-9283bb587e2b/" width="100%" border="5" />

## Results
Here I show some samples of each cluster. I sorted them from the simplest ones to the most complex. As you can see this method is useful to identify and discard uninteresting patterns such us the ones from the Cluster 0. It's also useful to identify the most beautiful patterns, most of the best patterns I found are from the Cluster 3, the one with big complexity but not the biggest fractal dimension.

### Cluster 0: Null patterns
<img src="https://ucarecdn.com/6f41e3ce-45dd-4b8e-aa00-b96fde1f09b4/" width="100%" border="5" />

### Cluster 1 and 2: Almost Null Patterns
<img src="https://ucarecdn.com/565971db-1047-4100-92aa-c4feca3697ef/" width="100%" border="5" />

### Cluster 3: Intermediate complexity / The most interesting and beautiful ones
<img src="https://ucarecdn.com/8f4a6dcf-b501-4b8a-bcc0-0b4822b6c26e/" width="100%" border="5" />

### Cluster 4: Too crazy and chaotic patterns
<img src="https://ucarecdn.com/b7066ecc-a054-4d34-9ec6-e9ef521fad85/" width="100%" border="5" />
