# Udacity_Pyspark_Capstone_Project

# 1. Business Understanding
When users use the APP, they will leave a lot of behavioral data, such as the interface they have logged in, the songs they have listened to, the songs they like, the songs they hate, and so on.We can find the characteristics of lost users from these behavioral data, analyze the reasons for their loss, and then try to improve the retention rate of users.
# Sparkify Project Workspace
This workspace contains a tiny subset (128MB) of the full dataset available (12GB). Feel free to use this workspace to build your project, or to explore a smaller subset with Spark before deploying your cluster on the cloud. Instructions for setting up your Spark cluster is included in the last lesson of the Extracurricular Spark Course content.

You can follow the steps below to guide your data analysis and model building portion of this project.

# 2. Data Understanding
# Load and Clean Dataset
Clean your dataset, checking for invalid or missing data. For example, records without userids or sessionids. In this workspace, the filename is `mini_sparkify_event_data.json`.
# Exploratory Data Analysis
When you're working with the full dataset, perform EDA by loading a small subset of the data and doing basic manipulations within Spark. In this workspace, you are already provided a small subset of data you can explore.
## Define Churn

Once you've done some preliminary analysis, create a column `Churn` to use as the label for your model. I suggest using the `Cancellation Confirmation` events to define your churn, which happen for both paid and free users. As a bonus task, you can also look into the `Downgrade` events.

## Explore Data
Once you've defined churn, perform some exploratory data analysis to observe the behavior for users who stayed vs users who churned. You can start by exploring aggregates on these two groups of users, observing how much of a specific action they experienced per a certain time unit or number of songs played.<br>
we find paid level,use visit page,visit page proportion ,number of songs,number of session,average number of songs in each session,user lifetime can influence use's churned behavior.

# 3. Data Preparation
# Feature Engineering
Once you've familiarized yourself with the data, build out the features you find promising to train your model on. To work with the full dataset, you can follow the following steps.
- Write a script to extract the necessary features from the smaller subset of data
- Ensure that your script is scalable, using the best practices discussed in Lesson 3
- Try your script on the full data set, debugging your script if necessary

If you are working in the classroom workspace, you can just extract features based on the small subset of data contained here. Be sure to transfer over this work to the larger dataset when you work on your Spark cluster.

# 5. Modeling
Split the full dataset into train, test, and validation sets. Test out several of the machine learning methods you learned. Evaluate the accuracy of the various models, tuning parameters as necessary. Determine your winning model based on test accuracy and report results on the validation set. Since the churned users are a fairly small subset, I suggest using F1 score as the metric to optimize.

conclusion 
After the test above, we finally choose the random forest as the final model, with its accurcy = 0.75 and f1= 0.7.<p/>
The factors that have the greatest impact on user churn are: <p/>
lifetime,freq_Roll_advert,freq_Thumbs_Up,freq_Settings,freq_Downgrade,freq_Thumbs_Down,freq_NextSong,count_Add_Friend,Freq_Help,Freq_upgrade

# Final Steps
Clean up your code, adding comments and renaming variables to make the code easier to read and maintain. Refer to the Spark Project Overview page and Data Scientist Capstone Project Rubric to make sure you are including all components of the capstone project and meet all expectations. Remember, this includes thorough documentation in a README file in a Github repository, as well as a web app or blog post.

## Problems and Prospects
User behavior data is often very large and difficult to complete using traditional analysis methods, so it needs to be done through spark.Pyspark is a combination of the python language and spark that handles these issues well.Considering the problem of computing resources, only 248M of the total 12G data was used in this paper, with a total of 488 users.

**Problem 1**. Not all data are used, and the deviation of sampling may lead to the deviation of analysis conclusion.<br>
**Follow-up work**. Use full 12G data for analysis and mining.

**Problem 2**. Abnormal information haven't been clean.Our purpose is to analyze normal users, but there are some black users on the market who use fake mobile phones for illegal behavior, or other abnormal users.Their behaviors may affect our analysis and judgment,so should be eliminated.<br>
**Follow-up work**. Detected and delete abnormal data.

**Problem 3**. More feature engineering.We only carried out a simple feature work, but there are more features to explore, such as users often both thumb up and often thumb down, this type of users may be more fiery personality, so it is easier to some problems and loss.This type of feature can be further explored.<br>
**Follow-up work**. Explored more features.

