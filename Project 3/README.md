# Project 3: Web APIs & Classification
Description
In week four we've learned about a few different classifiers. In week five we'll learn about webscraping, APIs, and Natural Language Processing (NLP). Now we're going to put those skills to the test.

For project 3, your goal is two-fold:

Using Reddit's API, you'll collect posts from two subreddits of your choosing.
You'll then use NLP to train a classifier on which subreddit a given post came from. This is a binary classification problem.
About the API
Reddit's API is fairly straightforward. For example, if I want the posts from /r/boardgames, all I have to do is add .json to the end of the url: https://www.reddit.com/r/boardgames.json

To help you get started, we have a primer video on how to use Reddit's API: https://www.youtube.com/watch?v=5Y3ZE26Ciuk

Requirements
Scrape and prepare your data using the requests library.
Create and compare two models. One of these must be a random forest, however the other can be a classifier of your choosing: logistic regression, KNN, SVM, etc.
A Jupyter Notebook with your analysis for a peer audience of data scientists.
An executive summary of the results you found.
A short presentation outlining your process and findings for a semi-technical audience.


Pro Tip 1: You can find a good example executive summary here.

Pro Tip 2: Reddit will give you 25 posts per request. To get enough data, you'll need to hit Reddit's API repeatedly (most likely in a for loop). Be sure to use the time.sleep() function at the end of your loop to allow for a break in between requests. THIS IS CRUCIAL

Pro tip 3: The API will cap you at 1,000 posts for each subreddit (assuming the subreddit has that many posts).

Pro tip 4: At the end of each loop, be sure to save the results from your scrape as a csv: JSON from Reddit > Pandas DataFrame > CSV. That way, if something goes wrong in your loop, you won't lose all your data.

## The Problem
Reddit, the open forum of the internet.  Where individuals post their beliefs and ideas.  Many people including myself see the an internet forum like reddit the true place for people's opinions, where no one speaker is hindered by threat of personal attack. 
A place like reddit is home to endless amounts of information, with the proper tools and ingenuity you can draw valuable information from the open forum.

## Tools and Code
The primary method for retrieving the post information was querying the reddit API.  By utilizing for loops and one can quickly return 25k+ post including the comments, title, post contents, users and more. These posts were collected into a pandas DataFrame for easy evaluation and exploration.

After doing this, each post was countervectorized a process called tokenizing is used to break sentences into individual words (or characters in some cases) so the computer can evaluate their importance to classification.  Without this step, the computer would not be able to properly run the functions below.

Once our important words were selected from each post they were used as features for our Random Forest Regressor, an aggregated decision tree model which develops branches based on information gain from each stage.  With this information the model is able to predict the subreddit origin with 93% accuracy (r2 Score).  

The developed model has the capability to return which words are most important for the classification process.  In the example of this project - 'Risk' was the determining word with almost 75% importance.  That is not surprising coming from r/Finance where much of the regular discussion is about financial risks.

## What Next
The next stages of this project would be to utilize similar techniques as above to determine trends within posts.  Which posts return the most karma, have the most comments, which titles attract the most attention, etc.  These processes are currently in development and will be using similar code as above. 
