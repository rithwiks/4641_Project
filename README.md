# Final Report

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
We have two main parts in our notebook: preprocessing and the actual regression. For preprocessing, we will need to clean up the data and engineer new features that could give the model a better chance at predicting the revenue. One of the first things we did was replace null values in each column with the means for numeric data and modes for non-numeric data. From there we created new features that told the model whether or not key things existed for the movie (tagline, homepage, etc.). From there, we parsed the genres of the movie and turned it into a one-hot encoding. We also parsed the date strings and turned them into separate day, month, and year categories. Finally, we went through the production companies and attached their id to each data point in addition to whether the production company was one of the 20 biggest or not. After data cleaning and feature engineering, we implemented some feature selection using the backward selection techniques. To explain further, we removed features one at a time and determined the significance of the feature in impacting the score of the model. We then selected features that had a significance value above 0.0075 (signifance value being the difference in score between using every feature and using every feature except the selected one).

For the actual model, we utilized sklearn and its implementations of numerous regression models. We utilized 3 models: Random Forest Regression, Linear Regression, and Bayesian Ridge Regression. We used the Random Forest regression since, as an ensemble model, it would be more robust when it comes to noise. We used the linear regression model as a second good baseline comparison, and to see if revenue was linearly related to our input. We implemented Bayesian Ridge Regression as it provided a way to regularize linear regression, which would lead to better results. Finally, we used a random number generator to evaluate our models against a completely random model.

## Potential Results and Discussion
We have two potential metrics we could predict given a movie's information: ratings or box office performance. These would both be quantitative measurements that could help producers determine if a movie would be successful or help movie-goers determine if a movie is worth watching. Since both values are numeric, we could utilize a loss metric like MSE to validate our results and help train our model. Our goal would be to be able to predict these values accurately given the title, genre, runtime, actors, directors, etc.

**update

Upon further evaluation, we decided upon predicting just box office revenuew. We found that tyring to predict ratings is extremely volatile, and is very noisy for our models to identify patterns. Box office reveneue was a more direct relationship to the features we had, and we were able to achieve a higher score with this metric.

We use the following metrics to evaluate our model:
 - Mean Absolute Error (MAE)
 - Mean Squared Error (MSE)
 - R2 Score
 - Relative MAE

View the [Results](#results) section below for more information.

## Results

Through our analysis, we found that our model has suprising performnce on predicitng movie revenue. We were able to achieve a mean absolute error of 4.739 × 10^7. This corresspond to a score of 70.90% (we use the R2 score as our score metric). Through diagram below, we can see that our model is able to predict the revenue of a movie with a high score.

![image](https://github.com/rithwiks/4641_Team54/assets/62059099/522ea41a-a706-48bb-bd9b-812ddbd5dee2)

We benchmark this performance against other possible models, and we find that our performance surpasses other models. We use a simple random predcitive model, a linear regression, and a bayesian ridge regression model. Each of these models are highly applicable to our dataset, and we find that our random forest model outperforms each of these models.

We have attached a table showing the performance of each model below. We use a scaled mean absolute error as our metric, and we find that our model outperforms each of the other models. This metric is also referred to as relative MAE.

| Model           | MAE (mean absolute error)        |
| ------------- | ------------- |
| Random Forest (Our Model)      | 1.607822e+04 |
| Random      | 1.787770e+06 |
| Linear Regression      | 2.797153e+05 |
| Bayesian Ridge Regression      | 2.650542e+05 |

Overall, we are satisfied with the performance; we find clear places where the model learns identifiable characteristics and makes accurate predictions, as well as places where the model can be improved. It also points out areas where improvements are possible. This suggests a balanced view, recognizing the model's strengths in learning and prediction score while also identifying potential areas for enhancement to refine its capabilities further.


This implies that our model has a higher affinity for predictinng the box office revenue of a movie than other models. Using the movie production information such as budget, crew, actors, language, and more, we are able to estimate the box office revenue to within $40 million. This is a significant improvement over other models we test, and we are able to achieve this by using a random forest model. We find that our model is able to predict the revenue of a movie with a high score, performs better than the other models, and beats the baseline model (random precitions) by a large margin.


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
| Backward Feature Selection | Model Implementation           | Presentation                   |                      | Presentation         |
| Methods                    | Data Preprocessing & Cleaning  | Final Recording                |                      | Final Recording      | 
| Presentation               | Presentation                   |                                |                      |                      | 
| Final Recording            | Final Recording                |                                |                      |                      | 

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

# Additional Information

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

### Relationship Between Production Company ID and Movie Revenue
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/c5c5bbe9-25f7-4e38-aa45-7b129937fdd4)

The scatter plot above visualizes the relationship between production_id and revenue. We cam tell that there is a large concentration of data points with lower production IDs associated with a wide range of revenues. There's no clear trend suggesting a correlation between production ID and revenue, as the production ID is likely an arbitrary or sequential number assigned to companies.

### Link Between Movie Popularity and Box Office Revenue
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/b1bd7fd8-6d5e-4cb7-b7d5-69c0f5687cd6)

The scatter plot above depicts the relationship between a movie's popularity and its box office revenue. The spread of data points indicates that movies with higher popularity tend to have a wide range of revenue outcomes, including some of the highest revenues observed. However, there are also less popular movies that achieve significant box office success, suggesting that popularity is not the sole determinant of financial performance.

### Financial Outcomes by Production Company Scale
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/4107828a-6f09-4e29-8978-a9fd6bd42446)

The box plot titled  compares the revenue distribution between movies produced by small/medium-sized companies and large production companies. The plot for big production companies displays a higher median revenue, greater interquartile range, and more high-revenue outliers, indicating that larger companies often yield more financially successful movies. In contrast, small/medium-sized companies show lower median revenues and fewer outliers, highlighting the financial disparities in the movie industry based on company size.

### Production Volume Comparison by Company Size
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/7faefb24-f609-451b-8579-048c64951dae)

The bar chart above compares the number of movies produced by small/medium companies versus large companies. The chart indicates that both small/medium and big production companies have significant outputs, with big companies producing slightly fewer movies than their smaller counterparts. This could suggest that while large companies may focus on fewer, potentially higher-budget films, small/medium companies contribute a substantial number of films to the market.

### Linguistic Influence on Movie Revenue Success
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/297917f4-c21c-45e8-9821-6cfd857d7732)

The bar chart above compares the total revenues of movies by their language. The category '0' represents non-English movies, and '1' represents English-language movies. Also, it shows that English-language movies have substantially higher total revenues compared to non-English ones.

### Revenue Variability Across Language Barriers
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/8ce03bbd-ed2b-46bf-b8f5-38b3e6debead)

The box plot above shows the distribution of movie revenues differentiated by language: Non-English versus English. The box plot for English language movies displays a higher median revenue and a greater range of revenue outcomes, with several outliers indicating movies that have achieved exceptional box office success. In contrast, Non-English movies have a lower median revenue and fewer high-revenue outliers. Thus, we can say that English language movies tend to be more financially successful on average.

### Film Industry Dominance by Language
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/d180cf65-0f46-40ee-a8be-a3b21ba0610a)

The bar chart above compares the number of movies produced in English versus Non-English languages. The chart shows a significantly larger number of Non-English language movies are there compared to English language movies, indicating a greater global film dominance in languages other than English. We can also tell that while the English based movies have higher average revenue, there are still way more non-English based movies in the industry.

### Monthly Revenue Patterns in the Movie Industry
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/3b86a109-510b-4aea-9554-68820cc0d67d)

The bar chart above illustrates the total movie revenue for each month. It shows that at certain months, particularly on July, movies generate significantly higher revenues. There's a noticeable drop in the eighth and ninth months, with a subsequent rise towards the end of the year. 

### Weekly Box Office Revenue Fluctuations
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/8ebdf2e9-d090-4220-823f-74930c31e788)

The bar chart above displays the variation in movie revenues across different days of the week. The chart indicates that the second day of the week sees the highest revenue. The revenue appears to decline towards the middle of the week and then slightly increases again.

### Longitudinal Analysis of Movie Revenue Growth
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/c4c32bc2-18ad-43f2-88b5-969f2e2bf277)

The scatter plot above presents the trend of movie revenues over time, from 1920 to approximately 2020.  The plot shows a clear upward trend in maximum revenues as time progresses, with a significant increase in higher revenue movies in more recent years.

### The Financial Impact of Movie Taglines
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/c4d2d666-9188-4b47-977d-aa7aea4680b3)

The bar chart above compares total revenues between movies with and without taglines. The '0' category, representing movies without taglines, shows considerably lower revenue compared to the '1' category, representing movies with taglines. This suggests that the presence of a tagline might be correlated with higher movie revenue.

### Online Presence Correlation with Revenue
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/c73631bd-1edd-4ac8-b320-39574d0b15fb)

The bar chart above compares total movie revenues based on whether a movie has a homepage(website). The category '0' denotes movies without an online presence, while '1' indicates movies with one. The chart shows that movies with an online presence generate significantly higher revenues than those without. Thus we can suggests that having a digital footprint can be a substantial factor in a movie's financial success.

### Impact of Poster Availability on Movie Revenue
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/a37e63b8-1936-49a6-bc86-2352c0bdfeb0)

The bar chart aboves compares - actually, there is not even enough source to compare - the total movie revenues based on the availability of posters. The '0' category, which represents movies without available posters, shows perfectly lower revenue compared to the '1' category, representing movies with posters. This suggests that having a poster, which is a basic marketing tool, is perfectly associated with higher movie revenue.

### Correlation Between Cast Size and Movie Revenue
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/e917b7bf-610b-4ee1-97dc-6cfe01f591b9)

The scatter plot above illustrates the relationship between the size of a movie's cast and its revenue. The plot shows that there is no clear linear correlation between the number of cast members and the revenue a movie generates. There is a dense cluster of points at lower cast sizes, indicating that movies with smaller casts can achieve a wide range of revenue outcomes. However, the data also shows that having a large cast does not necessarily equate to higher revenue. This suggests that factors other than cast size are more decisive in determining a movie's financial success.

### Budget Allocation vs. Revenue Generation in Movies
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/1b52adb0-9368-4198-87fa-6328c24842ce)

The scatter above shows the relationship between a movie's budget  and the revenue it generates. The distribution of data points shows a trend where movies with higher budgets tend to have the potential for higher revenues, but there is considerable variance. Not all high-budget movies result in high revenue, indicating that while budget is a factor, it does not guarantee financial success. There are also movies with relatively low budgets achieving significant revenue, highlighting the complexity of the factors that contribute to a movie's financial outcome.

### Influence of Keyword Count on Movie Revenue
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/dbf7cb23-31e4-4221-a2be-c36cc3bdf2b2)

The scatter plot above visualizes the relationship between the number of keywords associated with a movie and its revenue. The distribution of data points does not indicate a clear linear relationship. However, it still shows a wide variance in revenue across movies with similar keyword counts. Some movies with a low count of keywords have high revenue, and the opposite is also there, suggesting that the number of keywords alone is not that strong predictor of movie revenue.

### Revenue Trends Across Movies with Multiple Genres
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/fc4cd85f-ad44-468c-9bcd-e6d109cff69c)

The bar chart above illustrates the relationship between the number of genres a movie is categorized under and its total revenue. We can suggests that movies classified under four genres tend to generate the highest revenue. The chart shows a general increase in revenue as the number of genres increases from two to four, after which the revenue appears to decline. 

## Model Performance Visualization

### Comparison of Actual and Predicted Movie Revenues
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/522ea41a-a706-48bb-bd9b-812ddbd5dee2)\

This graph presents a comparative analysis of actual versus predicted movie revenues. Each movie is represented by an index on the horizontal axis. The blue line indicates actual revenues, while the orange line shows the predicted revenues for each movie. The red line depicts the absolute difference between the actual and predicted values, serving as an indicator of the prediction accuracy. The spikes in the absolute difference line suggest areas where the prediction model deviated significantly from the actual revenue. Overall, the visualization is useful for assessing the performance of the revenue prediction model across a dataset of movies.

### Distribution of Predicted vs. Actual Movie Revenues
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/1b679d95-ed5b-459b-b684-514c9ece2ff3)

This histogram compares the frequency distribution of predicted and actual movie revenues. The horizontal axis represents revenue, while the vertical axis indicates the frequency of movies falling into each revenue bracket. The blue bars represent predicted revenues, and the red bars indicate actual revenues. The overlap of the two distributions suggests areas where our prediction model aligns closely with the actual revenue figures. The differences in height between the corresponding bars of actual and predicted revenues indicate inaccuracy in the model's predictions. This visual helps to identify the accuracy of the revenue prediction model and its distribution pattern relative to the actual revenue data.

### Scatter Analysis of Predicted Revenue vs. Actual Figures
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/56a7117e-bd94-4932-875d-bd7b6170dc6e)

This scatter plot depicts the relationship between actual and predicted movie revenues, with actual revenue on the x-axis and predicted revenue on the y-axis, both measured up to 1 billion. The dashed diagonal line represents the line of equality, where the predicted revenues match the actual revenues. Data points closely aligned with this line indicate accurate predictions. The plot shows that for lower revenue values, the predictions are closely clustered around the line of equality, suggesting high performance / score in this range. However, for higher revenue movies, the predictions are more scattered, indicating less precision in the model's predictions. This visualization highlights the model's performance and can be used to identify the range of revenue values for which the model's predictions are most and least reliable.

### Residuals of Revenue Predictions for Movies
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/977314dc-0bed-4355-93b2-fa96f4bd8c2c)

This residual plot assesses the discrepancies between predicted and actual movie revenues. The horizontal axis represents the predicted revenue, while the vertical axis shows the residuals, which are the differences between the actual revenue and the predicted revenue. A residual of zero, marked by the red line, would mean the prediction was exactly correct. Points above the line indicate an underestimation, and points below represent an overestimation by our predictive model. The concentration of data points close to the red line at lower revenue predictions suggests that the model is more accurate in this range. However, the presence of points further away from the line, especially at higher revenue predictions, indicates larger errors, signifying potential overfitting or model limitations in capturing the factors that drive higher revenues.

### Feature Importance in Predicting Movie Revenue
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/806ce0b4-a61f-47f8-8b74-b07f1cb36e68)

This horizontal bar chart ranks the relative importance of different features used in our model to predict movie revenues. The 'budget' and 'popularity' features have the highest importance, indicating a strong influence on revenue prediction. 'Belongs_to_collection' also shows significant importance, suggesting that movies in a series or franchise tend to have predictable revenue streams. Other features like 'num_cast', 'production_id', and 'num_crew' have moderate importance. Features related to the release timing, such as 'release_year' and 'release_month', appear to have less influence compared to financial and popularity metrics. Attributes like 'homepage_exists', 'in_english', 'tagline_exists', and 'poster_exists' have the least importance, indicating they might be less critical in predicting revenue, at least within the context of this model. This chart is crucial for understanding which variables are most predictive of financial success and can guide producers and marketers in their decision-making processes.

###  Learning Curves of Model Training and Validation Error
![image](https://github.com/rithwiks/4641_Team54/assets/62059099/7fa868cc-3a23-4aeb-8088-0cc123c96968)

This learning curve graph depicts the Mean Squared Error (MSE) of our predictive model as a function of the training set size. The blue line represents the training error, which decreases and then levels off as more data is used, suggesting the model is learning effectively from the training data. The orange line represents the validation error, which starts high and decreases as the training set size increases, indicating the model is generalizing better to new data with more training examples. However, the persistence of a gap between the training and validation error lines suggests there is still some overfitting, as the model performs better on the training data than on unseen validation data. Ideally, the two lines would converge, indicating a model that performs consistently well on both training and validation sets. The plateauing of both curves suggests that adding more data may not lead to significant improvements in the model's performance, and attention may need to be turned to model complexity or feature engineering for further enhancements.
