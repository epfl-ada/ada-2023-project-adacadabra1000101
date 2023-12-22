# Decoding the DNA of our characters on the silver screen

## Abstract
Have you ever wondered why some actors keep getting cast in the same role? Why Dwayne Johnson always seems to plays the adventurous, headstrong and caring leader? Why Jason Staham is constantly cast as the gritty, hardboiled tough guy? And do these recurring casting choices lead to box office success? <br>
This phenomenon is called typecasting, in which an actor becomes strongly identified with particular roles, or characters having the same traits or coming from the same social or ethnic groups. The CMU Movies Summary Corpus has already observed 501 recurring character tropes. In this study, we want to analyse these tropes, by decoding the features *(gender, age, height, ethnicity and facial features)* of their actors observing them throughout time and movie genres, before correlating these findings to the movie's box office success.  


_**Please find our code and results for Milestone P3 in milstone_p3.ipynb**_


## Research questions
In this study, we would like to explore whether specific actor types are associated with particular character tropes and what are the specific features for each trope.

### Subquestions for story telling
* Do casting choices perpetuate stereotypes?
* Did certain films establish a trend in typecasting, where actors are selected based on their similarity to a particularly influential portrayal in a specific role?
* In what type of role would you find yourself typecasted in?

## Additional Datasets
- Images of actors: We construct our own dataset containing good quality face images of the actors of interest (#347). We obtain the images from [The Movie DataBase](https://www.themoviedb.org/) (TMDB). To see more detail, consult Step 3. <br>
- [WikiData](https://query.wikidata.org/sparql): We use WikiData to convert our ActorEthnicities values from keys to usable, readable strings. 

## Addtional Files
We have exported some of the dataframes we have constructed in the .ipynb files into .csv files, in order to access them more easily, without having to rerun the code each time, as some of the functions returning the dataframes took quite long to run. The files are the following and can be found in data/our_datasets: 

- **actors_with_tropes.csv** : contains only the actors that have a trope associetated to their character (contains doubles)

- **actor_images.csv** : 4 columns (Actor,Image URL,Image height,Image width) and 351 rows

- **actor_features.csv** : 3 columns (Actor's name, actor landmakrs (series), actor encodings (array)), 350 rows (1 row per actor)

- **tropes_characters_ethnicity.csv** : dataset extracted during P2 milestone, containing the following columns: Freebase_charactermap,Trope,CharacterName,ActorName,ActorAge,ActorDOB,ActorEthnicity Label,ActorGender,ActorHeight,Freebase_actorID,MovieName,Genres,Decade,ReleaseDate,BoxOffice,Freebase_movieID,Wiki_movieID,StrActorEthnicity (501 rows)

- **merge_features_filtered.csv** : dataframe that is the merge of tropes_characters_ethnicity and actor_features. It contains addtional columns for the euclidean distance between each character

We have also one additional notebook used to generate some of the datasets above:

- **people_images.ipynb** : jupyter notebook in which the functions to create actor_images.csv and actor_features.csv are defined 

## Methods
### 1) Supervised Machine Learning for Classification
We want to find the function, y=F(X), that links the actor's features to the character trope played. We are given input/output pairs (X, y) with y beeing categorical and representing the differnt movie tropes and X the list of actor features, both continous and categorical. For this we use and compare differnt classification algorithms. We go through Decision Trees, kNN, ordinary least squares (OLS) and Supervised Neural Network algorithm.<br>

### 2) Unsupervised Machine Learning for Clustering
We want to see whether actors playing the same tropes ressemble each other, and therefore cluster together. We only concentrate on the facial features of the actors in order to obtain the clusters (use of the euclidean distance between actors). We are also interesting in finding tropes that cluster together 


## Project Structure
### Part 1: Exploring and pre-processing the data
We identify the datasets of interest and their variables: *movies.metadata.tsv*, *characters.metadata.tsv* and *tvtropes.clusters.txt*. <br>
- *Movie metadata: Wiki_movieID, Movie Name, Release Date, Box Office, Genres* <br>
- *Character metadata: Wiki_movieID, Release Date, Character Name, Gender, Height, Ethinicity, Actor Name, Age at Movie Release* <br>

**Step 1: Exploring Movie and Characters MetaData** <br>
    - We plot our variables of interest and their missing data to visualise distributions, range and/or aberrant outliers. <br>
    - We merge movies.metadata.tsv with characters.metadata.tsv to associate the characters with their respective genres, movie box office revenue and decade of release. <br>
    
**Step 2: TV Tropes** <br>
    - We merge tvtropes.clusters.txt with our merged character & movies metadata. We identify 501 character tropes with 72 unique tropes. <br>
    - We do univariate and bivariate exploratory data analysis for our variables of interest. <br>
    
**Step 3: Extracting Actor Images** <br>
    - We extract the 350 actor images from [The Movie Database](https://www.themoviedb.org/) to create the Actor_image.csv dataset. Please see our project-P2-milestone for more details <br>
    - Despite having high-quality images and a well-trained model, we still encounter head pose challenges. In the upcoming steps, we will explore methods to rotate a 3D face to a pose comparable to a standard face. From these standardized images, we will extract facial landmarks to enhance the performance of the chosen model. <br>
    
### Part 2: Facial Image Analysis
**Step 4: Extracting Facial Features** <br>
    - We use the extracted coordinates to derive additional facial features of our actor images.<br>

**Step 5: Analysing and Selecting Facial Features** <br>
    -<br>

### Part 3: Classifying our data
**Step 6: Putting all the features together** <br>
    - We select the features, obtained from tropes-character-movies and the facial image analysis. <br>
    - We select a model and tune its parameters <br>

### Part 4: Data Analysis
**Step 7: Analysis** <br>
    - We analyse our data and find answers to our research questions. <br>
    - We also use t-test to test whether tropes are similar to each other <br>

### Part 5: Story-Telling
**Step 8: Web Design** <br>
    - We use our findings to create our story on the webpage. <br>

## Proposed Timeline
- 17.11: Pre-processing our movies & character metadata as well as tv tropes cluster. <br>
- 17.11: Extracting images from TMDB <br>
- 17.11: Extracting facial features from Actor_Images dataset <br>
↓ <br>
- P2 Milestone <br> 
↓ <br>
- Break - Homework 2 <br>
↓ <br>
- 05.12 - Classifying our data <br>
↓ <br>
- 08.12 - Analysis and Model Selection <br>
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
    <td class="tg-0lax">Exploring and pre-processing movies & characters metadata and TV Tropes (except ethnicity) data<br><br><br>Writing the ReadMe</td>
  </tr>
  <tr>
    <td class="tg-0lax">CVoirol</td>
    <td class="tg-0lax">Converting ethnicity keys to strings using WikiData before grouping and simplifying them, Converting the tvtropes file to a dataframe <br><br><br><br></td>
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
    <td class="tg-0lax">Exploring and pre-processing movies & characters metadata and TV Tropes (execept ethnicity) data<br><br><br><br></td>
  </tr>
</tbody>
</table>
