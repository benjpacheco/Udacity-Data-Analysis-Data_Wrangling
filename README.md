
<h1 align="center">WeRateDogs Twitter Data Wrangling</h1>


## Table of Contents
- [Installation](#installation)
- [Project Overview](#project_overview)
- [Project Details](#details)
  - [Gathering Data](#gather)
- [Project Motivation](#motivation)
- [Results](#results)



## Installation <a name="installation"></a>

You need to be able to work in a Jupyter Notebook on your computer. The following packages (libraries) need to be installed. You can install these packages via conda, pip, or by creating an environment from my environment.yml file.

- Tweepy
- Requests
- Pandas
- Matplotlib
- Seaborn
- conda env create -f environment.yml

## Project Overview <a name="project_overview"></a>

Real-world data rarely comes clean. Using Python and its libraries, I will gather data from a variety of sources and in a variety of formats, assess its quality and tidiness, then clean it. This is called data wrangling. I will document my wrangling efforts in a Jupyter Notebook, plus showcase them through analyses and visualizations using Python (and its libraries) and/or SQL.

The dataset that I will be wrangling (and analyzing and visualizing) is the tweet archive of Twitter user [@dog_rates](https://twitter.com/dog_rates), also known as [WeRateDogs](https://en.wikipedia.org/wiki/WeRateDogs). WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "[they're good dogs Brent](http://knowyourmeme.com/memes/theyre-good-dogs-brent)." WeRateDogs has over 4 million followers and has received international media coverage.

<p align="center">
  <img src="https://video.udacity-data.com/topher/2017/October/59dd378f_dog-rates-social/dog-rates-social.jpg" width = 500px; height =300px;\>
</p>

### Source of Data <a name="gather"></a>

I will gather each of the three pieces of data as described below in a Jupyter Notebook titled `wrangle_act.ipynb`:
<ol>
    <li>The WeRateDogs Twitter archive. `twitter_archive_enhanced.csv` </li> 

   <li>The tweet image predictions, i.e., what breed of dog (or other object, animal, etc.) is present in each tweet according to a neural network. This file (image_predictions.tsv) is hosted on Udacity's servers and should be downloaded programmatically using the <a href="https://pypi.org/project/requests/">Requests</a> library and the following URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv</li>

   <li>Each tweet's retweet count and favorite ("like"). Using the tweet IDs in the WeRateDogs Twitter archive, I will query the Twitter API for each tweet's JSON data using Python's <a href="http://www.tweepy.org/">Tweepy</a> library and store each tweet's entire set of JSON data in a file called <em>tweet_json.json file</em>. Each tweet's JSON data should be written to its own line. Then read this .txt file line by line into a pandas DataFrame with (at minimum) tweet ID, retweet count, and favorite count.</li>
</ol>


### Project Motivation <a name="motivation"></a>

I was interested in using Tweet Data to better understand: </br>

- What is the total number of tweets over time to see whether that number increases, or decreases, over time.
- What is the retweet counts, and favorite counts comparison over time.
- What is the most popular dog breed.
- What is the most popular dog names.

## Results <a name="results"></a>

- The most common dog names are Charlie and Oliver, followed by Lola, Cooper, and Lucy.
- The most common dog breeds predicted by the neural network were the Golden Retriever, Pembroke, and Labrador Retriever.
- Most favorited tweet was 'Here's a doggo realizing you can stand in a pool. 13/10 enlightened af (vid by Tina Conrad)' with a count of 146369 likes.


