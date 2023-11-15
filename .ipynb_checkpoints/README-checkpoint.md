# Decoding the DNA of our characters on the silver screen

## Abstract
Have you ever wondered why some actors keep getting cast in the same role? Why Dwayne Johnson always seems to plays the adventurous, headstrong and caring leader? Why Jason Staham is constantly cast as the gritty, hardboiled tough guy? And do these recurring casting choices lead to box office success? <br>
This phenomenon is called typecasting, in which an actor becomes strongly identified with particular roles, or characters having the same traits or coming from the same social or ethnic groups. In this study, we want to analyse the physical aspects of typecasting, by decoding the features *(gender, age, ethnicity and facial features)* of the actors playing these character tropes on the silver screen and observing them throughout time and genres, before associating these findings to the movie's success. These features will be analysed courtesy of both the CMU Movies Summary Corpus and a facial analysis algorithm.

## Research questions
In this study, we would like to answer these questions:
* How do physical attributes influence the casting based on character tropes?
* Do these preferences fluctuate over the decades and movie genres?
* What is the effect of these casting choices on a movie's box office success?

## Additional Datasets

### Part 1: Exploring and pre-processing the data
We are given a series of datasets in this corpus, with the metadata and tv tropes cluster being the data of most interest for us. This metadata is comprised of two dataframes, the movie metadata and the characters metadata. As indicated in the CMU Movie Summary Corpus ReadMe, these two dataframes have a many variables. Let us first identify the variables of interest for our story. <br>
- *Movie metadata: Wiki_movieID, Movie Name, Release Date, Box Office, Genres* <br>
- *Character metadata: Wiki_movieID, Release Date, Character Name, Gender, Height, Ethinicity, Actor Name, Age at Movie Release* <br>

**Step 1: Movie and Characters MetaData**
    - We plot our variables of interest to visualise the coherence of our data before fixing any errors. <br>
    - We analyse the percentage of missing data, giving us insight on the datasets we should use to complete our study. <br>
    - We complete key missing data *(Actor Ethnicity)*.
    - We merge movies.metadata.tsv with characters.metadata.tsv to associate the characters with their respective genres, movie box office revenue and decade of release. <br>
    
**Step 2: TV Tropes**
    - We pre-process our tvtropes.clusters.txt file and merge it with our merged character and movies metadata.
    - We identify 501 character tropes with 72 unique archetypes.

### Part 2: Clustering tropes together
    
 

