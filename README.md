# Final-Project
Flatiron School Capstone project

## Business Case
As the digital age continues to advance, the music industry has had to adapt to different measures of success when content is realeased. For example, CD album sales have been steadily declining as far back as 2000 to the point where major retailers like Best Buy stopped selling them altogether in 2018. Thanks to music-streaming services like Spotify and Apple Music, digital sales of albums seem to be following the same trend as sales have dropped from 24.6% to 17.3% between 2017 and 2018. (For reference, 1,500 streams equate to one album sale).

Due to the fact that users can pick and choose specifc songs from an artist's album to listen to, it is more difficult to gauge the reception of the full breadth of the artist's work through stream alone. This is why reviews of albums can show it's usefullness as it provides direct feedback to artists and labels about the entirity of their catalog. Through reviews from online users and critics alike, artists are able to get a better idea of what their fans like and dislike about the album, increase awareness of their content depending on how highly regarded it is, and ultimately make improvements on their next project. 

In this project, data was collected from www.metacritic.com and consisted of user reviews, critic reviews and other details of the albums on the website. These reviews were used to analyze the sentiment from each user to establish an NLP classification model that can accurately classify reviews as positive, neutral, or negative. 

Source:
https://www.statista.com/chart/12950/cd-sales-in-the-us/#:~:text=According%20to%20the%20Recording%20Industry,album%20topped%20the%20Billboard%20charts.
https://www.rollingstone.com/pro/news/album-sales-dying-as-fast-as-streaming-services-rising-774563/

## Goals of this project: 

(1) analyze album reviews; 

(2) gain an understanding on the words commonly used in positive, neutral, and negative reviews as well as reviews in different genres; 

(3) create an NLP classification model that can classifies reviews for artists and record label, to quickly gain qualitative insights from fan opinions on an album.



## Resources of data:
Album user reviews from: 
www.metacritic.com



## Approach:

1. Data collection - Webscraping (See Metacritc Scrape.ipynb)
2. Data cleaning
3. Explanatory Data Analysis
4. Preprocessing & feature engineering
5. Various model fitting
6. Topic modeling
7. Model evaluation


## Limitations and Discussion: 

### Class imbalance:

User the Vader Sentiment Intensity Analyzer, there were a significantly large amount of reviews that were classified as positive. It is possible that some reviews could have been missclassied i.e high user rating but classified as negative, so further analysis should be done on the differences between the classifications and the individual user rating for the reviews.

![Image](/images/sent_class.png)
![Image](/images/sent_class_crit.png)

### User Reviews:

Analyzing user reviews can also come with analyzing irrelavent data since user can type in whatever they want. Through analyzing the frequencies of bigrams and trigrams, many of the top words were just repeated a bunch of times in a single review and it was confirmed that it was indeed how the reviews appear on metacritic as well but 

### Word Cloud

After cleaning the review text removing stop words, word clouds were created to have a visual on which particular words were used most frequently between classes as well as certain genres. Below is an example of the word usage for positive reviews in Rock and Rap albums. As you can see, Rock fans typically mention the lyrics and sound while rap fans make references to a certain track on the album as well as the quality of the beats and production.

![Image](/images/rock_pos.png)
![Image](/images/rap_pos.png)


### Accuracy and F1 score metrics to evaluate sentiment classifer:

The metrics used to evaluate the models are the accuracy score and weighted f1 score. The final model used in both data sets was an SVM model which had an accuracy score of 0.890 and a weighted f1 score of 0.891 for user reviews, and an accuracy and weighted of 0.843 and 0.844 respectively for critic reviews. While this model performs well, it's understandable to consider the user's rating score as their overall opinion on an album. However, a benefit of using a sentiment classier over simply relying on the rating score is that it capturess the qualitative aspect of the opinions behind the review

### Future steps:

For some of the reviews, the ratings score differed from the sentiment that was classified with vader so further analysis would be needed to understand and correct these discrepancies. Additionally, I believe it would be fruitful to analyze the topics of album reviews in various genres to see which ones have more concrete distinctions between topics. Lastly, another stretch goal I would like to achieve with this project is to develop a text generator for the reviews of each class that can potentially used for automation.


## Project presentation link:

https://docs.google.com/presentation/d/1tPs0qnjlVUcwVU1b1fksZTFsY5wsC6oUXwni4a7K-R4/edit?usp=sharing
