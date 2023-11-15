# Decoding the DNA of our characters on the silver screen

## Abstract
Have you ever wondered why some actors keep getting cast in the same role? Why Dwayne Johnson always seems to plays the adventurous, headstrong and caring leader? Why Jason Staham is constantly cast as the gritty, hardboiled tough guy? And do these recurring casting choices lead to box office success? <br>
This phenomenon is called typecasting, in which an actor becomes strongly identified with particular roles, or characters having the same traits or coming from the same social or ethnic groups. The CMU Movies Summary Corpus has already observed 501 recurring character tropes. In this study, we want to analyse the physical aspects of typecasting, by decoding the features *(gender, age, ethnicity and facial features)* of the actors playing these character tropes on the silver screen and observing them throughout time and genres, before correlating these findings to the movie's box office success. 

## Research questions
In this study, we would like to answer these questions:
* How do physical attributes influence the casting based on character tropes?
* Do these preferences fluctuate over the decades and movie genres?
* What is the effect of these casting choices on a movie's box office success?

## Additional Datasets
- Actor Images Dataset: We construct our own dataset containing images of the actors of interest. We obtain the images from The Movie DataBase (TMDB). These images will be analysed to obtain the quantified facial features. They will in turn be used as variables for our study.<br>
- WikiData: We use WikiData to convert our ActorEthnicities values from keys to usable, readable words.

## Methods
### 1) Clustering Algorithm
We use a clustering algorithm to regroup similar tropes and ethnicities together. This will allow for better data visualization as there will be more data per trope cluster.

### 2)

### Part 1: Exploring and pre-processing the data
We are given a series of datasets in this corpus, with the metadata and tv tropes cluster being the data of most interest for us. This metadata is comprised of two dataframes, the movie metadata and the characters metadata. As indicated in the CMU Movie Summary Corpus ReadMe, these two dataframes have a many variables. Let us first identify the variables of interest for our story. <br>
- *Movie metadata: Wiki_movieID, Movie Name, Release Date, Box Office, Genres* <br>
- *Character metadata: Wiki_movieID, Release Date, Character Name, Gender, Height, Ethinicity, Actor Name, Age at Movie Release* <br>

**Step 1: Movie and Characters MetaData** <br>
    - We plot our variables of interest to visualise the coherence of our data before fixing any errors. <br>
    - We analyse the percentage of missing data, giving us insight on the datasets we should use to complete our study. <br>
    - We complete key missing data *(Actor Ethnicity)*. <br>
    - We merge movies.metadata.tsv with characters.metadata.tsv to associate the characters with their respective genres, movie box office revenue and decade of release. <br>
    
**Step 2: TV Tropes** <br>
    - We pre-process our tvtropes.clusters.txt file and merge it with our merged character and movies metadata. <br>
    - We identify 501 character tropes with 72 unique archetypes. As such, we focus on these 501 tropes and their associated characters, actors and movies. We identify 350 actors corresponding to these 501 character archetypes. <br>
    - We merge TV Tropes with Movie and Character MetaData. <br>
    - We plot the number of tropes in function of movie genres to identify which genres we can remove from our dataset. <br>
    
**Step 3: Extracting Actor** <br>
    - We extract the 350 actor images from The Movies Database to create the Actor_image.csv dataset. <br>

### Part 2: Clustering our data
**Step 4: Clustering Tropes** <br>
    - We have 72 unique character tropes. This gives an average of 7 characters per trope. This is too little data for any significant analysis. As such, we decide to cluster similar tropes together to give us a more subsequent amount of characters per clustered trope. <br>
    
**Step 5: Clustering Ethnicities** <br>
    - Similarly to our character tropes, we identify a large number of unique ethnicities. With the same reasoning as for the tropes, we cluster our ethnicities together for better analysis. <br>
    
### Part 3: Facial Image Analysis
**Step X: Analysing Facial Features** <br>
    - We analyse and quantify the facial features of our actor images using a facial recognition algorithm. <br>
    
## Proposed Timeline


    
## Team Contributions
<table class="tg" style="undefined;table-layout: fixed; width: 342px">
<colgroup>
<col style="width: 164px">
<col style="width: 178px">
</colgroup>
<thead>
  <tr>
    <th class="tg-0lax"></th>
    <th class="tg-0lax">Tasks</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">Tim1110mann</td>
    <td class="tg-0lax">Exploring and pre-processing movies and characters metadata<br><br>Writing the ReadMe</td>
  </tr>
  <tr>
    <td class="tg-0lax">CVoirol</td>
    <td class="tg-0lax">Converting ethnicity from keys to usable words using WikiData<br><br><br><br></td>
  </tr>
  <tr>
    <td class="tg-0lax">izushka</td>
    <td class="tg-0lax">Extracting actor images from The Movie Database<br><br><br><br></td>
  </tr>
  <tr>
    <td class="tg-0lax">AnandaW0lz</td>
    <td class="tg-0lax">Analyzing plotted graphs<br><br><br><br></td>
  </tr>
  <tr>
    <td class="tg-0lax">Usermatthis</td>
    <td class="tg-0lax">Pre-processing tv tropes data and merging it with character and movies metadata<br><br><br><br></td>
  </tr>
</tbody>
</table>
