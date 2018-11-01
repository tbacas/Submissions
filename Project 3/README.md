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
