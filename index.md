---
layout: page
title: Cinematography in Times of Crisis
subtitle:  Exploring the Impact of Global Events on Film Genres and Public Preferences
cover-img: /assets/img/téléchargement.jpeg
thumbnail-img: /assets/img/téléchargement.jpeg
share-img: /assets/img/téléchargement.jpeg
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

<div class="container my-4">
    <!-- Second Carousel -->
    <div id="carouselExampleIndicators2" class="carousel slide" data-bs-ride="carousel">
        <div class="carousel-indicators">
            <button type="button" data-bs-target="#carouselExampleIndicators2" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
            <button type="button" data-bs-target="#carouselExampleIndicators2" data-bs-slide-to="1" aria-label="Slide 2"></button>
            <button type="button" data-bs-target="#carouselExampleIndicators2" data-bs-slide-to="2" aria-label="Slide 3"></button>
            <button type="button" data-bs-target="#carouselExampleIndicators2" data-bs-slide-to="3" aria-label="Slide 4"></button>
        </div>
        <div class="carousel-inner">
            <div class="carousel-item active">
                <iframe src="images/Q1/trend_batdeath_military.html" frameborder="0" width="100%" height="600"></iframe>
            </div>
            <div class="carousel-item">
                <iframe src="images/Q1/trend_batdeath_antiwarmilitary.html" frameborder="0" width="100%" height="600"></iframe>
            </div>
            <div class="carousel-item">
                <iframe src="images/Q1/trend_batdeath_political.html" frameborder="0" width="100%" height="600"></iframe>
            </div>
            <div class="carousel-item">
                <iframe src="images/Q1/trend_batdeath_dystopian.html" frameborder="0" width="100%" height="600"></iframe>
            </div>
        </div>
        <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleIndicators2" data-bs-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleIndicators2" data-bs-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Next</span>
        </button>
    </div>
</div>

## Correlations
Correlations for the Second World War (1937-1947)

<!-- First Carousel -->
<div id="carouselcorr" class="carousel slide" data-bs-ride="carousel">
  <!-- Indicators -->
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#carouselcorr" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#carouselcorr" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#carouselcorr" data-bs-slide-to="2" aria-label="Slide 3"></button>
    <button type="button" data-bs-target="#carouselcorr" data-bs-slide-to="3" aria-label="Slide 4"></button>
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
    <div class="carousel-item">
      <iframe src='images/Q1/corr_batdeath_Military_1937-1947.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
    <iframe src='images/Q1/corr_batdeath_Military&Antiwar_1937-1947.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
    <iframe src='images/Q1/corr_batdeath_War_film_1937-1947.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
    <iframe src='images/Q1/corr_numwars_Antiwar_1937-1947.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
    <iframe src='images/Q1/corr_numwars_Disaster_1937-1947.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
    <iframe src='images/Q1/corr_numwars_Thriller_1937-1947.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
  </div>

  <!-- Controls -->
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselcorr" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselcorr" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

Correlations for the Vietnam War (1963-1977)

<!-- Second Carousel -->
<div id="carouselcorr2" class="carousel slide" data-bs-ride="carousel">
  <!-- Indicators -->
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#carouselcorr2" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#carouselcorr2" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#carouselcorr2" data-bs-slide-to="2" aria-label="Slide 3"></button>
    <button type="button" data-bs-target="#carouselcorr2" data-bs-slide-to="3" aria-label="Slide 4"></button>
  </div>

  <!-- Slides -->
  <div class="carousel-inner">
    <div class="carousel-item active">
      <iframe src='images/Q1/corr_batdeath_Fantasy_1963-1977.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/corr_numwars_Family_Film_1963-1977.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/corr_numwars_Romantic_comedy_1963-1977.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
  </div>

  <!-- Controls -->
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselcorr2" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselcorr2" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

Correlations for the Cold War (1947-1991)

<iframe src='images/Q1/corr_numwars_Romantic_comedy_1947-1991.html' width="100%" height="600" frameborder="0"></iframe>

Correlations for the Iran-Iraq War (1978-1990)
<!-- Third Carousel -->
<div id="carouselcorr3" class="carousel slide" data-bs-ride="carousel">
  <!-- Indicators -->
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#carouselcorr3" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#carouselcorr3" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#carouselcorr3" data-bs-slide-to="2" aria-label="Slide 3"></button>
    <button type="button" data-bs-target="#carouselcorr3" data-bs-slide-to="3" aria-label="Slide 4"></button>
  </div>

  <!-- Slides -->
  <div class="carousel-inner">
    <div class="carousel-item active">
      <iframe src='images/Q1/corr_batdeath_Disaster_1978-1990.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/corr_batdeath_Superhero_1978-1990.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/corr_numwars_Disaster_1978-1990.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/corr_numwars_Family_Film_1978-1990.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
  </div>

  <!-- Controls -->
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselcorr3" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselcorr3" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>

Correlations for the timeline (1950-2012)
1950 was created as a cut off since the spike in battle deaths during the WW2 significantely affected the results.

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
      <iframe src='images/Q1/corr_numwars_Romantic_comedy_1950-2012.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/corr_numwars_Superhero_1950-2012.html' width="100%" height="600" frameborder="0"></iframe>
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

Plotting the network
<iframe src="images/Q1/network.html" frameborder="0" width="100%" height="600"></iframe>

## Significant Changes in Genres for the Chosen Wars
<iframe src="images/Q1/significantchange_WW2.html" frameborder="0" width="100%" height="600"></iframe>
<iframe src="images/Q1/significantchange_ColdWar.html" frameborder="0" width="100%" height="600"></iframe>
<iframe src="images/Q1/significantchange_Vietnam.html" frameborder="0" width="100%" height="600"></iframe>
<iframe src="images/Q1/significantchange_Iran-Iraq.html" frameborder="0" width="100%" height="600"></iframe>

## Specific Genres for the Chosen Wars
World War II
<div id="WW2" class="carousel slide" data-bs-ride="carousel">
  <!-- Indicators -->
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#WW2" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#WW2" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#WW2" data-bs-slide-to="2" aria-label="Slide 3"></button>
    <button type="button" data-bs-target="#WW2" data-bs-slide-to="3" aria-label="Slide 4"></button>
  </div>

  <!-- Slides -->
  <div class="carousel-inner">
    <div class="carousel-item active">
      <iframe src='images/Q1/WW2_barplot_militaryandantiwar.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/WW2_barplot_political.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/WW2_barplot_positive.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
  </div>

  <!-- Controls -->
  <button class="carousel-control-prev" type="button" data-bs-target="#WW2" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#WW2" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>


The Cold War
<div id="Cold" class="carousel slide" data-bs-ride="carousel">
  <!-- Indicators -->
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#Cold" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#Cold" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#Cold" data-bs-slide-to="2" aria-label="Slide 3"></button>
    <button type="button" data-bs-target="#Cold" data-bs-slide-to="3" aria-label="Slide 4"></button>
  </div>

  <!-- Slides -->
  <div class="carousel-inner">
    <div class="carousel-item active">
      <iframe src='images/Q1/Cold_War_barplot_militaryandantiwar.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/Cold_War_barplot_political.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/Cold_War_barplot_dystopian.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/Cold_War_barplot_positive.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
  </div>

  <!-- Controls -->
  <button class="carousel-control-prev" type="button" data-bs-target="#Cold" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#Cold" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>


The Vietnam War

<div id="Vietnam" class="carousel slide" data-bs-ride="carousel">
  <!-- Indicators -->
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#Vietnam" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#Vietnam" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#Vietnam" data-bs-slide-to="2" aria-label="Slide 3"></button>
    <button type="button" data-bs-target="#Vietnam" data-bs-slide-to="3" aria-label="Slide 4"></button>
  </div>

  <!-- Slides -->
  <div class="carousel-inner">
    <div class="carousel-item active">
      <iframe src='images/Q1/Vietnam_barplot_militaryandantiwar.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/Vietnam_barplot_political.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/Vietnam_barplot_dystopian.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/Vietnam_barplot_positive.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
  </div>

  <!-- Controls -->
  <button class="carousel-control-prev" type="button" data-bs-target="#Vietnam" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#Vietnam" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>


The Iran-Iraq War

<div id="Iran" class="carousel slide" data-bs-ride="carousel">
  <!-- Indicators -->
  <div class="carousel-indicators">
    <button type="button" data-bs-target="#Iran" data-bs-slide-to="0" class="active" aria-current="true" aria-label="Slide 1"></button>
    <button type="button" data-bs-target="#Iran" data-bs-slide-to="1" aria-label="Slide 2"></button>
    <button type="button" data-bs-target="#Iran" data-bs-slide-to="2" aria-label="Slide 3"></button>
    <button type="button" data-bs-target="#Iran" data-bs-slide-to="3" aria-label="Slide 4"></button>
  </div>

  <!-- Slides -->
  <div class="carousel-inner">
    <div class="carousel-item active">
      <iframe src='images/Q1/Iran-Iraq_barplot_militaryandantiwar.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/Iran-Iraq_barplot_political.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/Iran-Iraq_barplot_dystopian.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
    <div class="carousel-item">
      <iframe src='images/Q1/Iran-Iraq_barplot_positive.html' width="100%" height="600" frameborder="0"></iframe>
    </div>
  </div>

  <!-- Controls -->
  <button class="carousel-control-prev" type="button" data-bs-target="#Iran" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#Iran" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>


## World Maps for Analyzed Conflicts
In order to provide a quick overview of the wars we are analyzing, we provide some initial plots, showing the world map for the opposing countries for each one of the 4 conflicts:

<iframe src="images\Q2\countries_World_War_II.html" width="800px" height="600px" frameborder="0" position="relative"  style="display: block;">positive barplot</iframe>
<iframe src="images\Q2\countries_Korean_War.html" width="800px" height="600px" frameborder="0" position="relative" style="display: block;">positive barplot</iframe>
<iframe src="images\Q2\countries_Cold_War.html" width="800px" height="600px" frameborder="0" position="relative" style="display: block;">positive barplot</iframe>
<iframe src="images\Q2\countries_Vietnam_War.html" width="800px" height="600px" frameborder="0" position="relative"  style="display: block;">positive barplot</iframe>

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


# Examining Storytelling Variations in War Films
While our previous analysis revealed distinct patterns in genre production across different countries, a deeper examination of narrative construction within the same genre warrants investigation. Our analysis will focus exclusively on war cinema as it provides a unique window into how different nations process, interpret, and memorialize shared historical events through film. War movies are particularly revealing because they often reflect not only a country's historical perspective but also its contemporary values, national identity, and relationship with military conflict. 

We isolated war films specifically depicting our four conflicts of interest and identified their respective sides. Unfortunately, given the limited number of movies produced about the Vietnam War and the Korean War, we have decided to focus exclusively on the Cold War and World War II.

<iframe src="number_of_war_movies.html" width="100%" height="800px" frameborder="0">n_movies</iframe>

## Sentiment Analysis

### Word War II 

We performed a sentiment analysis on the summaries of the movies identified. This analysis helped identify the emotional tone of the summaries, determining whether they are primarily positive, negative, or neutral depending of the countries of production and the event. 

<iframe src="wwii_sentiment_analysis.html" width="100%" height="800px" frameborder="0">n_movies </iframe>

We do observe a higher negative score which isn't surprizing, however the overlapping confidence intervals across all categories indicate that the differences between the Allied and Axis films' sentiment scores are pretty similar. However, it is surpriing to observe that the confidence intervall is much higher for the compound result. Let's observe the distribution. 

<iframe src="wwii_distribution_compound.html" width="100%" height="800px" frameborder="0">n_movies </iframe>

The distribution is pretty similar among the two samples, however the sample sizes are imbalanced, which could contribute to the variability observed, particularly for Side 2. We also conducted a T-test that confirmed that they were no significant difference between the two sides. 

### Cold War 


When comparing the results with those from Cold War-themed movies, we found that the sentiment analysis scores were remarkably consistent across both historical contexts. This suggests that the emotional tone in the plot summaries of war genre movies remains largely stable, regardless of the specific conflict being depicted. As with WWII movies, no significant differences were observed between the two sides for neutral, positive, or negative sentiment scores. While a difference in the compound score was noted, it is likely attributable to sample size limitations rather than a meaningful divergence in sentiment. 

<iframe src="global_sentiment_analysis.html" width="100%" height="800px" frameborder="0">n_movies </iframe>


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

On the Western Bloc side during the Cold War tensions, sentiment towards entities is mixed, with a noticeable inclination toward more negative sentiments. For instance, organizations such as the KGB and Communist Party exhibit both positive and negative sentiment scores. Interestingly, some US-related entities also receive negative sentiments, reflecting a nuanced narrative. This suggests that, despite the overarching hostility depicted in media towards the opposing bloc, the relatively freer speech in the West allowed for more balanced or even positive portrayals in certain instances. Furthermore, military organizations and concepts, such as Military and DEFCON, are often associated with negative sentiments, reflecting the pervasive anxiety about the potential for imminent conflict.

After the Cold War, sentiments toward Soviet bloc-related entities become less negative as tensions subside, reflecting a gradual easing of hostility in narratives.

In contrast, the Soviet bloc exhibits a universally positive representation of its allied entities, such as the Bolshevik Party, which achieves a notably high positive sentiment (~0.8). This consistent positivity highlights the influence of controlled narratives within the Soviet bloc, where media operated under stricter guidelines and presented a narrower, more favorable lens on allied organizations.


