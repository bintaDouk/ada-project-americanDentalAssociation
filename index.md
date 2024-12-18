---
layout: page
title: Cinematography in Times of Crisis
subtitle:  Exploring the Impact of Global Events on Film Genres and Public Preferences
cover-img: /assets/img/cover_img.jpeg
thumbnail-img: /assets/img/cover_img.jpeg
share-img: /assets/img/cover_img.jpeg
use-site-title: true
---

## Background and motivation
Ever since the begining of cinematography, movies have often been a reflection of reality. Whether it is through romance stories or tragedies, fiction has been used as a way to mirror real life situations.
This tendency also applies to crises, as they are major events that impact the socio-economic status of the world, as well as peoples' daily lives. It is only natural to ask ourselves how these very particular events are mirrored in movies, and how well these depictions are received by the public.

Using the CMU Movie Dataset, we will answer the following research questions:
1. How do global crises and significant world events shape film production, themes, and public preferences?
2. How do movie genre preferences differ between countries in conflict or those experiencing similar global events?
3. How does the portrayal of historical events in movies vary based on the country of production?
4. How do global events like natural disasters, pandemics, and wars influence public preferences for specific themes and genres?

Our analysis starts from three main datasets:
* The [CMU Movie Summary Corpus Dataset](https://www.cs.cmu.edu/~ark/personas/), containing movie summaries, actors and other information
* The [IMDb Dataset](https://www.kaggle.com/datasets/ashirwadsangwan/imdb-dataset), containing movie ratings and other information
* The [Correlates of War Dataset](https://correlatesofwar.org/data-sets/cow-war/), containing a list of major historical conflicts
After some quick initial filtering, we merged the CMU and IMDb datasets to generate a bigger `Movies` dataset better suited for our needs, and we filtered the `Wars` datasets to only contain the conflicts relevant to the time period corresponding to the movies we are considering.   
On top of that, we decided to focus our analysis on a reduced set of wars, being `World War II`, `Korean War`, `Cold War` and `Vietnam War`, which from a quick initial analysis seemed to have the largest related information in the movies dataset.

## World Maps for Analyzed Conflicts
In order to provide a quick overview of the wars we are analyzing, we provide some initial plots, showing the world map for the opposing countries for each one of the 4 conflicts:

{% raw %}
<iframe class="toggle-frame" src="images\Q2\countries_slideshow.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
{% raw %}

## Movies Timeline
In this third section of the analysis, we filter the movies by looking at the summaries from the `Movies` dataset, and for each war we look to how many movies about it were released over the course of the years.

<iframe class="toggle-frame" src="images\Q2\movies_timeline.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>

## Geographical Analysis of Movies


## Portrayal of historical events accross perspectives
This part of the Analysis will mainly focus on the sentiment associated with movies for the four specific conflicts retained earlier for ... 
* World War II
* Korean War
* Cold War
* Vietnam War

TODO: add the first part with the global sentiment analysis 
### The shifting sentiment towards organizations during an world-scale conflict.
The way conflicts are represented in cultural narratives often reveals underlying societal attitudes, biases, and historical contexts. In this part of the study we applied entity-level sentiment analysis to entities tagged as 
Now that we have overall information on the sentiment about different war, we can delve into it deeper and try to similar actors have similar sentiment in different sides for a given conflict.  
We perform entity-level sentiment analysis, in order toextract the sentiment associate with a particular entity. For a given conflict we select entities that ...
WWII: Nazis, 
Korean War:

<iframe class="toggle-frame" src="heatmap_0.html" width="800px" height="530px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>


