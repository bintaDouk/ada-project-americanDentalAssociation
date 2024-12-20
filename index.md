---
layout: page
title: Cinematography in Times of Crisis
subtitle:  Exploring the Impact of Wars and Global Events on Film Production and Public Preferences
cover-img: /assets/img/téléchargement.jpg
thumbnail-img: /assets/img/téléchargement.jpg
share-img: /assets/img/téléchargement.jpg
use-site-title: true
---
<style>
.carousel-control-prev-icon,
.carousel-control-next-icon {
  background-color: rgba(0, 0, 0, 0.5); /* Add a semi-transparent black background */
  border-radius: 50%; /* Make the buttons circular */
  width: 40px; /* Adjust width */
  height: 40px; /* Adjust height */
}

.carousel-control-prev,
.carousel-control-next {
  position: absolute;
  top: 50%; /* Center vertically */
  transform: translateY(-50%);
  width: auto; /* Adjust width to fit the button */
}

.carousel-control-prev {
  left: -5%; /* Move left button further to the left */
}

.carousel-control-next {
  right: -5%; /* Move right button further to the right */
}

.carousel-indicators button {
  background-color: black; /* Make carousel indicators visible */
  width: 12px; /* Adjust width */
  height: 12px; /* Adjust height */
  border-radius: 50%; /* Make indicators circular */
}
</style>
## Background and motivation
Ever since the begining of cinematography, movies have often been a reflection of reality. Whether it is through romance stories or tragedies, fiction has been used as a way to mirror real life situations.
This tendency also applies to wars and other crises, as they are major events that impact the socio-economic status of the world, as well as peoples' daily lives. It is only natural to ask ourselves how these very particular events are mirrored in movies, and how well these depictions are received by the public. In our study we focus on interstate wars and discover their influence of genre production and then extend our analysis to other crises and the public's preference.

Using the CMU Movie Dataset, we will answer the following research questions:
1. How do wars shape film production, themes, and public preferences?
2. How do movie genre preferences differ between countries at war?
3. How does the portrayal of historical events in movies vary based on the country of production?
4. How do global events like natural disasters, pandemics, and wars influence public preferences for specific themes and genres?

Our analysis starts from three main datasets:
* The [CMU Movie Summary Corpus Dataset](https://www.cs.cmu.edu/~ark/personas/), containing movie summaries, actors and other information
* The [IMDb Dataset](https://www.kaggle.com/datasets/ashirwadsangwan/imdb-dataset), containing movie ratings and other information
* The [Correlates of War Dataset](https://correlatesofwar.org/data-sets/cow-war/), containing a list of major historical conflicts
After some quick initial filtering, we merged the CMU and IMDb datasets to generate a bigger `Movies` dataset better suited for our needs, and we filtered the `Wars` datasets to only contain the conflicts relevant to the time period corresponding to the movies we are considering.   
On top of that, throughout the project decided to focus our analysis on reduced sets of wars are identified in the project.

## Inspecting genre groups

The analysis in the first section examines how various wars influenced the production of different movie genres over time. By analyzing genre proportions, correlations with war-related metrics, co-occurrence networks, and significant changes in genre distributions, this analysis uncovers key insights about the interplay between historical conflicts and cinema production.

To lead a preliminary inspection of war-related genres and chose specific wars for further analysis, three groups of of a few specfic genres were formed: war-related genres, political genres, dystopian genres.

**Military** (War-related) genres: War Film, Antiwar, Superhero, Spy

**Political** genres: Political Thriller, Political Satire, Political Cinema, Political Drama

**Dystopian** genres: Dystopia, Apocalyptic and Postapocalyptic Fiction

The war-related genres are the ones that we identified eariler as genres either related to war or military propaganda. Political genres were chosen to reflect the geopolitical side of wars. Dystopian and Apocalyptic genres were chosen as these genres often talk about war-related aplocalypses as well as dystopian societies based on military rule.

In the plots below, the proportion of movies in a genre group released each year (in relation to the total movies released) are presented for the whole timeline. 

<div id="carouselExample" class="carousel slide" data-bs-ride="carousel">
  <!-- Indicators -->
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#carouselExample" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#carouselExample" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#carouselExample" data-bs-slide-to="2" aria-label="Slide 3"></button>
    <button type="button" data-bs-target="#carouselExample" data-bs-slide-to="3" aria-label="Slide 4"></button>
  </div>

  <!-- Slides -->
  <div class="carousel-inner">
    <div class="carousel-item active">
      <iframe src="images/Q1/trend_numwars_military.html" width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src="images/Q1/trend_numwars_antiwarmilitary.html" width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src="images/Q1/trend_numwars_political.html" width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src="images/Q1/trend_numwars_dystopian.html" width="100%" height="600" frameborder="0"></iframe>
    </div>
  </div>

  <!-- Controls -->
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExample" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExample" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

From the military genre production trends, we can see that the biggest spike can be associated with WW2 - it reached its peak in 1943, around the middle of the war. However, some other noticeably spikes happened in 1966 and 1958, a year in the beginning of a full-scale Vietnam War and a year when it was still a Civil War with some indirect involvement of other countries. However, the Cold War was also ongoing at the time. Since the Cold War's official timeline is around 40 years, it is difficult to associate specific spikes with it without inspecting the timeline of the smaller events within it. Although we can note that some signigicant events like Cuban Missile Crisis and Prague Spring happened at that time, they are not included in this analysis.
In the political genres figure we observe a lot of oscillation, so the only observation we can make from the plot is the overall growth of the political genres from 1930s to 1990s.
In the dystopian genres, the trend is pretty stable over time except for the two noticeably peaks in 1974 and 1990, at the end Vietnam War and at the end of the Cold War.

We were interested in the times when spikes appeared for each genre group. Thus, the peaks for these genre groups were inspected, and a list of events in the 2-year window around the peak year was formed to analyze further. The events that were chosen appeared in at least two of the final lists and had more than 1000 movies released in their timeline (a sperate group of War movies without the Antiwar was created as well, since the movies specifically labelled Antiwar are of a different nature). The comprehensive list of events to analyzed was yielded:

- `World War II`
- `Vietnam War`
- `Second Laotian War`
- `Cold War`
- `Iran-Iraq War`

Note, however, that the Second Laotian War's timeline is contained withing the timeline of the Vietnam War, so the analysis is conducted for the Vietnam War only but can be applied to both.

## Finding Correlations
In this section, for the chosen wars' time window (the timeline with a 2 year window before and after), we inspected the correlation of the genres released with the number of ongoing wars per year and yearly battle deaths. The inspection was conducted for the genres groups mentioned before. And moreover, for these genres:
**War film, Spy, Superhero, Romance Film, Romantic drama, Family Film, Romantic comedy, Comedy, Fantasy, Thriller, Horror, Drama, Social issues, Antiwar, Disaster**. 

Moreover, another genre group was created:

**Positive** genres: Family Film, Romance Film, Romantic Comedy, Fantasy, Romantic Drama.

The range of genres was increased in order to include the more widespread genres, such as Drama, and inspect negative genres, such as Horror and Thriller, and postive genres. One of the objectives of the analysis was to identify not just correlation with war-related genres or horror-related genres but with positive genres that are associated with entertainemnt and/or escapism.

The plots below showcase the scatter plots for genre proportions vs. number of ongoing wars or vs. battle deaths. The plots also contain the Pearson correlation value, the p-value and the OLS line. For the analysus the condifence interval of 95% (alpha = 0.05) was chosen. The plots presented were sorted based on the p-value below 0.05 and correlation value above 0.45.

**Correlations for the Second World War (1939-1945)**

*Battle Deaths:*

Family Film: correlation value = -0.72, p-value = 0.0167, R-squared = 0.524.

Horror: correlation value = 0.84, p-value = 0.00137, R-squared = 0.6976.

Drama: correlation value = -0.6089, p-value = 0.0468, R-squared = 0.37.

 We can infer that as the battle deaths grow, the number of family films produced decreases while horror movies' production grows. Drama decreases with the growth but this model's fit is weak. Note, however, that the increased battle deaths for World War II might skew the results.

<!-- First Carousel -->
<div id="carouselcorrwar" class="carousel slide" data-bs-ride="carousel">
  <!-- Indicators -->
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#carouselcorrwar" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#carouselcorrwar" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#carouselcorrwar" data-bs-slide-to="2" aria-label="Slide 3"></button>
    <button type="button" data-bs-target="#carouselcorrwar" data-bs-slide-to="3" aria-label="Slide 4"></button>
  </div>

  <!-- Slides -->
  <div class="carousel-inner">
    <div class="carousel-item active">
      <iframe src='images/Q1/corr_batdeath_Drama_1937-1947.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/corr_batdeath_Family_Film_1937-1947.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/corr_batdeath_Horror_1937-1947.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
  </div>

  <!-- Controls -->
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselcorrwar" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselcorrwar" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

**Correlations for the Vietnam War (1965-1975)**

*Number of Wars:*

Family Film: correlation value = -0.6108, p-value = 0.015, R-squared = 0.373

*Battle Deaths:*

Fantasy: correlation value = -0.5166, p-value = 0.0486, R-squared = 0.2669

Due to low values of R-squared, it is hard to make conclusions but we may say that the number of Family Films produced decreases as the number of wars increases. While Fantasy Films produciton decreases with the increase of Battle Deaths.

<script>
function showFrame(frameId) {
  // Get all iframes with the toggle-frame class
  var frames = document.getElementsByClassName('toggle-frame');

  // Hide all iframes with the toggle-frame class
  for (var i = 0; i < frames.length; i++) {
    frames[i].style.display = 'none';
  }

  // Show the selected iframe
  var frame = document.getElementById(frameId);
  frame.style.display = 'block';
}
</script>

<!-- Create the buttons -->
<button class="button" style="margin: 8px 0; width: 20%; margin-left: 130px; margin-right: 5px" onclick="showFrame('corrvietbat')">Battle Deaths</button>
<button class="button" style="width: 20%; margin-right: 5px;" onclick="showFrame('corrvietnum')">Number of Wars</button>

<iframe class="toggle-frame" src="images/Q1/corr_batdeath_Fantasy_1963-1977.html" width="800px" height="600px" frameborder="0" position="relative" id="corrvietbat" style="display: block;"></iframe>
<iframe class="toggle-frame" src="images/Q1/corr_numwars_Family_Film_1963-1977.html" width="800px" height="600px" frameborder="0" position="relative" id="corrvietnum" style="display: block;"></iframe>

**Correlations for the Cold War (1949-1989)**

*Number of Wars:*

Romantic Comedy: correlation value = -0.4506, p-value = 0.00189, R-squared = 0.203

The R-squared is quite low, so it is hard to make a concrete conclusion but the suggestion is that the Romantic Comedy production decreases as the number of wars grows.

<iframe src='images/Q1/corr_numwars_Romantic_comedy_1947-1991.html' width="100%" height="600" frameborder="0"></iframe>

**Correlations for the Iran-Iraq War (1980-1988)**

None of the correlations yield a small enough p-value.

**Correlations for the timeline (1950-2012)**

Correlations were first calculated for the full timeline of 1931-2012 and yilded very low p-values for War Film, Military Movies, Military & Antiwar Movies. However, most battle deaths recorded are below 300,000, while the Battle Deaths for the WW2 are recorded as more than 2 million yearly (approximation done by dividing the duration of a war by the total battle death). So these values will not be reported as significant, even though it can be said that the proportion of War movies had the largest spike at the time. Consequently, a cutoff of 1950 was created since the spike in battle deaths during the WW2 significantely affected the results.

*Number of Wars:*

Superhero: correlation value = -0.4841 p-value = 5.8151e-05, R-squared = 0.234

Romantic comedy: correlation value = -0.5606, p-value = 1.7646e-06, R-squared = 0.314

The R-squared are low again but for Romantic comedy it may be said that it decreases in production as the number of wars increases.

<div id="carouselcorr5" class="carousel slide" data-bs-ride="carousel">
  <!-- Indicators -->
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#carouselcorr5" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#carouselcorr5" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#carouselcorr5" data-bs-slide-to="2" aria-label="Slide 3"></button>
    <button type="button" data-bs-target="#carouselcorr5" data-bs-slide-to="3" aria-label="Slide 4"></button>
  </div>

  <!-- Slides -->
  <div class="carousel-inner">
    <div class="carousel-item active">
      <iframe src='images/Q1/corr_numwars_Superhero_1950-2012.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/corr_numwars_Romantic_comedy_1950-2012.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
  </div>

  <!-- Controls -->
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselcorr5" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselcorr5" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

**Correlations for the the End of 20th - Beginning of 21st Century**

*Number of Wars:*

Social Issues: correlation value = -0.5008, p-value = 0.0149, R-squared = 0.2508

Political Movies: correlation value = -0.548, 0.0067, R-squared = 0.3

The R-squared are low again but for Romantic comedy it may be said that it decreases in production as the number of wars increases.

<div id="carouselcorr4" class="carousel slide" data-bs-ride="carousel">
  <!-- Indicators -->
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#carouselcorr4" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#carouselcorr4" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#carouselcorr4" data-bs-slide-to="2" aria-label="Slide 3"></button>
    <button type="button" data-bs-target="#carouselcorr4" data-bs-slide-to="3" aria-label="Slide 4"></button>
  </div>

  <!-- Slides -->
  <div class="carousel-inner">
    <div class="carousel-item active">
      <iframe src='images/Q1/corr_numwars_Social_issues_1990-2012.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/corr_numrwars_Political_1990-2012.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
  </div>

  <!-- Controls -->
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselcorr4" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselcorr4" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

To sum up, while the model often fit weakly or moderately, we can note a few things:

As the number of wars increased, the Family Film production decreased during the times of the Vietnam War, the Romantic comedy production decreased during the second half of the 20th century and for most of the timeline as well. Plotical Movies and Social Issues films decreased for the 1990-2012 timeline.
As the number of battle deaths increased, Family Film, Horror, and Drama decreased for the WW2 timeline, but result is skewed. Fantasy decreased for the Vietnam War timeline.
All in all, we see a decrease for all kinds of movie genres with the increase of number of ongoing wars and battle deaths. We can note the Family Film and Romantic comedy appear more than once, which could suggest that the wars affect their production greatly.

**Plotting the network**

For some inspection, the network for War Film was created, which is the movie genres that were mentioned together with War Film more often. Some of the observations that can be made from the network are that War Films are often associated with historical or documentary films, with action films, and sometimes with political genres. What is interesting for our analysis is that Comedy, Romance films and Romantic drama often go together with War Films, thus, our objective to inspect the production of more entertaining and escapistic genres may not be supported in full by inspecting these "positive" genres, as they are often included in movies about war as well.

<iframe src="images/Q1/network.html" frameborder="0" width="100%" height="600"></iframe>

## Significant Changes in Genres for the Chosen Wars

Significant changes in genre distribution were defined for the chosen wars by using chi-square testing. The window before and after the war defined as 5 years.

**World War II**

Some of the changes can be associated with cinematography trends: Back and White, Film Noir, PreCode (Pre-Code Hollywood was an era in the American film industry that occurred between the widespread adoption of sound in film in the late 1920s), and World Cinema. However, it is important to note that the origins of Film Noir as a genre included dark themes and after the war the genre grew and started depicting moral ambiguity, physchological effects of war and other introspection and reflection on the war.

Some interesting observations here also incldue that the War Film genre increases greatly during the war but in the aftermath drops to its previous level. A similar thing happened to the Horror genre - moreover, its production after the war drops to lower than before the event. Thriller and Psychological Thriller, on the other hand exprience growth during and then after the war as well. The production of Drama drops during the war and increases back afterwards. Propaganda movies were on an extreme rise during the war, which aligns with the nature of the World War II and propagandistic goals of Nazi Germany.

**Cold War**

As discussed earlier, the Cold War spans a very large timeline, moreover the "before" time for it includes the World War II, so it is hard to make any concrete analysis from the resulting graph. Most of the changes are explained the trends in cinematography. We can say, however, that the War Films experienced a drop after the Cold War ended.

**Vietnam War**

Here we once again see an increase in Thriller movies production and here it is joined by Action movies. Interestingly, the War Film genre has not experienced significant changes, even though its peaks were identified to happen at the time as well. Romantic comedy genre has significantly decreased and noteably, for some timelines we have seen before a correlation - that Romantic comedy production decreases as the number of wars grows. It is interesting to see a great increase in Matrial Arts Film, which could be affected by the events of the war, as Martial Arts are usually associated with Asian culture.
Genres like British New Wave and Kitchen Sink Realism (film, whose protagonists usually could be described as "angry young men" who were disillusioned with modern society) dropped in production. These genres talked about social issues but were weakly related to specific wars.

**Iran-Iraq War**

For the timeline of the Iran-Iraq, it seems like most of the significant genre production changes were influenced by trends in cinematography and new genres originating at the time. This could also be explained by the fact that this war included much less countries than the previous war and lacked the involvement of Western countries and the United States specifically who dominate the movie market.

<script>
  let currentVisibleSet = null; // To track the currently visible set of graphs

  function showGraphs(id) {
    // Hide the currently visible set, if any
    if (currentVisibleSet) {
      currentVisibleSet.style.display = 'none';
    }

    // Show the selected set of graphs
    const selectedSet = document.getElementById(id);
    if (selectedSet) {
      selectedSet.style.display = 'block';
      currentVisibleSet = selectedSet; // Update the currently visible set
    }
  }

  // Initially hide all sets
  document.addEventListener('DOMContentLoaded', () => {
    const graphSets = document.querySelectorAll('.graph-set');
    graphSets.forEach(set => {
      set.style.display = 'none';
    });
  });
</script>

<!-- Create the buttons -->
<button class="button" style="margin: 0.5px 0; width: 20%; margin-left: 10px; margin-right: 5px" onclick="showFrame('ww2change')">WW2</button>
<button class="button" style="width: 20%; margin-right: 5px;" onclick="showFrame('coldchange')">Cold War</button>
<button class="button" style="width: 20%; margin-right: 5px;" onclick="showFrame('vietchange')">Vietnam War</button>
<button class="button" style="width: 20%; margin-right: 5px;" onclick="showFrame('iraniraqchange')">Iran-Iraq War</button>

<iframe class="toggle-frame" src="images/Q1/significantchange_WW2.html" width="1000px" height="600px" frameborder="0" position="relative" id="ww2change" style="display: block;"></iframe>
<iframe class="toggle-frame" src="images/Q1/significantchange_ColdWar.html" width="1000px" height="600px" frameborder="0" position="relative" id="coldchange" style="display: block;"></iframe>
<iframe class="toggle-frame" src="images/Q1/significantchange_Vietnam.html" width="1000px" height="600px" frameborder="0" position="relative" id="vietchange" style="display: block;"></iframe>
<iframe class="toggle-frame" src="images/Q1/significantchange_Iran-Iraq.html" width="1000px" height="600px" frameborder="0" position="relative" id="iraniraqchange" style="display: block;"></iframe>


## Specific Genres for the Chosen Wars
**World War II**

Military Genres:
For military mvoies we can see an almost normal distribution in the plot for World War II. The War Film genre especially looks like it follows normal distribution with its peak in 1943. The spy movies also were at the highest in the middle of the war (1942 and 1943). 

Positive Genres:
The positive genres seem to be quite stable over the timeline with a vary similar total proportion for each year. 

**Cold War**

Military Genres:
Multiple the events of signigicant importance within the Cold War happened in the 1950s and 1960s, which could explain some increase in the War Film genre. However, as we know, the Vietnam War also starts in the 1960s, so the results can be affected by both of these. Another rise closer to the 1980s, for example, could be associated with the war in Afghanistan, which is associated with the Cold War as well. However, these observartions are highly theoretical and could be a base for a more specific Cold War analysis in another study.

Positive Genres:
Once again we see that the positive genre production is stable over time even for such a extensive timeline, except for a drop from around 1966, which will be mentioned later.

**Vietnam War**

Military Genres:
From 1963 to 1971 it seems like the Spy genre is close to normal distribution, which could be related to the nature of the Vietnam War. It is important to note that the U.S. was involved in the Civil War and events in Vietnam before it officially joined it. The War Film genre was quite stable in the beginning and dropped in the middle.

Positive Genres:
Interestingly, as mentoined earlier here the Positive Genres are not stable and they slowly decrease in produciton up until 1974, mostly due to the Comedy genre. Thus, it could be hypothesized that this war specifically had an unusual effect on the Comedy genre.

**Iran-Iraq War**

Military genres:
The production of War Film had a noticeably peak in 1979 (note: Soviet invasion in Afghanistan) but stayed approximately the same for the other years. So we can assume the Iran-Iraq War did not affect the genre greatly.

Dystopian genres:
There is definitely a noticeable increase in the genre of Dystopia in the 1990 but it is hard to tell if it influenced by cinematographic trends, the war or other events.

Positive Genres:
The positive genres have stable production over time.

Most of the time the positive genres have the same proportion across the timeline with an exception of a Vietnam War or the 1960s and 1970s (included multiple political events within the Cold War such as Cuban Missile Crisis, Fall of the Berlin Wall, Prague Spring). We can conclude that positive events are usually stable in production and are not highly affected by wars. However, the found exception is an interesting observation that could be analysed further.
The political genres do not lead to any conclusions and contain a lot of oscillations. The conclusion is that the political genres are not affected by interstate wars but could be affected by other global events.
The dystopian genres also do not lead to any specific conclusion and do not seem to be influenced by wars. We can also note that these genres are quite modern and lack in produciton in the 20th century.
The military genres often seemed to follow a normal distribution during the big 20th century wars. This implies that military-related genres rise as the war starts, peak in the middle of the war and decrease again. However, for Iran-Iraq War the pattern was not identified, which could be due to the involvement of Western Countries and the scale of the event.

<script>
  let currentVisibleSet = null; // To track the currently visible set of graphs

  function showGraphs(id) {
    // Hide the currently visible set, if any
    if (currentVisibleSet) {
      currentVisibleSet.style.display = 'none';
    }

    // Show the selected set of graphs
    const selectedSet = document.getElementById(id);
    if (selectedSet) {
      selectedSet.style.display = 'block';
      currentVisibleSet = selectedSet; // Update the currently visible set
    }
  }

  // Initially hide all sets
  document.addEventListener('DOMContentLoaded', () => {
    const graphSets = document.querySelectorAll('.graph-set');
    graphSets.forEach(set => {
      set.style.display = 'none';
    });
  });
</script>

<button class="button" style="margin: 0.5px 0; width: 20%; margin-left: 10px; margin-right: 5px" onclick="showGraphs('WW2')">WW2</button>
<button class="button" style="width: 20%; margin-right: 5px;" onclick="showGraphs('Cold')">Cold War</button>
<button class="button" style="width: 20%; margin-right: 5px;" onclick="showGraphs('Vietnam')">Vietnam War</button>
<button class="button" style="width: 20%; margin-right: 5px;" onclick="showGraphs('Iran')">Iran-Iraq War</button>

<div id="WW2" class="graph-set" style="display: none;">
  <iframe src="images/Q1/WW2_barplot_militaryandantiwar.html" width="1000" height="600" frameborder="0"></iframe>
  <iframe src="images/Q1/WW2_barplot_political.html" width="1000" height="600" frameborder="0"></iframe>
  <iframe src="images/Q1/WW2_barplot_positive.html" width="1000" height="600" frameborder="0"></iframe>
</div>

<div id="Cold" class="graph-set" style="display: none;">
  <iframe src="images/Q1/Cold_War_barplot_militaryandantiwar.html" width="1000" height="600" frameborder="0"></iframe>
  <iframe src="images/Q1/Cold_War_barplot_political.html" width="1000" height="600" frameborder="0"></iframe>
  <iframe src="images/Q1/Cold_War_barplot_positive.html" width="1000" height="600" frameborder="0"></iframe>
  <iframe src="images/Q1/Cold_War_barplot_dystopian.html" width="1000" height="600" frameborder="0"></iframe>
</div>

<div id="Vietnam" class="graph-set" style="display: none;">
  <iframe src="images/Q1/Vietnam_barplot_militaryandantiwar.html" width="1000" height="600" frameborder="0"></iframe>
  <iframe src="images/Q1/Vietnam_barplot_political.html" width="1000" height="600" frameborder="0"></iframe>
  <iframe src="images/Q1/Vietnam_barplot_positive.html" width="1000" height="600" frameborder="0"></iframe>
  <iframe src="images/Q1/Vietnam_barplot_dystopian.html" width="1000" height="600" frameborder="0"></iframe>
</div>

<div id="Iran" class="graph-set" style="display: none;">
  <iframe src="images/Q1/Iran-Iraq_barplot_militaryandantiwar.html" width="1000" height="600" frameborder="0"></iframe>
  <iframe src="images/Q1/Iran-Iraq_barplot_political.html" width="1000" height="600" frameborder="0"></iframe>
  <iframe src="images/Q1/Iran-Iraq_barplot_positive.html" width="1000" height="600" frameborder="0"></iframe>
  <iframe src="images/Q1/Iran-Iraq_barplot_dystopian.html" width="1000" height="600" frameborder="0"></iframe>
</div>

This study’s first research question examined how wars influenced the production of various movie genres, revealing distinct trends. Military genres, such as War Films and Spy Films, often followed a cyclic pattern, peaking during major conflicts like World War II and the Vietnam War before declining afterward. Positive genres, including Comedy and Family Films, generally remained stable, serving as escapism, though prolonged conflicts like the Vietnam War disrupted their production. Political and dystopian genres showed less consistent trends, suggesting they are more influenced by broader cultural or geopolitical factors.

Significant changes in genre distributions during key wars provided further insights. World War II saw spikes in War Films and propaganda, while Horror Films rose during the war but declined afterward. The Vietnam War spurred increases in Thrillers and Action Films, alongside a notable drop in Romantic Comedies. The Cold War’s extended timeline diluted clear trends, though War Films declined post-conflict. These findings highlight the complex interplay between wars and cinematic trends, particularly for military and positive genres, offering a foundation for further exploration in subsequent research questions.

The identified trends in genre production are global and do not offer nuance on the specific countries involved in the war and their sides. Consequently, further, we will analyze film production in relation to specific countries.

## Geopolitical Analysis of Conflicts
This section of our research is devolved to the research question: `How do movie genre preferences differ between countries in conflict?`, in which we investigate variations in genre trends across nations, focusing on contrasts during political tensions and on how different nations respond to similar historical events.      

In order to provide a quick overview of the wars we are analyzing, we provide some initial plots, showing the world map for the opposing countries for each one of the 4 conflicts:   
* World War II
* Korean War
* Cold War
* Vietnam War
This distinction between `Side 1` (Red) and `Side 2` (Blue) will be important for a deeper understanding of the following sections.   

<iframe src="images\Q2\countries_World_War_II.html" width="800px" height="600px" frameborder="0" position="relative"  style="display: block;">positive barplot</iframe>
<iframe src="images\Q2\countries_Korean_War.html" width="800px" height="600px" frameborder="0" position="relative" style="display: block;">positive barplot</iframe>
<iframe src="images\Q2\countries_Cold_War.html" width="800px" height="600px" frameborder="0" position="relative" style="display: block;">positive barplot</iframe>
<iframe src="images\Q2\countries_Vietnam_War.html" width="800px" height="600px" frameborder="0" position="relative"  style="display: block;">positive barplot</iframe>

## Movies Timeline
Another plot helpful in the understanding of the setting of the analysis is the following timeline, which aims to show the number of movies produced over the course of the years relative to each one of the considered conflicts:   

<iframe class="toggle-frame" src="images\Q2\movies_timeline.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>

The plot shows a large area associated to movies related to `World War II`, much larger than that of all other conflicts combined. This highlights the influence a conflict of such scale has had on the world, even further in the future.   
A more in-depth inspection of the graph shows how, despite the general movies trend are characterized by an overall increase in movies produced every year, the peak in production of WWII movies has peaked during the conflict itself, to then decrease gradually over time to then settle between 10-15 movies a year in the XXI century.   
Movies on the `Vietnam War` were not produced inconsistently across all years starting from the war, reaching their peak in 2005 with 9 movies.   
The `Korean War` has had its highest movies production in the period right after the war, in the 1950s, after which it hasn-t received much attention in the cinematographic world, achieving at most 3 movies per year ever since.   
Finally, contrary to our expectations, the `Cold War` itself didn't get much attention during the course of the years, with no more than 4 movies produced in a given year making it the lowest in our analysis.

## Geographical Analysis of Movie Production
The final introductive plot of this section is a sunburst chart which depicts for each war where the movies obtained by the previous filtering are produced, using the same division between `Side 1` and `Side 2` as in the section for `World Maps for Analyzed Conflicts`.   
This section is mainly aimed at depicting a comparison between the way the opposing countries in the war (as well as the ones not directly involved) were influenced by the conflicts, in terms of a purely quantitative rather than qualitative analysis.   
For each of the following plots, the `Red` section corresponds to `Side 1`, the `Blue` one to `Side 2` and the `Green` one to movies produced in `other countries`.

<iframe class="toggle-frame" src="images\Q2\sunburst_World War II.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\sunburst_Korean War.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\sunburst_Cold War.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\sunburst_Vietnam War.html" width="800px" height="600px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>

A comment which can be made for each of these graphs is that United States take up the largest slice of the chart divided by countries, and this is largely due to the fact that the United States contribute in the largest amount to all movies produced, regardless of the topic.    
Entering more in detail, regarding `World War II`, we can see that the largest forces of the conflict lead the movie production, with the USA having released more than 400 movies, the UK more than 100 and countries such as France, Germany, Italy and Japan all with more than 20 movies each. On top of this, the massive influence of the conflict can also be seen from the large number of smaller countries having released some movies about it, with movies released in more than 50 countries in total!   
Once again, for the `Korean War`, most of the movies were produced by the USA, but if we exclude its contribution we can see that South Korea, one of the countries directly involved in the conflict, is the largest producer of movies on the conflict. Follow the UK and China, alongside some other Asian countries.   
Moreover, we see that for the `Cold War` the largest part of the movies were produced by countries not directly involved in the conflict, showing how such a conflict has impacted the whole world and not only the two opposing sides. As stated before, the USA contribute to the largest part of the movies, while Russia, despite being one of the two involved countries, only amounts to a single movie in our chart, surpassed by the large european countries such as Germany, UK and France.   
Finally, for the `Vietnam War` we can see from the chart that no movies about it were released in Vietnam, only country directly involved in the war as "Side 2" in our dataset, while the movies are almost equally distributed among the various countries (as usual, exception made for the USA).


## Comparative Genre Analysis of Movies
In this and the following sections we delve deeper in the qualitative analysis and comparison between the two sides of the conflicts, analyzing the different distribution in movie genres for different subsets of the Movies dataset.   
Here we provide a first analysis by filtering our dataset based on the movies released in a historical period around each of the analyzed war, and check what is the movie genre of the movies depicting countries from either side of the conflict.   
On top of that, in the barplot we also present the distribution of those same genres across movies produced in general, comparing the results obtained during the war to the frequency these genres have over time.

<iframe class="toggle-frame" src="images\Q2\genres_year_World War II.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\genres_year_Korean War.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\genres_year_Cold War.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\genres_year_Vietnam War.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>

A first look at the plot makes it easy to see that genres like `Drama` are the most common overall, wo we will not consider these common trends in the analysis, but we will focus more on the distinctions between the two sides and between the specific time period vs the entire dataset.   
During `World War II`, a common trend between the two sides was the large presence of BlackandWhite movies, which is mainly to attribute to an historical reason rather than a Geopolitical one. What characeterizes this period the most is the sharp increase in War Films, which see by far the largest increase, with Spy movies being also fairly common on both sides. On top of this, genres like Adventure and Romance Films were still prominent, reflecting themes of heroism and human struggle. The most distinctive trend betwee the two sides is the presence of Propaganda Films on Side 2, alongside genres like Japanese Movies which are instead causes by a purely geographical connotation.   
During the `Korean War`, we see once again the trend for BlackandWhite films dominating the genre landscape on both sides compared to the overall dataset, once again associated to the analyzed historical period. On Side 1, there was a strong emphasis on Romance Films and Adventure films, while Side 2 leaned more into violent themes, such as War Films (which are the most present in this reduced dataset) and Combat Films, highlighting themes of conflict and cultural representation.
During the `Cold War`, on Side 1 genres like Adventure, ActionAdventure, and War Films show a significant increase compared to the whole dataset, while genres related to romance are less common in this period of time. On Side 2, instead, Spy films and War films stood out more, alongside Political Thrillers, suggesting themes of espionage and historical reflection, themes fairly common in the sentiment of the time.    
The `Vietnam War` era saw a general increase in genres like Action, Thriller, and War Films, emphasizing the conflict's intensity, but the specific response of the two sides was quite different: Side 1 had a much stronger increase in genres like Crime Fiction, Horror and Disaster compared to all other subsets of data analyzed so far, underlying the climate of tension in Vietnam in particular in this period of time. Side 2, on the other hand, had changes more in line with the general trends, with Action, Adventure and War films being more present while Romance and World cinema are less common overall.   



This final section of the comparative analysis between countries focuses more on the way the conflict is portrayed in movies produced in different countries. This section has a similar approach to that discussed in the section `Geographical Analysis of Movie Production`, but goes in depth analyzing the differences in genre between the two movie subsets, although this analysis often times ended up being difficult due to the limited sizes of the sub-datasets.

<iframe class="toggle-frame" src="images\Q2\genres_summary_World War II.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\genres_summary_Korean War.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="images\Q2\genres_summary_Cold War.html" width="800px" height="400px" frameborder="0" position="relative" id="positive" style="display: block;">positive barplot</iframe>

The first thing to notice is the fact that for both `Cold War` and `Korean War` one side has much fewer movies compared to the other, while for the `Vietnam War` not enough movies were found for one of the two sides, hence no plot was produced. This leads to the results relative to these plots less significant overall, but we decided to still mention them for completeness.   
The plot for the `Cold War` shows lines of regular heigths in the histogram, due to the small amount of movies plotted. Other than this, the trends in the plot are to be expected, with genres like Thriller and Spy being the most represented in both sides, but a weird-to-explain entry is the presence of Comedy films on Side 1.   
Movies about the `Korean War` show much more different genres on Side 1, while on Side 2 we see a strong geographical component in the genres, with Chinese and Japanese Movies being common.   
Finally, movies about `World War II` are the ones associated with the largest number of movies, information which can also be extracted by the "smoothness" of the histogram distribution. Both sides share a large variety of genres for the movies, with War films and Period Piece being the most significant ones in terms of comparison with the whole dataset, but no significant difference between the two sides can be extracted from he plot.   

In general these plots underline how the general sentiment associated to the movies produced during the war and movies which directly reference the war are usually quite serious and tense, so we decided to go more in depth with the analysis of the sentiment of the storytelling, suing techniques derived from Natural Language Processing (NLP).

# Examining Storytelling Variations in War Films
While our previous analysis revealed distinct patterns in genre production across different countries, a deeper examination of narrative construction within the same genre warrants investigation. Our analysis will focus exclusively on war cinema as it provides a unique window into how different nations process, interpret, and memorialize shared historical events through film. War movies are particularly revealing because they often reflect not only a country's historical perspective but also its contemporary values, national identity, and relationship with military conflict. 

We isolated war films specifically depicting our four conflicts of interest and identified their respective sides. Unfortunately, given the limited number of movies produced about the Vietnam War and the Korean War, we have decided to focus exclusively on the Cold War and World War II.

<iframe src="number_of_war_movies.html" width="100%" height="800px" frameborder="0">n_movies</iframe>

## Sentiment Analysis

### Word War II 

We performed a sentiment analysis on the summaries of the movies identified. This analysis helped identify the emotional tone of the summaries, determining whether they are primarily positive, negative, or neutral depending of the countries of production and the event. 

<iframe src="wwii_sentiment_mini.html" width="100%" height="800px" frameborder="0">n_movies </iframe>

We do observe a higher negative score which isn't surprizing, however the overlapping confidence intervals across all categories indicate that the differences between the Allied and Axis films' sentiment scores are pretty similar. However, it is surpriing to observe that the confidence intervall is much higher for the compound result. Let's observe the distribution. 

<iframe src="wwii_distribution_mini.html" width="100%" height="800px" frameborder="0">n_movies </iframe>

The distribution is pretty similar among the two samples, however the sample sizes are imbalanced, which could contribute to the variability observed, particularly for Side 2. We also conducted a T-test that confirmed that they were no significant difference between the two sides. 

### Cold War 


When comparing the results with those from Cold War-themed movies, we found that the sentiment analysis scores were remarkably consistent across both historical contexts. This suggests that the emotional tone in the plot summaries of war genre movies remains largely stable, regardless of the specific conflict being depicted. As with WWII movies, no significant differences were observed between the two sides for neutral, positive, or negative sentiment scores. While a difference in the compound score was noted, it is likely attributable to sample size limitations rather than a meaningful divergence in sentiment. 

<iframe src="global_sentiment_mini.html" width="100%" height="800px" frameborder="0">n_movies </iframe>


It is not sufficient to draw definitive conclusions from these findings, as we cannot yet confidently determine whether there are no differences between countries in their depiction of conflicts within the movie industry. Our sample size was relatively small, and relying solely on plot summaries may not have been the most effective approach for capturing nuanced differences. In the next section, we will adopt a more qualitative approach, focusing not on the overall sentiment of the global plot but on the sentiment associated with specific entities. This shift in methodology aims to provide deeper insights and address potential limitations in our initial analysis.


### The shifting sentiment towards organizations during a world-scale conflicts.
The way conflicts are represented in cultural narratives often reveals underlying societal attitudes, biases, and historical contexts. In this part of the study we applied entity-level sentiment analysis to entities tagged as ‘ORGANIZATIONS’ in two worldwide conflicts : World War II and the Cold War.  
By analyzing the sentiment associated with such entities, we can uncover patterns of representation before, during and after the conflicts.   
The accompanying heatmaps visualize the compound sentiment scores associated with each organization:
* Negative sentiment is indicated by negative scores, represented by shades of red.
* Positive sentiment is shown by positive scores, depicted in shades of blue.
* The deeper the color, the more extreme the sentiment.
  
Through this lens, we highlight how military, political, and international organizations were characterized, uncovering patterns that reflect both the conflict's nature and the cultural context of each side.

#### World War II
Starting with World War II, we analyse representations from two key perspectives : the Allied Forces and the Axis forces. For the Allied forces,sufficent data allows for a comparative analysis of sentiment before and after the conflict, leading to three significant observations. 

##### Allied Side Heatmaps

<script>
function showFrame(frameId) {
  // Get all iframes with the toggle-frame class
  var frames = document.getElementsByClassName('toggle-frame');

  // Hide all iframes with the toggle-frame class
  for (var i = 0; i < frames.length; i++) {
    frames[i].style.display = 'none';
  }

  // Show the selected iframe
  var frame = document.getElementById(frameId);
  frame.style.display = 'block';
}
</script>
<style>
  .button {
    background-color: #8B0000;
    border: none;
    border-radius: 10px;
    color: white;
    padding: 14px 20px;
    text-align: center;
    font-size: 11px;
    text-decoration: none;
    display: inline-block;
    cursor: pointer;
    font-size: 11px;
  }
</style>

<!-- Create the buttons -->
<button class="button" style="margin: 8px 0; width: 20%; margin-left: 130px; margin-right: 5px" onclick="showFrame('wwii_Before1')">Allied Side, Before</button>
<button class="button" style="width: 20%; margin-right: 5px;" onclick="showFrame('wwii_After1')">Allied Side, After</button>

<iframe class="toggle-frame" src="heatmap_0.html" width="800px" height="900px" frameborder="0" position="relative" id="wwii_Before1" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="heatmap_1.html" width="800px" height="900px" frameborder="0" position="relative" id="wwii_After1" style="display: block;">positive barplot</iframe>

##### Axis Side Heatmap
<iframe src="heatmap_2.html" width="800px" height="900px" frameborder="0" position="relative" id="Before2" style="display: block;">positive barplot</iframe>

These heatmaps lead us to three significant observations :   
**Military Authorities have an universally negative depiction**      
Regardless of the geopolitical side, military authorities are predominantly portrayed negatively before and after the conflict.  
One key example of this phenomenon appears in the heatmaps of the Allied forces (before and after the conflict), where entities tagged with military ranks like “Commander” and “Infantry” consistently exhibit highly negative scores.
This reflects a recurring portrayal of militarism as oppressive and destructive, particularly when analyzed over time. Even as the conflict resolves, negative sentiment toward military organizations persists. 

**Political parties sentiment shift with context and time**  
The main example of this phenomenon is the portrayal of the Nazi Party in cultural narratives, which reveals temporal and cultural shifts.  
On the first hand, in early Allied Forces representations, the Nazi Party occasionally exhibits positive sentiment scores. For example, the heatmap reveals a positive sentiment score of 0.61525 in the UK. This likely reflects pre-conflict ambivalence when the Nazi Party was not yet universally associated with its later actions. After the conflict, however, still in the western perspective, the party’s portrayal becomes uniformly negative, aligning with the global consensus on its role in the war.  
On the other hand, in the Axis Forces’ heatmap, the Nazi Party is consistently portrayed with neutral to highly negative score, reflecting a post-war cultural reckoning within Germany.

**International Organizations as stabilizing roles**  
Entities like NATO and other international organizations show a trend of neutral sentiment, notably in Western narratives.
For example, in the post-conflict Allied Forces’ heatmap, NATO maintains neutral scores, emphasizing their portrayal as stabilizing forces.

#### Cold War
The Cold War was as much a battle of ideologies as it was a geopolitical and military standoff. Sentiment analysis applied to organizational entities reveals the nuanced ways in which each side—Western Bloc and Eastern Bloc—portrayed military, political, and international organizations.

##### Western Block Heatmaps 
<!-- Create the buttons -->
<button class="button" style="margin: 8px 0; width: 20%; margin-left: 130px; margin-right: 5px" onclick="showFrame('cw_Before1')">Western Block, Before</button>
<button class="button" style="width: 20%; margin-right: 5px;" onclick="showFrame('cw_After1')">Western Block, After</button>

<iframe class="toggle-frame" src="heatmap_3.html" width="800px" height="900px" frameborder="0" position="relative" id="cw_Before1" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="heatmap_4.html" width="800px" height="900px" frameborder="0" position="relative" id="cw_After1" style="display: block;">positive barplot</iframe>

##### Sovietic Block Heatmaps 


<!-- Create the buttons -->
<button class="button" style="margin: 8px 0; width: 20%; margin-left: 130px; margin-right: 5px" onclick="showFrame('cw_Before2')">Sovietic Block, Before</button>
<button class="button" style="width: 20%; margin-right: 5px;" onclick="showFrame('cw_After2')">Sovietic Block, After</button>

<iframe class="toggle-frame" src="heatmap_5.html" width="800px" height="900px" frameborder="0" position="relative" id="cw_Before2" style="display: block;">positive barplot</iframe>
<iframe class="toggle-frame" src="heatmap_6.html" width="800px" height="900px" frameborder="0" position="relative" id="cw_After2" style="display: block;">positive barplot</iframe>

On the Western Bloc side during the Cold War tensions, sentiment towards entities is mixed, with a noticeable
inclination toward more negative sentiments. For instance, organizations such as the KGB and Communist Partyexhibit both positive and negative sentiment scores. Interestingly, some US-related entities also receive negative sentiments, reflecting a nuanced narrative. This suggests that, despite the overarching hostility depicted in media towards the opposing bloc, the relatively freer speech in the West allowed for more balanced or even positive portrayals in certain instances. Furthermore, military organizations and concepts, such as Military and DEFCON, are often associated with negative sentiments, reflecting the pervasive anxiety about the potential for imminent conflict.

After the Cold War, sentiments toward Soviet bloc-related entities become less negative as tensions subside, reflecting a gradual easing of hostility in narratives.

In contrast, the Soviet bloc exhibits a universally positive representation of its allied entities, such as the Bolshevik Party, which achieves a notably high positive sentiment (~0.8). This consistent positivity highlights the influence of controlled narratives within the Soviet bloc, where media operated under stricter guidelines and presented a narrower, more favorable lens on allied organizations.

# Audience Preferences During Crises

Over the course of this analysis, we have explored the evolution of war cinema and the sentiment associated with different entities during global conflicts. All of that was based on the internal production and representation of the movies. In this final part, we would like to switch to the viewer sentiment and interest, aligning global
events such as wars, pandemics, and natural disasters to inspect both short-term and long-term shifts in audience
preferences. To do this, we will inspect genre-specific trend analysis to identify spikes in popularity as well as
sustained changes over time. In order to achieve this, we utilize the insights from [Google Search Trends](https://trends.google.com/trends/) that will help us uncover user interest for both general movie genres and thematics and particular movies in our aggregated movies dataset.

## Genres Interest Over Time 

In previous parts we have found the most prominent movies genres. Now we will explore the interest in these genres over time. We firstly took the top 20 genres overall.

<image src="images/Q4/top_genres.png" style="width: 100%; height: auto;"></image>

We then analyzed the search interest intensity over the years for these genres.

<image src="images/Q4/heatmap_interest.png" style="width: 100%; height: auto;"></image>

The first general observation is that the overall movies popularity peaked in 2016-2017 and then again in the beginning of COVID pandemics. The reason for the peak during the pandemics is clear - we were stuck at home during the lockdowns! However, why was there another peak in 2016-2017?

This peak could be explained by two of many other factors:

1. By 2015, streaming had firmly established itself as a dominant force in the entertainment industry. Netflix had expanded to over 190 countries, and Amazon Prime Video had also become a significant player, therefore driving interest in movies.
2. 2016-2018 were among the best years in history with the number of newly released movies as well as box office numbers peaked (Source: [BoxOfficeMojo](https://www.boxofficemojo.com/year/)). Further analysis of such factors would be a particularly interesting idea but is worth another ADA project by itself!

If we zoom out from these peak periods, we can also observe strong seasonality patterns in particular movie genres interest. For example, interest for horror movies generally peaks during Halloween season and Family movies peak around Christmas. 

<image src="images/Q4/seasonality_chart.png" style="width: 100%; height: auto;"></image>

We can now perform a seasonal decomposition analysis to further inspect the strength of such patterns for all movie genres. This analysis is performed using an additive seasonality signal:

Y[t] = T[t] + S[t] + e[t]

- Y[t]: Popularity of a movie genre at time t
- T[t]: Trend
- S[t]: Seasonality
- e[t]: Residual

This helps us to firstly identify if there are movie movie genres exhibiting strong seasonality patterns. While we do not find more positive seasonality patterns as for Horror and Family movies, we can observe more significant negative seasonality where popularity historical movies reduces during the summer months. This seasonal impact is more prolonged, as observed by wider signal peaks.

<image src="images/Q4/seasonality_all.png" style="width: 100%; height: auto;"></image>

One potential reason for such negative seasonality could be that historical movies are consumed for educational purposes, therefore during the summer months, when students are on vacation, the interest in historical movies decreases.

Moreover, as explained above, the seasonality decomposition also provides us the ability to infer a cleaner trend signal. Paired with a polynomial regression (of degree two in this case), we can identify the overall trend in popularity for each movie genre.

<image src="images/Q4/trends_all.png" style="width: 100%; height: auto;"></image>

Here, we can clearly see long-term changes in the popularity of different movie genres. The majority of genres exhibit a popularity trend consistent with the movies popularity peaks where the trend was positive until 2017 and reversed shortly after that. It is also observed that crime and thriller movie genres have been consistently gaining popularity over the years. A clear declining trend is also observed for the historical movie genre and music movies. What is a music movie? As per IMDb:

> Music Movie: Contains significant music-related elements while not actually being a Musical; this may mean a concert, or a story about a band (either fictional or documentary). Examples: A Star Is Born (2018) |Almost Famous (2000) | Sunshine Daydream (2013)

Focusing ourselves on the impact of wars, we can see that the popularity in war and historical movies genres has been very stable over the years. It is clear that people are always interested in re-visiting and learning about historical events through the lens of a movie.

However are the interest fluctuations related to the number of movies released over the years? To answer this, we have to restrict ourselves in movies data availability period which overlaps with available Google Search Trends Data for years 2004-2012. We can then estimate the correlation between the number of movies released and the interest in a particular genre.

<image src="images/Q4/correlation.png" style="width: 100%; height: auto;"></image>

The results suggest that the number of genre-specific movies released in a year is largely negatively correlated with the interest for such a genre. A possible explanation for that could be that if more movies are released in a genre, audiences might experience fatigue or feel overwhelmed, leading to a decline in search interest. Nonetheless, there are three notable outliers over our defined sample period: Music, Musicals and Sci-Fi movies. These differences could be explained by a boom of Sci-Fi movies released over the 2000s. There was also a shorter boom in Musicals, especially notable with the release of *Mamma Mia!* and other Musicals that followed the influx of this movie's genres. This would suggest that over the years the interest in such genres was not dilluted by the amount of new movies being released. Nonetheless, these results are not significant at a 5% confidence level, therefore cannot be considered as a strong evidence of a relationship between the number of movies released and the interest in a genre.

But what about the impact of global events on audience preferences? To answer this question, we will shift focus to changes in genre popularity when these events occur. We can firstly try to check if the occurences of different global events had an impact on the interest of certain movie genres. For that, we have collected the most important global events from the [Wikipedia's 21st Century Timeline](https://en.wikipedia.org/wiki/Timeline_of_the_21st_century) and classified them into 5 types: wars, political instability, natural disasters, catastrophes, pandemics, and economic crises. We then analyzed the changes interest of different movie genres together with the number of instances of these events over the months over the period of 2004 to 2023. For that, a linear regression analysis was performed to estimate the impact of these events on the interest in a genre. Below we have plotted only those results which are significant at a 5% confidence level.

<image src="images/Q4/events_on_movie_interest.png" style="width: 100%; height: auto;"></image>

While the results estimate that the impact of global events on the interest in movie genres is significant for some pairs, the R-squared values are generally low, indicating that the global events do not explain the majority of the variance in the interest in movie genres, which is rational considering the rarity of such global events happening.

<image src="images/Q4/events_on_movie_interest_heatmap.png" style="width: 100%; height: auto;"></image>

The most significant impact is naturally observed by the occurence of pandemics. For our observation period, only COVID pandemic had a significant impact on the interest in almost all movie genres. This is rational as people were stuck at home during the lockdowns and were looking for ways to entertain themselves.

Nonetheless, it is especially interesting to observe that the interest in the war and historical movie genres is not impacted by the occurrence of wars, political instability, and catastrophes. This may be an indication that the audience is not interested in watching movies about the events they are currently experiencing. Is this supported by short-time trends?

<image src="images/Q4/short_term_trends.png" style="width: 100%; height: auto;"></image>

At least for war movies, it is not. The interest in war movies is not impacted by the occurrence of wars even in the short term, except for a couple of instances such as war in Ukraine or a conflict in Gaza back in 2007. This indicates that the audiences are rarely interested in watching movies about the events taht are currently experienced.

# Conclusion
Through this study, we explored how global events, particularly conflicts like World War II, the Cold War, and others, have influenced film genres, public preferences, and sentiment. The analysis of ouur data uncovered how historical events shape cinematic narratives, both in terms of content and reception.

The initial findings showed that wars significantly influence the production of various movie genres, with military genres like War Films and Spy Films showing cyclic peaks during major conflicts, such as World War II and the Vietnam War, before declining afterward. Positive genres such as Comedy and Family Films generally provided escapism though prolonged conflicts disrupted their stability. Shifts during key wars, such as spikes in propaganda films during World War II and increased Thrillers and Action Films during the Vietnam War, underscore the nuanced interplay between warfare and cinematic trends.

All wars have been met with a similar increase in genres associated with a serious and tense tone, but there are also charactecteristics differentiating the single countries, both in terms of amounts and genres. On top of that, due to the fact that every single conflict has a sphere of influence different from the others, it is difficult to demonstrate constant results across different conflicts.

Furthermore, each movie has an embedded message which can be revealed by sentiment analysis. Our findings revealed a predominantly negative tone in war-related narratives, reflecting the inherent gravitas of such topics. Entity-level analysis highlighted an universal negativity towards military organizations, shifts in the portrayal of political parties, such as the Nazi Party, and neutral to positive portrayals of international organizations like NATO.

The portrayal of global events such as war is inherent to the production of movies. However, interest in such movies is an important external factor. Audience preferences for movie genres are shaped by seasonal patterns and broader trends, with peaks during 2016-2017 and the COVID-19 pandemic. Seasonal spikes such as Halloween for horror and Christmas for family movies weere observed. Interest in most genres have periods of interest growth and decline while crime and thriller genres show sustained growth. Global events like pandemics significantly impact interest but wars and other crises have minimal influence, suggesting audiences prefer escapism over real-time reflections of hardships.


