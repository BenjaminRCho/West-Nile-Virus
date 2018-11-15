# West Nile Virus

### This Repo Includes:

1. West Nile Virus Project
    -Notebook contains code for the project
2. Data
    -Folder containing the data required to run code

### Objective
Time series data analysis are most commonly seen when monitoring industrial processes or tracking corporate business metrics. The analysis accounts for any correlation, trend or seasonal variation in the data points that were taken over time. I will be discussing one approach and method on how to process the data and make predictions. To demonstrate time series analysis, I did a project on the West Nile Virus dataset taken from Kaggle.

Every year, people in Chicago are diagnosed with the West Nile Virus. The virus is spread by mosquitoes of the Culex species. While less than one percent of people infected by West Nile virus develop life-threatening symptoms, people over the age of 60 are at the highest risk especially patients with kidney conditions, diabetes, high blood pressure, or a weakened immune system. In hopes of reducing West Nile virus outbreaks, public health workers set up mosquito traps around Chicagoland every year from late spring to fall to trap mosquitoes and then detect the mosquitoes infected with West Nile virus. Using past West Nile mosquito data, we will predict which parts of Chicagoland West Nile mosquitoes will be and we will predict at what times we will detect these occurrences.

As with any data science problem, exploring the data is the most important process before stating a solution. The dataset collected had data on Chicago weather, mosquitoes and mosquito traps. I first cleaned the three data sources for any missing or invalid measurements. The next step was to conduct feature engineering on our weather data. This is probably the most important aspect because theres a high correlation on how the mosquitoes develop the virus depending on the time and weather.

### Feature Engineering
Our Chicago weather dataset contains measurements from two different stations. To take account for a more generalized weather, I created a new dataset by taking the average of all the data for each day. Now for the fun part, I engineered some features to better quantify how the weather impacts the mosquito population in Chicago. In order to be figure out what kind of features I needed, some research on the subject matter, such as the life cycle of mosquitoes, was done.

The first feature created is to quantify the number of days since it last rained. Ideally, there should be a positive correlation between the number of days since it rained with the number of mosquitoes. The longer it doesn’t rain the more likely we will see a decrease in the number of mosquitoes present in Chicago.

The second feature was for the total time from sunrise to sunset. I wanted to explore whether a longer day or shorter day would have an effect on the virus because mosquitoes tend to be more active during the day compared to at night. It seemed more important to interpret the total time the sun has been up than just the time the sun came up and down.

My last idea created was to get the weather conditions from previous days and see if there was an effect on the number of mosquitoes and the virus. I believe that this is a very important deciding factor. Generally speaking, a mosquito’s life span goes from three to two weeks during the summer, sometimes longer. Weather conditions such as maximum temperature, or total precipitation from previous days play a huge role in the growth and reproduction of the insect. In this case, I decided to include weather conditions from one, three, seven and fourteen days ago because I wanted to cover the spectrum of their life cycle. From the earliest to the latest a mosquito egg can become an adult mosquito. 

### Building the model
In our three sources of data, I divided them into two sets: training and testing. I used the training data to train my model for more accurate predictions and used the test data to see how accurate the model was on unseen data. There were three classification models built: Random Forest Classifier, Logistic Regression, and Gradient Boosting Classifier. Out of the three models, Gradient Boosting Classifier was the model performed the best with an accuracy score of 0.825. After submitting my predicted values to Kaggle to test how well the model performed, I got an accuracy score of 0.74, which places me around top 500 spot.

All in all, my model is fairly decent but definitely can be improved on. For future study, I would like to see if there is more data to be used because I wasn’t able to include the spray data into my model. I believe Kaggle purposely did not include the right data to introduce a real world problem, data leakage. Finally, if we were to give a cost benefit analysis on how the city of Chicago should prevent West Nile Virus then we wouldn’t be able to give a fully supported conclusion. Even though we can predict to a certain extent the locations of the virus being present, it is still hard to make a suggestion on an optimal solution. There are too many factors in determining the cost for the city that was not presented in the data. Nonetheless, a life is always worth more than any cost so trying to prevent the disease from spreading should be prioritized over minimizing costs.