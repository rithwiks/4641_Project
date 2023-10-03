# Project Proposal

Author: Group 54
- Wonho Lim
- Dillon Rowe Greer
- Madeline Hartlage
- Rithwik Seth
- Puneet Singh Bagga

### distribution (temporary)
- Introduction/Background - Dillon
- Problem Definition - Dillon
- Methods - Rithwik/Puneet
- Potential Results - Rithwik/Puneet
- Discussion - Rithwik/Puneet
- References - Wonho
- Contribution - Madeline
- Timeline - Madeline
- Checkpoints - Madeline

## Topic

## Introduction/Background

## Problem Definition

## Methods
We have two main parts of the model: preprocessing and the actual regression. For preprocessing, we will need to clean up the data and transform some of the word-based features into some form of vectors. We could do this by encoding actors as a vector of the number of movies they have been in, the amount of money they have made, and the number of awards they have earned, for example. We also need to encode information like the plot of the movie, which we can do with a model like gensim's word2vec. Finally for the actual model, we can play around with multiple options, but in general we would need to use a regression model. We can test multiple, from linear to polynomial to ridge to see what will get us the best performance.

## Potential Results and Discussion
We have two potential metrics we could predict given a movie's information: ratings or box office performance. These would both be quantitative measurements that could help producers determine if a movie would be successful or help movie-goers determine if a movie is worth watching. Since both of these values are numeric, we could utilize a loss metric like MSE to validate our results and help train our model. Our goal would be to be able to predict these values accurately given the title, genre, runtime, actors, directors, etc. 
## References
1. Kalaivani, P., & Shunmuganathan, K. L. (2013). Sentiment classification of movie reviews by supervised machine learning approaches. Indian Journal of Computer Science and Engineering, 4(4), 285-292.
http://www.ijcse.com/docs/INDJCSE13-04-04-034.pdf
- This research paper focuses on movie preference anaysis based on of digital content on the internet like forums, review sites, blogs, and news outlets, which contains a lot of opinionated data. This research paper employees these resources to predict online user preferences by identifying and categorizing opinions that are available on internet. Specifically, the study focuses on sentiment analysis using online movie reviews for classification, which is closely related to our project. Investigation using three supervised machine learning algorithms - Support Vector Machines (SVM), Naive Bayes, and k-Nearest Neighbors (kNN) - this study have shown that that the SVM technique was superior, achieving accuracy rates of at least 80% when it is trained on an massive dataset. 
2. Latif, M. H., & Afzal, H. (2016). Prediction of movies popularity using machine learning techniques. International Journal of Computer Science and Network Security (IJCSNS), 16(8), 127.
https://www.researchgate.net/profile/Hammad-Afzal/publication/311913687_Prediction_of_Movies_popularity_Using_Machine_Learning_Techniques/links/586253ce08ae6eb871ab0748/Prediction-of-Movies-popularity-Using-Machine-Learning-Techniques.pdf
- This research paper also focuses on predicting a movie's performance in theaters which is influenced by everyone from casual viewers to esteemed producers, using machine learning techniques based on IMDB data. Especially, while new movies being released every week, the authors have shown the great opportunities for data mining in IMDB. However, it also suffered in usage of IMDB data which has great amount of varying data and a lot of missing fields. The authors were able to reach the highest accuray of 84%, using logistic and linear regression. The attributes that had higest contribution were metascore, number of votes, and Oscar awards won by the movies, and the number of screens the movie is going to be screened.
3. Agarwal, A., Das, R. R., & Das, A. (2021, October). Machine learning techniques for automated movie genre classification tool. In 2021 4th International Conference on Recent Developments in Control, Automation & Power Engineering (RDCAPE) (pp. 189-194). IEEE.
https://ieeexplore.ieee.org/abstract/document/9633422
- This paper focuses on a multilevel genre-based textual classification of automated sentiment analysis using machine learning algorithms. Their main goal was to analyze the sentiment of the scripts, counting their respective genres. The authors tested training and test accuracy on a dataset consisting of 15,187 scripts in total. The authors chekced the outcomes of different machine learning algorithms for the mentioned genres, and compared each algorithm to its best output. They also used a classification report with the accuracy percentages for both testing and training data sets. In conclusion, the Multinomial Naive Bayes Algorithm has shown to be the most accurate model among all textual genre classification models.

## Contribution

## Timeline

## Checkpoints
