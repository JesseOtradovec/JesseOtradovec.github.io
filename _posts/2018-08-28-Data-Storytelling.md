---
layout: post
title: Data StoryTelling Project!
image: /img/AuthorAveTotalHistograms.png
---

### GoodReads Data

#### Abstract
For my Data Storytelling project, I looked at this dataset from GoodReads of some top books. https://www.kaggle.com/brosen255/goodreads-books I then compared number of book reviews, number of author reviews, author average review, and book average review to get a sense of if male or female authors were more or less popular in a statistically significant way for a given genre. I found that while men won out on all metrics in the overall data and in many individual genres, women won out in all metrics for feminism and romance catagories. In Magical Realism (my personal favorite genre), there was no statistically significant difference in these metrics between the sexes.
#### Methodology
##### First Comparing Across All Genres
I loaded in the dataset and dropped duplicate books from the data. I only kept the columns I was interested in. During my exploratory phase with the data, I plotted histograms of the book average rating and author average rating, comparing the histogram of men with that of women. I noticed there was some difference in the mean, but couldn't tell without doing a t test if this difference was statistically significant. 

![author](/img/AuthorAveTotalHistograms.png){: .center-block :}

![book](/img/BookTotalAve.png){: .center-block :}

Here's a useless table:

| Number | Next number | Previous number |
| :------ |:--- | :--- |
| Five | Six | Four |
| Ten | Eleven | Nine |
| Seven | Eight | Six |
| Two | Three | One |

I did, however, do my t-tests, and found that:

| Title | p-value|
| :------ |:--- |
|Men do better in author average rating than women for all genres combined|0.0004366582094875568| 
|Men do better in author rating count than women for all genres combined|5.4896001041356025e-05| 
|Men do better in book average rating than women for all genres combined|3.1790828751819067e-06|
|Men do better in number of book ratings than women for all genres combined|1.4028101661091678e-11|
