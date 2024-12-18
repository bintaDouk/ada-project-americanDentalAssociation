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

## Inspect genre groups

<iframe class="toggle-frame" src="images/Q1/genregroups_numberwars.html" width="900px" height="700px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images/Q1/genregroups_battledeaths.html" width="900px" height="700px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>


## World Maps for Analyzed Conflicts
In order to provide a quick overview of the wars we are analyzing, we provide some initial plots, showing the world map for the opposing countries for each one of the 4 conflicts:

<iframe class="toggle-frame" src="images\Q2\countries_World_War_II.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\countries_Korean_War.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\countries_Cold_War.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\countries_Vietnam_War.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>

# Examining Storytelling Variations in War Films
While our previous analysis revealed distinct patterns in genre production across different countries, a deeper examination of narrative construction within the same genre warrants investigation. Our analysis will focus exclusively on war cinema as it provides a unique window into how different nations process, interpret, and memorialize shared historical events through film. War movies are particularly revealing because they often reflect not only a country's historical perspective but also its contemporary values, national identity, and relationship with military conflict. 

We isolated war films specifically depicting our four conflicts of interest and identified their respective sides. Unfortunately, given the limited number of movies produced about the Vietnam War and the Korean War, we have decided to focus exclusively on the Cold War and World War II.

<iframe src="\number_of_war_movies.html" width="100%" height="800px" frameborder="0"> </iframe>


## Movies Timeline
In this third section of the analysis, we filter the movies by looking at the summaries from the `Movies` dataset, and for each war we look to how many movies about it were released over the course of the years.

<iframe class="toggle-frame" src="images\Q2\movies_timeline.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>

The plot shows a large area associated to movies related to `World War II`, much larger than that of all other conflicts combined. This highlights the influence a conflict of such scale has had on the world even further in the future.   
A more in-depth inspection of the graph shows how, despite the general movies trend are characterized by an overall increase in movies produced every year, the peak in production of WWII movies has peaked during the conflict itself, to then decrease gradually over time to then settle between 10-15 movies a year in the XXI century.   
Movies on the `Vietnam War` were not produced inconsistently across all years starting from the war, reaching their peak in 2005 with 9 movies.   
The `Korean War` has had its highest movies production in the period right after the war, in the 1950s, after which it hasn-t received much attention in the cinematographic world, achieving at most 3 movies per year ever since.   
Finally, contrary to our expectations, the `Cold War` itself didn't get much attention during the course of the years, with no more than 4 movies produced in a given year making it the lowest in our analysis.

## Comparative Genre Analysis of Movies
In this section we perform a comparative analysis between the countries on either side of the conflicts, by analyzing the genre distribution of movies filtered by some specific criteria.      
First we provide an analysis of the geographical connotation of the influence of these events on the movies produced, by filtering our dataset based on the movies released in a historical period around each of the analyzed war, and check what is the movie genre of the movies depicting countries from either side of the conflict.   
We plot our results in two barplots, one for each side of the war, each one showing not only the genre distribution for that period of time but also the genre distribution over the whole dataset, to provide through comparison additional information about the way this sentiment changed overtime.   

<iframe class="toggle-frame" src="images\Q2\genres_year_World War II.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\genres_year_Korean War.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\genres_year_Cold War.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\genres_year_Vietnam War.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>

During `World War II`, Drama and Black-and-White films dominated the genre landscape on both sides. On Side 1, genres like War Films, Adventure, and Romance Films were prominent, reflecting themes of heroism and human struggle. On Side 2, Propaganda Films and Combat Films emerged, alongside Thrillers and Costume Dramas, showcasing narratives aligned with wartime efforts and cultural expression. Compared to their total distributions, both sides saw significant spikes in war-focused genres, with Side 2 emphasizing propaganda and Side 1 highlighting wartime romance and heroism.   
During the `Korean War`, Drama remained the top genre for both sides, but their focuses diverged slightly. On Side 1, there was a strong emphasis on Romance Films and Black-and-White films, along with notable contributions from Adventure and War Films. Meanwhile, Side 2 leaned more into Thriller, Combat Films, and Costume Drama, highlighting themes of conflict and cultural representation. Compared to their overall genre distributions, both sides showed increased focus on war-related genres, with Side 1 emphasizing romanticized narratives and Side 2 reflecting more action-driven storytelling.   
During the `Cold War`, Drama dominated both sides, reflecting its enduring role in storytelling. On Side 1, genres like Thriller, Action, and War Films were significant, alongside a notable presence of Political Drama and Science Fiction, which may mirror societal tensions of the time. On Side 2, Spy films and Thrillers stood out more, alongside Period Dramas, suggesting themes of espionage and historical reflection. Compared to the overall dataset, both sides experienced a spike in war-related and suspense genres during the Cold War, aligning with its geopolitical anxieties.   
The `Vietnam War` era saw Drama as the dominant genre on both sides. On Side 1, genres like Action, Thriller, and War Films took center stage, emphasizing the conflict's intensity. Meanwhile, Side 2 also featured Thriller prominently but included genres like Comedy and Political Drama, reflecting a mix of conflict-focused and escapist narratives. Compared to the overall dataset, both sides saw an increased emphasis on war and political genres during this period, with Side 2 incorporating more variety in tone through comedy and satire.   

A second analysis was performed by focusing instead on movies depicting the war, filtered from our original dataset by looking for the names of the war (opportunely cleaned). Once again we analyze the difference in distribution between various genres, but this time the distinction between the two sides is done by looking at the country the movie is produced in.

<iframe class="toggle-frame" src="images\Q2\genres_summary_World War II.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\genres_summary_Korean War.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\genres_summary_Cold War.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>


A fisrt thing easy to notice is the fact that for both `Cold War` and `Korean War` one side has much fewer movies compared to the other , while for the `Vietnam War` not enough movies were found for one of the two sides, hence no plot was produced.   
This leads to a the results relative to these plots less significant overall, but we decided to still mention them for completeness.   
`World War II` movies prominently feature Drama, War Films, and Period Pieces across both sides. Side 1 strongly highlights Drama, War Films, and Black-and-White genres, emphasizing the historical and serious tone of the conflict. Side 2 includes World Cinema, Japanese Movies, and Period Pieces, reflecting regional diversity in storytelling. Compared to the overall dataset, genres such as Period Piece and Black-and-White are significantly elevated, underscoring the historical importance and widespread cinematic coverage of World War II.   
Movies about the `Korean War` highlight Drama, War Films, and Action on both sides. Side 1 emphasizes Drama as the leading genre, with War Films and Action genres also receiving considerable attention. On Side 2, Chinese Movies and World Cinema stand out, reflecting regional influences and storytelling traditions. Compared to the total dataset, War Films and Chinese Movies gain prominence, showcasing the somber tone and regional cinematic focus associated with the Korean War.   
Movies about the `Cold War` display a strong focus on Thriller, Spy, and Action genres. On Side 1, Drama and Thriller dominate, with notable emphasis on Spy films reflecting political tension and espionage themes. On Side 2, Thriller and Spy genres stand out even more prominently, with Action Thrillers receiving a significant share. Compared to the overall dataset, genres such as Spy and Political Thriller become far more prevalent, capturing the paranoia and secrecy characteristic of the Cold War.   

## Geographical Analysis of Movie Production
This final section of geographical analysis is made through the use of sunburst charts, which show how many movies about each war were produced by either side, entering in details of the single countries from either (or neither) side.   

<iframe class="toggle-frame" src="images\Q2\country_piechart_World War II.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\country_piechart_Korean War.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\country_piechart_Cold War.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\country_piechart_Vietnam War.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>

A comment which can be made for each of these graphs is that United States take up the largest slice of the chart divided by countries, and this is largely due to the fact that the United States contribute in the largest amount to all movies produced, regardless of the topic.    
Entering more in detail, regarding `World War II`, we can see that the largest forces of the conflict lead the movie production, with the USA having released more than 400 movies, the UK more than 100 and countries such as France, Germany, Italy and Japan all with more than 20 movies each. On top of this, the massive influence of the conflict can also be seen from the large number of smaller countries having released some movies about it, with movies released in more than 50 countries in total!   
Once again, for the `Korean War`, most of the movies were produced by the USA, but if we exclude its contribution we can see that South Korea, one of the countries directly involved in the conflict, is the largest producer of movies on the conflict. Follow the UK and China, alongside some other Asian countries.   
Moreover, we see that for the `Cold War` the largest part of the movies were produced by countries not directly involved in the conflict, showing how such a conflict has impacted the whole world and not only the two opposing sides. As stated before, the USA contribute to the largest part of the movies, while Russia, despite being one of the two involved countries, only amounts to a single movie in our chart, surpassed by the large european countries such as Germany, UK and France.   
Finally, for the `Vietnam War` we can see from the chart that no movies about it were released in Vietnam, only country directly involved in the war as "Side 2" in our dataset, while the movies are almost equally distributed among the various countries (as usual, exception made for the USA).


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


