# KaggleCompetition 17/703
Playground Series - Season 3, Episode 6

This notebook show the final state of the code i used to get the **13th** position out of **703** for this kaggle regression competition : https://www.kaggle.com/competitions/playground-series-s3e6/

*Please note that many things were tested but are not present right here, only the final state of the notebook is presented*

## About the data
Before I explain how I approach the problem let’s talk about the data.
So, the data is quite simple no missing values, few outliers, only about 30 observations out of the [-2.5,2.5] standard deviation interval after applying z-score. There is no correlation between the variables (except for one pair) as you will see in the notebook.

## My approach
### 1.	Setting a reference value
The metric for this regression problem was the root mean square error rmse, I started by using an extreme gradient boosting without a proper limitation on its max_depth parameter i.e. **I used an algorithm that would perform and over fit**. The idea was to get as close as possible to the best possible value for the problem, on the training set the rme was about at **6k**.

### 2.	Trying to reach rmse = 6k on the out of fold Cross validation
*Quick answer*: I didn’t.
I started by trying to reach a rmse as close as possible to the gradient boosting while lowering the max depth, I reached a rmse of about **8-9k on the oof set**, which is close to the 6k. Because the oof results were like the ones on the training set, I knew I wouldn’t over fit too much on the testing set (the submission).

### 3.	Ensemble
I trained many other algorithms but I couldn’t get a rmse inferior to **40 k**, so I decided not to add them to create an ensemble, it is useless to aggregate algorithms that don’t perform well in the first place. 

### similarProject.ipynb
This file contains a similar project with a little more insights and less emphasis on the quality of the result 
