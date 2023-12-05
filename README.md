# Midterm Report

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
We have two main parts in our notebook: preprocessing and the actual regression. For preprocessing, we will need to clean up the data and engineer new features that could give the model a better chance at predicting the revenue. One of the first things we did was replace null values in each column with the means for numeric data and modes for non-numeric data. From there we created new features that told the model whether or not key things existed for the movie (tagline, homepage, etc.). From there, we parsed the genres of the movie and turned it into a one-hot encoding. We also parsed the date strings and turned them into separate day, month, and year categories. Finally, we went through the production companies and attached their id to each data point in addition to whether the production company was one of the 20 biggest or not. After data cleaning and feature engineering, we implemented some feature selection using the backward selection techniques. To explain further, we removed features one at a time and determined the significance of the feature in impacting the accuracy of the model. We then selected features that had a significance value above 0.0075 (signifance value being the difference in accuracy between using every feature and using every feature except the selected one). For the actual model, we utilized sklearn and its implementations of numerous regression models. We are currently using sklearn's RandomForestRegressor, as it provides suitable performance. Future steps for our team include testing out different regression models and trying other types of models, like neural networks for example.

## Potential Results and Discussion
We have two potential metrics we could predict given a movie's information: ratings or box office performance. These would both be quantitative measurements that could help producers determine if a movie would be successful or help movie-goers determine if a movie is worth watching. Since both values are numeric, we could utilize a loss metric like MSE to validate our results and help train our model. Our goal would be to be able to predict these values accurately given the title, genre, runtime, actors, directors, etc.

## Results

Through our analysis, we found that our model has suprising performnce on predicitng movie revenue. We were able to achieve a mean absolute error of 4.739 × 10^7. This corresspond to a score of 70.90% (we use the R2 score as our score metric). Through diagram below, we can see that our model is able to predict the revenue of a movie with a high degree of accuracy.

![image](https://github.com/rithwiks/4641_Team54/assets/62059099/522ea41a-a706-48bb-bd9b-812ddbd5dee2)

We benchmark this performance against other possible models, and we find that our performance surpasses other models. We use a simple random predcitive model, a linear regression, and a bayesian ridge regression model. Each of these models are highly applicable to our dataset, and we find that our random forest model outperforms each of these models.

We have attached a table showing the performance of each model below.

| Model           | Accuracy        |
| ------------- | ------------- |
| Random Forest (Our Model)      | 16078.215007 |
| Random      | 279683.563966 |
| Linear Regression      | 72571.414512 |
| Bayesian Ridge Regression      | 42988.025552 |

Overall, we are satisfied with the performance; we find clear places where the model learns identifiable characteristics and makes accurate predictions, as well as places where the model can be improved. It also points out areas where improvements are possible. This suggests a balanced view, recognizing the model's strengths in learning and prediction accuracy while also identifying potential areas for enhancement to refine its capabilities further.

Too see more visualizations, please refer to the [Model Performance Visualization](#model-performance-visualization) section below.


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

| Madeline Hartlage          | Rithwik Seth                   | Puneet Bagga                   | Dillon Greer         | Wonho Lim            |
| -------------------------- | ------------------------------ | ------------------------------ | -------------------- | -------------------- |
| Contribution Table         | Methods                        | Presentation                   | Intro & Background   | References           |
| Timeline                   | Potential Results & Discussion | Recording                      | Problem Definition   | GitHub Page          |
| Checkpoint                 | Presentation                   | Results & Discussion           | GitHub Page          | Results & Discussion |
| GitHub Page                | GitHub Page                    | GitHub Page                    | Results & Discussion | Visualizations       |
| Backward Feature Selection | Model Implementation           |                                |                      |                      |
| Methods                    | Data Preprocessing & Cleaning  |                                |                      |                      | 

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

# Results

## Dataset Visualization
### Dataset Overview
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/10f6e16e-5289-4194-92c3-159f8e5e2397)

The dataset summary above shows 23 attributes for 3000 movies in the dataset that we used for this project. It indicates all non-null counts and data types for each attribute. Attributes having many null entries means that it is optional data. Data types range from integers to objects, and the dataset occupies over 539 KB of memory in total.

### Movie Metrics Statistics
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/3f2a7acb-c753-4127-9995-b820d989f562)

The statistics aboce presents a statistical summary of five key metrics for a movie dataset: 'id', 'budget', 'popularity', 'runtime', and 'revenue', among 3000 records in total. It provides count, mean, standard deviation, minimum, quartiles, and maximum values. 'Budget' and 'revenue' show wide variations as indicated by their large standard deviations and ranges. The 'popularity' metric has a high maximum value, indicating that there is a outlier movies with exceptional popularity.

## Overview of Missing Data
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/f252f4bf-8fe2-4f87-814e-a0454971eed8)

The image above shows a count of missing values by each column in a movie dataset. It highlights that 'belongs_to_collection' and 'homepage' have the highest number of missing entries, telling that these are less frequently recorded attributes. Other columns like 'genres', 'overview', and 'tagline' also show missing data, but to a lesser extent. The dataset seems well-maintained for key identifiers like 'id', 'budget', 'imdb_id', and 'revenue', all with zero missing values, which could be crucial for analysis.

## Insights

### Movie Revenue Classification
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/804384ee-8fb7-46b0-8d41-c35ab2d3543c)

The bar chart above is showing the distribution of movies for revenue classifications. We have evenly distributed of movies across different revenue levels so that we can effectively analyze the proportion of movies that fall into each revenue category.

### Budget Allocation Across Different Revenue Tiers in Cinema
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/c8fb64ce-c33a-45c0-a98e-c1cf61fea120)

The box plot above is illustrating the range and distribution of movie budgets across five revenue classes: very low, low, medium, high, and very high. The boxes indicate the interquartile ranges of the budgets within each revenue class, with the lines inside the boxes representing the median budget values. Outliers are represented by circles above the whiskers of the boxes. The trend suggests that higher revenue classes tend to have higher median budgets and a wider range of budget values. Moreover, especially in very high level revenue class, the plot is suggesting that a few movies had significantly larger budgets than the most of their class. 

### Comparative Revenue Analysis of Movies Within Collections
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/16d529cb-051c-4a78-8d3b-d8813e6b2847)

The bar chart above compares the total revenue by movies that are part of a collection versus those that are not. The chart shows that movies in a collection significantly outperform those that are not, with the revenue for collection movies being significantly higher.

### Genre-Wise Box Office Revenue Comparison
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/71d6caf9-99f8-4205-9e73-adecdb2956b3)

The bar chart above provides a comparison of total revenue generated by movies across various main genres. Action, Adventure, and Science Fiction appear to have strong audience preference. On the other hand, genres like Documentary, Foreign, and Western show relatively lower total revenues.

### Disparity and Outliers in Genre-Specific Movie Revenues
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/9a1b0847-dfec-4467-a1a5-b480263d925c)

The box plot above illustrates the spread and outliers of movie revenues within genres. It reveals the median revenue, the interquartile range, and outliers for each genre. Action and Adventure genres show a higher median revenue and a greater range of revenue outcomes. However, genres like Documentary and Foreign have a lower median revenue and fewer outliers, suggesting more consistent but lower earnings.

### Genre Popularity Rankings in the Film Industry
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/5146c772-83c2-435d-b615-95e48cd5a273)

This bar chart shows the average popularity of movies across a range of genres, showing a clear trend where certain genres like Family, Science Fiction, and Adventure are more popular among audiences. Genres such as Foreign and Documentary are in the lower bound being consistent with analysis from earlier visualizations. We can also figure out that genres that often involve higher budgets and are more effects-driven tend to garner more popularity.

### Revenue Correlation with Varied Movie Features
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/c5c5bbe9-25f7-4e38-aa45-7b129937fdd4)


### Temporal and ID-Based Revenue Trends in Film
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/b1bd7fd8-6d5e-4cb7-b7d5-69c0f5687cd6)


### Financial Outcomes by Production Company Scale
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/4107828a-6f09-4e29-8978-a9fd6bd42446)


### Production Volume Comparison by Company Size
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/7faefb24-f609-451b-8579-048c64951dae)


### Linguistic Influence on Movie Revenue Success
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/297917f4-c21c-45e8-9821-6cfd857d7732)


### Revenue Variability Across Language Barriers
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/8ce03bbd-ed2b-46bf-b8f5-38b3e6debead)


### Film Industry Output by Language
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/d180cf65-0f46-40ee-a8be-a3b21ba0610a)


### Monthly Revenue Patterns in the Movie Industry
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/3b86a109-510b-4aea-9554-68820cc0d67d)


### Weekly Box Office Revenue Fluctuations
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/8ebdf2e9-d090-4220-823f-74930c31e788)


### Longitudinal Analysis of Movie Revenue Growth
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/c4c32bc2-18ad-43f2-88b5-969f2e2bf277)


### The Financial Impact of Movie Taglines
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/c4d2d666-9188-4b47-977d-aa7aea4680b3)


### Online Presence Correlation with Revenue
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/c73631bd-1edd-4ac8-b320-39574d0b15fb)


### Impact of Poster Availability on Movie Revenue
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/a37e63b8-1936-49a6-bc86-2352c0bdfeb0)


### Correlation Between Cast Size and Movie Revenue
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/e917b7bf-610b-4ee1-97dc-6cfe01f591b9)


### Budget Allocation vs. Revenue Generation in Movies
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/1b52adb0-9368-4198-87fa-6328c24842ce)


### Influence of Keyword Count on Movie Revenue
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/dbf7cb23-31e4-4221-a2be-c36cc3bdf2b2)


### Revenue Trends Across Movies with Multiple Genres
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/fc4cd85f-ad44-468c-9bcd-e6d109cff69c)



## Model Performance Visualization
### Comparison of Actual and Predicted Movie Revenues
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/522ea41a-a706-48bb-bd9b-812ddbd5dee2)\


### Distribution of Predicted vs. Actual Movie Revenues
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/1b679d95-ed5b-459b-b684-514c9ece2ff3)


### Scatter Analysis of Predicted Revenue vs. Actual Figures
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/56a7117e-bd94-4932-875d-bd7b6170dc6e)


### Residuals of Revenue Predictions for Movies
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/977314dc-0bed-4355-93b2-fa96f4bd8c2c)


### Feature Importance in Predicting Movie Revenue
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/806ce0b4-a61f-47f8-8b74-b07f1cb36e68)


###  Learning Curves of Model Training and Validation Error
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/7fa868cc-3a23-4aeb-8088-0cc123c96968)




