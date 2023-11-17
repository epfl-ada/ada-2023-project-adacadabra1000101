# Decoding the DNA of our characters on the silver screen

## Abstract
Have you ever wondered why some actors keep getting cast in the same role? Why Dwayne Johnson always seems to plays the adventurous, headstrong and caring leader? Why Jason Staham is constantly cast as the gritty, hardboiled tough guy? And do these recurring casting choices lead to box office success? <br>
This phenomenon is called typecasting, in which an actor becomes strongly identified with particular roles, or characters having the same traits or coming from the same social or ethnic groups. The CMU Movies Summary Corpus has already observed 501 recurring character tropes. In this study, we want to analyse these tropes, by decoding the features *(gender, age, height, ethnicity and facial features)* of their actors observing them throughout time and movie genres, before correlating these findings to the movie's box office success.  

## Research questions
In this study, we would like to explore following:
* Explore whether specific actor types are associated with particular character tropes
* Do these casting preferences fluctuate over the decades and movie genres?
* How does the alignment between casting choices and ideal character portrayals impact a movie's box office success?
### Subquestions for story telling
* Do casting choices perpetuate stereotypes?
* Did certain films establish a trend in typecasting, where actors are selected based on their similarity to a particularly influential portrayal in a specific role?
* In what type of role would you find yourself typecast?

## Additional Datasets
- Actor Images Dataset: We construct our own dataset containing good quality face images of the actors of interest (#347). We obtain the images from [The Movie DataBase](https://www.themoviedb.org/) (TMDB). To see more detail, consult Step 3. <br>
- [WikiData](https://query.wikidata.org/sparql): We use WikiData to convert our ActorEthnicities values from keys to usable, readable strings. 

## Methods
### 1) Clustering Algorithm
We use a clustering algorithm to regroup similar tropes and ethnicities together. This will allow for better data visualization as there will be more data per trope cluster.

### 2)
How does the alignment between casting choices and ideal character portrayals impact a movie's box office success? In other words, does closer adherence to the perfect casting choice correlate with higher revenue, while deviation from the ideal casting leads to lower financial returns?

### Part 1: Exploring and pre-processing the data
We are given a series of datasets in this corpus, with the metadata and tv tropes cluster being the data of most interest for us. This metadata is comprised of two dataframes, the movie metadata and the characters metadata. As indicated in the CMU Movie Summary Corpus ReadMe, these two dataframes have a many variables. Let us first identify the variables of interest for our story. <br>
- *Movie metadata: Wiki_movieID, Movie Name, Release Date, Box Office, Genres* <br>
- *Character metadata: Wiki_movieID, Release Date, Character Name, Gender, Height, Ethinicity, Actor Name, Age at Movie Release* <br>

**Step 1: Movie and Characters MetaData** <br>
    - We plot our variables of interest to visualise the coherence of our data before fixing any errors. <br>
    - We analyse the percentage of missing data, giving us insight on the datasets we should use to complete our study. <br>
    - We merge movies.metadata.tsv with characters.metadata.tsv to associate the characters with their respective genres, movie box office revenue and decade of release. <br>
    
**Step 2: TV Tropes** <br>
    - We pre-process our tvtropes.clusters.txt file and merge it with our merged character & movies metadata. We identify 501 character tropes with 72 unique tropes. <br>
    - We merge TV Tropes with Movie and Character MetaData. <br>
    - We complete key missing data. <br>
    - We visualise our data and further filter it by grouping tropes and ethnicities together. <br>
    
**Step 3: Extracting Actor Images** <br>
    - We extract the 350 actor images from [The Movie Database](https://www.themoviedb.org/) to create the Actor_image.csv dataset. <br>
    -  We generated a personal API to extract the images URL and store them in a csv file with corresponding actor names.  We will use Dlib, a widely used pre-trained facial landmark detector to identify 68 key points on the face, storing them as pairs of coordinates. They will in turn used to derive additional features that we will link to the actors for our study. [Dlib annotations emphasize the importance of resolution and head pose accuracy in landmark placement. Illumination, quality, and color have a relatively minor impact](https://essay.utwente.nl/86867/1/Meijerink_BA_EEMCS.pdf). <br>
    <p align = "center">
        <img src = "https://github.com/epfl-ada/ada-2023-project-adacadabra1000101/assets/145772112/a8839649-0450-4d0d-9b08-e1fdbca23b2e.png" width = "400" height = "400"> <br>
    </p>
    - Despite having high-quality images and a well-trained model, we still encounter head pose challenges. In the upcoming steps, we will explore methods to rotate a 3D face to a pose comparable to a standard face. From these standardized images, we will extract facial landmarks to enhance the performance of the chosen model. Additionally, the features calculated from the landmarks we will address proportional considerations, as length between landmarks does not provide information as we do not have a reference length.
    
### Part 2: Facial Image Analysis
**Step 4: Extracting Facial Features** <br>
    - We extract the facial features of our actor images using a facial recognition algorithm. <br>

**Step 5: Analysing and Selecting Facial Features** <br>
    - We analyse and select the facial features that are most pertinent to our study. <br>

### Part 3: Clustering our data
**Step 4: Clustering Facial Features** <br>
    - We cluster the similar facial features we identified earlier together. <br>

### Part 4: Data Analysis
**Step 5: Correlating with our tropes-characters-movies dataset** <br>
    - We correlate the obtained facial features with the other features given to us by CMU Movie Summary Corpus, to identify feature trends in function of character tropes.<br>

**Step 6: Analysis** <br>
    - We analyse our data and find answers to our research questions. <br>

### Part 5: Story-Telling
**Step 7: Web Design** <br>
    - We use our findings to create our story on the webpage. <br>

### Part 6: When the fun *finally* begins
**Step 8: Adding our own images** <br>
    - We add our own images and use what we found earlier to determine what character trope would suit each of us best. <br>

***BONUS step: Adding an interactive feature*** <br>
    - We add a feature where a user can upload his own image and/or fill a form. We would then analyse his image and/or form to show the character trope that suits the user best.

## Proposed Timeline
- 17.11: Pre-processing our movies & character metadata as well as tv tropes cluster. <br>
- 17.11: Extracting images from TMDB <br>
- 17.11: Extracting facial features from Actor_Images dataset <br>
↓ <br>
- P2 Milestone <br> 
↓ <br>
- Break - Homework 2 <br>
↓ <br>
- 05.12 - Clustering Facial Features <br>
↓ <br>
- 08.12 - Correlating with tropes-movies-characters dataset <br>
- 08.12 - Analysis <br>
↓ <br>
- 15.12 - Web Design <br>
↓ <br>
- 19.12 - Adding our own Images <br>
↓ <br>
- 22.12 - BONUS: Adding an interactive feature <br>
↓ <br>
- P3 Milestone - ADAcadabraaaa 🪄💫 <br>

    
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
    <td class="tg-0lax">Exploring and pre-processing movies & characters metadata and TV Tropes (except ethnicity) data<br><br>Writing the ReadMe</td>
  </tr>
  <tr>
    <td class="tg-0lax">CVoirol</td>
    <td class="tg-0lax">Converting ethnicity keys to strings using WikiData before grouping and simplifying them <br><br><br><br></td>
  </tr>
  <tr>
    <td class="tg-0lax">izushka</td>
    <td class="tg-0lax">Extracting actor images and their facial features from TMDB<br><br><br><br></td>
  </tr>
  <tr>
    <td class="tg-0lax">AnandaW0lz</td>
    <td class="tg-0lax">Extracting actor images and their facial features from TMDB<br><br><br><br></td>
  </tr>
  <tr>
    <td class="tg-0lax">Usermatthis</td>
    <td class="tg-0lax">Exploring and pre-processing movies & characters metadata and TV Tropes data<br><br><br><br></td>
  </tr>
</tbody>
</table>
