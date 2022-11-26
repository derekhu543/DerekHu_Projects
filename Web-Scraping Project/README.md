# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3: Web Scraping & Classification

### Description

This project helps you practice webscraping, NLP, and classification models.

### Scenario

You're fresh out of your Data Science bootcamp and looking to break through in the world of freelance data journalism. Nate Silver and co. at FiveThirtyEight have agreed to hear your pitch for a story in two weeks!

Your piece is going to be on how to create a Reddit post that will get the most engagement from Reddit users. Because this is FiveThirtyEight, you're going to have to get data and analyze it in order to make a compelling narrative.

#### Project Summary

I will collect data by scraping a website using praw (ran out of time for selenium) and build a binary predictor
using logsitic regression and random forest trees, both binary classification models.

**Problem Statement**
The goal of this project is to collect at least 10000 posts from the "all" section of reddit.
The "comments" variable is divided where all comments above the median is valued at "1"
while all comments below the median is valued at "0". Success is evaluated based on confusion
matrix and accuracy score of (X_train, X_test) and (y_train, y_test). I used random forest trees 
and logistic regression. I felt that logistic regression is the most interpretable and straightfoward
for audiences with less experience in modeling.

This project is meant for influencers/reddit posters to identift key words that would be
useful in order to maximize the total number of comments they can get in a post. It is also
an interesting study to show how certain words can attraction more attention than others.

My data is aquired through scraping threads from [Reddit] using the "all" homepage.

I've acquired several pieces of information about each thread. They were mostly used to make visualizations
as I only used "title" for my binary classifications.
1. The title of the thread
2. The subreddit that the thread corresponds to
3. The length of time it has been up on Reddit
4. The number of comments on the thread
5. The total score on the thread

I scraped roughly 13000 threads.

Once I got the data, I built classification models using text as X and the number of comments as y. My model predicts whether or not a given Reddit post will have above or below the median number of comments given the title contents.

I cleaned missing data values and analyzed overall distribution. Through visualizations and summary statistics, in terms of post score and comments, it is extreamely skewed with an extreamely high comment number and score for a tiny percentage of the total posts. Most comments and posts are below a few hundred. I decided to delete the top 1% of comments because of the massive outliers and they generally don't reflect reality.

For data cleaning, I deleted missing spaces, puntuations, and all numerical values. I also used lemmatization and
stop words which slightly increaed by test score accuracy. 

I trained and split by dataset with the countvectorized 'title' column as X and the number of comments as y.
Overal, the logistic regression with the tdif had the highest test accuracy score and decently good train accuracy score. I also looked at the coefficients of the model to see which ones had a positive effect on comments and
which had a negative effect. Lastly, I made confusion matrixes to find the number of TP, TN, FP, and FN. 

Based on my experience with Reddit, my conclusion largely matched with my expectations.
For coefficients that increased the number of comments
-There are a decent number of India related subs.
-ama is a popular subreddit where people can be interviewed on their jobs and experiences.
Each post on that thread starts with 'iama' explaining why it's so popular.
-Politics is highly popular, especially the r/politics subreddit. The subreddit is generally
more left leaning which is why 'trump' often has high comments and 'democrat' has lower comments.
The posts with 'Democrat' often discuss the party in more negative terms causing lower attention.
-There are a lot of mental health awareness threads and areas to help those with depression. It
also means that posts with 'suicide' threads where people talk about problems with depression
is fairly common.
-There are plently of reaction subs such as 'livestreamfail' and 'publicfreakout' as well as twitch
and other online platforms that are popular and drive attention
-Opinion posts - either unpopular or popular opinions are commonly found
-Maybe 'smell' comes from talk of covid problems - loss of taste and smell
-'Amazon' - lots of attention from union strikes of people buying from Amazon, or business related issues
-Less to learn from unpopular phrases, often words that don't draw much attention such as 'of', 'aka', 'im'
-People dislike reading bot accounts

### The Data Science Process

**Problem Statement**
- Is it clear what the goal of the project is?
- What type of model will be developed?
- How will success be evaluated?
- Is the scope of the project appropriate?
- Is it clear who cares about this or why this is important to investigate?
- Does the student consider the audience and the primary and secondary stakeholders?

**Data Collection**
- Was enough data gathered to generate a significant result (at least 10,000 posts)?
- Was data collected that was useful and relevant to the project?
- Was data collection and storage optimized through custom functions, pipelines, and/or automation?
- Was thought given to the server receiving the requests such as considering number of requests per second?

**Data Cleaning and EDA**
- Are missing values imputed/handled appropriately?
- Are distributions examined and described?
- Are outliers identified and addressed?
- Are appropriate summary statistics provided?
- Are steps taken during data cleaning and EDA framed appropriately?
- Does the student address whether or not they are likely to be able to answer their problem statement with the provided data given what they've discovered during EDA?

**Preprocessing and Modeling**
- Is text data successfully converted to a matrix representation?
- Are methods such as stop words, stemming, and lemmatization explored?
- Does the student properly split and/or sample the data for validation/training purposes?
- Does the student test and evaluate a variety of models to identify a production algorithm (**AT MINIMUM:** two models)?
- Does the student defend their choice of production model relevant to the data at hand and the problem?
- Does the student explain how the model works and evaluate its performance successes/downfalls?

**Evaluation and Conceptual Understanding**
- Does the student accurately identify and explain the baseline score?
- Does the student select and use metrics relevant to the problem objective?
- Does the student interpret the results of their model for purposes of inference?
- Is domain knowledge demonstrated when interpreting results?
- Does the student provide appropriate interpretation with regards to descriptive and inferential statistics?

**Conclusion and Recommendations**
- Does the student provide appropriate context to connect individual steps back to the overall project?
- Is it clear how the final recommendations were reached?
- Are the conclusions/recommendations clearly stated?
- Does the conclusion answer the original problem statement?
- Does the student address how findings of this research can be applied for the benefit of stakeholders?
- Are future steps to move the project forward identified?


### Organization and Professionalism

**Project Organization**
- Are modules imported correctly (using appropriate aliases)?
- Are data imported/saved using relative paths?
- Does the README provide a good executive summary of the project?
- Is markdown formatting used appropriately to structure notebooks?
- Are there an appropriate amount of comments to support the code?
- Are files & directories organized correctly?
- Are there unnecessary files included?
- Do files and directories have well-structured, appropriate, consistent names?

**Visualizations**
- Are sufficient visualizations provided?
- Do plots accurately demonstrate valid relationships?
- Are plots labeled properly?
- Are plots interpreted appropriately?
- Are plots formatted and scaled appropriately for inclusion in a notebook-based technical report?

**Python Syntax and Control Flow**
- Is care taken to write human readable code?
- Is the code syntactically correct (no runtime errors)?
- Does the code generate desired results (logically correct)?
- Does the code follows general best practices and style guidelines?
- Are Pandas functions used appropriately?
- Are `sklearn` and `NLTK` methods used appropriately?

**Presentation**
- Is the problem statement clearly presented?
- Does a strong narrative run through the presentation building toward a final conclusion?
- Are the conclusions/recommendations clearly stated?
- Is the level of technicality appropriate for the intended audience?
- Is the student substantially over or under time?
- Does the student appropriately pace their presentation?
- Does the student deliver their message with clarity and volume?
- Are appropriate visualizations generated for the intended audience?
- Are visualizations necessary and useful for supporting conclusions/explaining findings?


-----

## Why did we choose this project for you?

This project covers three of the biggest concepts we cover in the class: Classification Modeling, Natural Language Processing and Data Wrangling/Acquisition.

**Part 1** of the project focuses on **Data wrangling/gathering/acquisition**. This is a very important skill as not all the data you will need will be in clean CSVs or a single table in SQL. There is a good chance that wherever you land you will have to gather some data from some unstructured/semi-structured sources; when possible, requesting information from an API, but often scraping it because they don't have an API (or it's terribly documented).

**Part 2** of the project focuses on **Natural Language Processing** and converting standard text data (like Titles and Comments) into a format that allows us to analyze it and use it in modeling.

**Part 3** of the project focuses on **Classification Modeling**. Given that project 2 was a regression focused problem, we needed to give you a classification focused problem to practice the various models, means of assessment and preprocessing associated with classification.
