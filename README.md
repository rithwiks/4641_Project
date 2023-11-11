# Project Proposal

Author: Group 54
- Wonho Lim
- Dillon Rowe Greer
- Madeline Hartlage
- Rithwik Seth
- Puneet Singh Bagga

## Topic
Predicting Movie Gross
## Introduction/Background
Predicting how well a movie will do in the box office is a complex task that can depend on many variables such as the movie's genre, actors, director, budget, and even the release date. Some research has been done on this topic as movies are high-budget projects with a lot riding on their success. However, many of them contain incomplete datasets as well as only look to determine the ratings but not the revenue a movie can produce. We will strive to look at both of these quantitative results in our model and better some of the previous models made which are listed in our references below. Our data set contains lists of the actors, cast, director, and genre of each movie with its rating and revenue. It also includes other movies in which these people were so we will be able to create a more well-rounded model.

## Problem Definition
The problem here lies both in the inconsistency of results from previous models as well as the lack of looking at revenue. Since all of the crew and actors must be paid, having a movie that will have a higher revenue will benefit those who are helping create these movies. This has come to the forefront today as there has been a recent strike between writers and movie studios over many issues involving financial concerns with movies and other forms of media. We are hoping that putting writers on projects that will be profitable in the long run will allow them to have a more stable income and job security.

## Methods
We have two main parts in our notebook: preprocessing and the actual regression. For preprocessing, we will need to clean up the data and engineer new features that could give the model a better chance at predicting the revenue. One of the first things we did was replace null values in each column with the means for numeric data and modes for non-numeric data. From there we created new features that told the model whether or not key things existed for the movie (tagline, homepage, etc.). From there, we parsed the genres of the movie and turned it into a one-hot encoding. We also parsed the date strings and turned them into separate day, month, and year categories. Finally, we went through the production companies and attached their id to each data point in addition to whether the production company was one of the 20 biggest or not. For the actual model, we utilized sklearn and its implementations of numerous regression models. We are currently using sklearn's RandomForestRegressor, as it provides suitable performance. Future steps for our team include testing out different regression models and trying other types of models, like neural networks for example.

## Potential Results and Discussion
We have two potential metrics we could predict given a movie's information: ratings or box office performance. These would both be quantitative measurements that could help producers determine if a movie would be successful or help movie-goers determine if a movie is worth watching. Since both values are numeric, we could utilize a loss metric like MSE to validate our results and help train our model. Our goal would be to be able to predict these values accurately given the title, genre, runtime, actors, directors, etc. 
## References
1. Kalaivani, P., & Shunmuganathan, K. L. (2013). Sentiment classification of movie reviews by supervised machine learning approaches. Indian Journal of Computer Science and Engineering, 4(4), 285-292.
http://www.ijcse.com/docs/INDJCSE13-04-04-034.pdf
- This research paper focuses on movie preference analysis based on of digital content on the internet like forums, review sites, blogs, and news outlets, which contain a lot of opinionated data. This research paper employs these resources to predict online user preferences by identifying and categorizing opinions that are available on the internet. Specifically, the study focuses on sentiment analysis using online movie reviews for classification, which is closely related to our project. Investigation using three supervised machine learning algorithms - Support Vector Machines (SVM), Naive Bayes, and k-Nearest Neighbors (kNN) - this study has shown that the SVM technique was superior, achieving accuracy rates of at least 80% when it is trained on a massive dataset. 
2. Latif, M. H., & Afzal, H. (2016). Prediction of movie popularity using machine learning techniques. International Journal of Computer Science and Network Security (IJCSNS), 16(8), 127.
https://www.researchgate.net/profile/Hammad-Afzal/publication/311913687_Prediction_of_Movies_popularity_Using_Machine_Learning_Techniques/links/586253ce08ae6eb871ab0748/Prediction-of-Movies-popularity-Using-Machine-Learning-Techniques.pdf
- This research paper also focuses on predicting a movie's performance in theaters which is influenced by everyone from casual viewers to esteemed producers, using machine learning techniques based on IMDB data. Especially, while new movies are being released every week, the authors have shown the great opportunities for data mining in IMDB. However, it also suffered in the usage of IMDB data which has a great amount of varying data and a lot of missing fields. The authors were able to reach the highest accuracy of 84%, using logistic and linear regression. The attributes that had highest contribution were metascore, number of votes, Oscar awards won by the movies, and the number of screens the movie is going to be screened.
3. Agarwal, A., Das, R. R., & Das, A. (2021, October). Machine learning techniques for automated movie genre classification tool. In 2021 4th International Conference on Recent Developments in Control, Automation & Power Engineering (RDCAPE) (pp. 189-194). IEEE.
https://ieeexplore.ieee.org/abstract/document/9633422
- This paper focuses on a multilevel genre-based textual classification of automated sentiment analysis using machine learning algorithms. Their main goal was to analyze the sentiment of the scripts, counting their respective genres. The authors tested training and test accuracy on a dataset consisting of 15,187 scripts in total. The authors chekced the outcomes of different machine learning algorithms for the mentioned genres, and compared each algorithm to its best output. They also used a classification report with the accuracy percentages for both testing and training data sets. In conclusion, the Multinomial Naive Bayes Algorithm has been shown to be the most accurate model among all textual genre classification models.

## Contribution
Contribution Table

| Madeline Hartlage          | Rithwik Seth                   | Puneet Bagga                   | Dillon Greer         | Wonho Lim      |
| -------------------------- | ------------------------------ | ------------------------------ | -------------------- | -------------- |
| Contribution Table         | Methods                        | Presentation                   | Intro & Background   | References     |
| Timeline                   | Potential Results & Discussion | Recording                      | Problem Definition   | GitHub Page    |
| Checkpoint                 | Presentation                   | Results & Discussion           | GitHub Page          | Visualizations |
| GitHub Page                | GitHub Page                    | GitHub Page                    | Results & Discussion |                |
| Backward Feature Selection | Model Implementation           |                                |                      |                |
| Methods                    | Data Preprocessing             |                                |                      |                | 

## Timeline
Gantt Chart <br />
https://1drv.ms/x/s!ArIjml_oEP6hiXQ_k4jeQjR8svcR?e=d1LcwV&nav=MTVfezAwMDAwMDAwLTAwMDEtMDAwMC0wMTAwLTAwMDAwMDAwMDAwMH0

## Checkpoint
### Dataset 
https://www.kaggle.com/datasets/ashpalsingh1525/imdb-movies-dataset
### Proposal (October 6th)
- Report and presentation finished by October 6th
### Midterm Report (November 10th)
- Model 1 design and selection by October 12th
- Data cleaned and pre-processed by October 18th
- Model 1 coded by November 2nd
- Data visualization complete by November 7th
- Results and report completed by deadline November 10th
### Final Report (December 5th)
- Model 2 design and selection by November 12th
- Data cleaned and pre-processed by November 15th
- Model 2 coded by November 29th
- Data visualization complete by December 1st
- Results and model comparisons documented by December 3rd
- Conclusions and contributions complete by December 4th
- Final presentation slides complete by December 5th
- Final report and recording complete by deadline December 5th
