# Airbnb-Reviews-Text-Mining-and-Sentiment-Analysis, 2018-2022

## TABLE OF CONTENTS

* [Introduction](#introduction)
* [Objective](#objective)
* [Language and Packages](#language-and-packages)
* [Data Source](#data-source)
* [Data Processing](#data-processing)
* [Data Visualization](#data-visualization)
* [Conclusions](#conclusions)

## Introduction

[Airbnb](https://en.wikipedia.org/wiki/Airbnb) is a global online marketplace for arranging or offering lodging and experiences, it has grown to become one of the largest online marketplaces for lodging in the world, while New York City (NYC) is one of the most popular cities on Airbnb, which means the competition is also brutal. Therefore, it's vital to understand what users like and dislike and make improvements to enhance the overall customer experience.

## Objective
Conducting text mining and sentiment analysis on 2018-2022 NYC Airbnb reviews to find out what users care about most and why they leave negative reviews.

## Language and Packages

- Language: R
- Packages
    - Data processing: tidyverse, lubridate, cld2
    - Data visualization: ggplot2, ggraph, gridExtra, tidygraph
    - Text mining: tidytext, quanteda
    - Sentiment analysis: lexicon_afinn, udpipe
- Environment: Jupyter Notebook

## Data Source

Reviews data `reviews.csv.gz` can be downloaded from [here](http://insideairbnb.com/get-the-data/),  in the section of New York City, New York, United States.

## Data Processing
- Data filtering: filter data by date (2018-01-01 to 2022-11-30 only) and language (English only)
- Data cleaning
    - remove missing values (close to 0%), html tags (e.g.: <br/>), duplicates, unnecessary columns; 
    - modify column names and data types

The final data dimension is 743K+ records.


## Data Visualization

Number of reviews over time:
<p align="center">
  <img alt="reviews over time" src="images/reviews-trend.png" width="46%">
</p>
During COVID 19 lockdown, the number of reviews dropped rapidly. But in general, the number of reviews increases year by year, but fluctuates seasonally (decreases in winter).

Most common words and trends:
<p align="center">
  <img alt="Common words" src="images/words.png" width="46%">
</p>
<p align="center">
  <img alt="Trends of words" src="images/word-trend.png" width="46%">
</p>
Among the top 6 most common words, the popularity of "stay", "location", "clean" is slowly increasing, while the others are decreasing.

Most common bigrams and trigrams:
<p align="center">
  <img alt="Bigrams" src="images/bigrams.png" width="46%">
</p>
<p align="center">
  <img alt="Trigrams" src="images/trigrams.png" width="46%">
</p>
Both bigrams and trigrams are heavily related to **minute walk**.

Starting and ending points of "minute walk":
<p align="center">
  <img alt="from walk" src="images/from-walk.png" width="46%">
</p>
<p align="center">
  <img alt="to walk" src="images/to-walk.png" width="46%">
</p>

Words linked to negative terms:
<p align="center">
  <img alt="Negative links" src="images/negative-link.png" width="46%">
</p>

Emotions and trends:
<p align="center">
  <img alt="emotions" src="images/emotions.png" width="46%">
</p>
<p align="center">
  <img alt="sentiments" src="images/sentiments.png" width="46%">
</p>
<p align="center">
  <img alt="sentiment-trend" src="images/sentiment-trend.png" width="46%">
</p>


## Conclusions

- The **location** of the listing is very important to guests, they care about the **walking distance** to **subway station**, and most often mentioned **5 minute walk** or **10 minute walk**.
- Reviews are more **positive** (88.9%) than negative (11.1%), the strongest emotions of reviews are **Trust** and **Joy**, which accounted for 61% of all emotions.
- Negative reviews are strongly associated with limited space, where **small room** leads to most negative reviews, followed by **small place** and **small apartment**. Besides, hosts also need to take care of issues such as hot water and natural light.
