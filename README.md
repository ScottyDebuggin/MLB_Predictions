# Major League Baseball (MLB) Data Processing and RNN Modeling


## Introduction
### This project entails the acquisition, analysis, and application of a vast amount of Major League Baseball (MLB) data. Drawing inspiration from a rich history of sports analytics, including DeepBall and sabermetrics-style statistical analysis, learning player trends and playstyles for prediction is the goal. The motivation for this project lies in the inherent complexity and intrigue of baseball's statistical universe, coupled with the ambition to make increasingly accurate predictions about game outcomes.

### The main objective is to train a machine learning model capable of predicting the performance of batters within a given game. As a proof of concept for this demo of my project, I zeroed in on one particular aspect of a batter's performance: whether or not a batter will hit a home run in a given game.

### Tools and Technologies include:
#### • TensorFlow and Keras: The bedrock of my machine learning efforts, allowing me to experiment with different architectures and optimization strategies.
#### • NumPy and Pandas: For heavy lifting of data wrangling and pre-processing my acquired data. Pandas was great for data cleaning, transforming, and prepping. NumPy was invaluable, as most of my MLB stats data was numerical measures.
#### • Scikit-Learn: Helpful for checking my model evaluation metrics and tuning the hyperparameters. GridSearchCV and RandomizedSearchCV are also handy for tuning and identifying the most optimal model parameters.
#### •Seaborn: Great for plotting appealing graphs, and particularly useful for visualizing data trends to both a technical and non-technical audience. 


## Section 1: Data Acquisition
### Data Sources:
#### • Savant Statcast: MLB's state-of-the-art tracking technology. It can measure player and ball movements at high speeds and provide a huge range of data points, including pitch speed, release point, spin rate, exit velocity(speed of the ball off the bat), launch angle, and more!
#### • Baseball Reference: A comprehensive source of player, team, and league statistics and common statistics/averages.
#### • Baseball Databank: An open-source project that contains historical baseball data. The data covers a wide range of statistics from player performance to team history and game logs. Most beneficial from this data would be player biometric data to deepen understanding.

### Repository Overview:
#### • batter_preparing: Data cleaning for my batters data
#### • defense_preparing: Starting zone for cleaning my catchers/defense data (which is more signifigant for my upcoming developments)
#### • pitcher_preparing: Data cleaning for my pitchers data
#### • pitcher_modeling1: Initial ML model testing on my pitcher data, to gauge how this high-dimensional data would process
#### • pitcher_modeling2: Secondary training on my pitcher data, with more tuning and defined subsets to maintain context in my relating features
#### • prep_merging 1 and 2: This is where I ran code to recieve and sort my raw data, as well as merge the relevant positions into new dataframes, and further prepare some prepared dataframes for adding context to my high level multi-input RNN
#### • testing_API and ydata: test notebooks where I ran external kernels and addons, mostly ydata profiling for my dataframes.
#### • home_run_modeling: This file contains my final model for homerun predictions, as well as some resulting metrics.


## Section 2: Data Processing

### Dealing with Missing Data: The data I have was on a pitch-by-pitch basis, so some results for batter hits would be Null values if a batter didn't hit the ball then. These values were replaced with 0, and a few Null values along the rest of the dataframe.

### Outliers: A ton of the pitching metrics were wild and had low-occuring extreme outliers. I dropped roughly 2%-3% of the extreme highs and lows of each numerical column, to give my ML model a more default view of player styles, without some accidents.

### Feature Engineering: I created a swarm of new features to help my model, including player age and season total, some telling batting and pitching averages, numerical measures of batters hit strength(because most of the Statcast batting metrics began in 2018), and for the purpose of this project demonstration, homerun hit on a pitch, and a yes or no for a batter hitting a homerun per 1 baseball game(calculated with the game date)


## Section 3: Modeling
Model Selection:


Model Overview: Explanation of why a multi-input Recurrent Neural Network (RNN) was selected.

Architectural Design: Description of the network architecture, including the number of layers, types of layers, and any activation or loss functions used.

Training the Model:

Training Process: Description of how the model was trained, including the use of any optimization techniques.

Hyperparameter Tuning: Overview of the process for tuning the model's hyperparameters.

Model Evaluation:

Evaluation Metrics: Explanation of which metrics were used to evaluate the model's performance.

Validation Process: Detailed account of how the model's performance was validated.

Test Results: Results of the model's performance on the test data.


### Section 4: Future Work

Next Steps: Description of any additional features or improvements planned for future versions of the project.

Challenges and Learnings: Discuss any challenges faced during the project and what was learned from them.


### Section 5: Conclusion

Summary: Brief summary of the project's accomplishments and the potential impact of this work.

Acknowledgements: Acknowledge any contributions from team members or other sources.

Appendices

Appendix A: Code Repository: Link to the Git repository containing the code.

Appendix B: References: List of any references or resources used during the project.
