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

I did, however, do my t-tests, and found that:

| Conclusion | p-value|
| :------ |:--- |
|Men do better in author average rating than women for all genres combined|0.0004366582094875568| 
|Men do better in author rating count than women for all genres combined|5.4896001041356025e-05| 
|Men do better in book average rating than women for all genres combined|3.1790828751819067e-06|
|Men do better in number of book ratings than women for all genres combined|1.4028101661091678e-11|

##### Now looking at individual genres

Here I need to put a note that it matters how you bin data. In particular, the dataset has a "genre_1" and a "genre_2" which seem to basically be main catagory genres and subgenres respectively. First, I just looped through each combinition of genre_1 and genre_2, and found that in each genre combinitaion for which there were actually instances of both male and female authors, men won out on all counts. I was shocked by these findings, as some of those subgenres included "feminism". And it seems intuitive that sexism bias in opinions of writers and publicity writers get would be less impactful for women who write within a genre involving feminsim... but alas... Sexism impacts all aspects of society. But I was very relieved that when I binned the data differrently, and took all instances where genre 1 or 2 contained "feminism" or "Feminism" showed that women who wrote with feminism in some way impacting the genre were actually better off than men in these metrics. 

###### Allow me to summarize my findings with some plots and some charts.

##### Fantasy
![fantasy]/img/Fantasy(1).png{: .center-block :}
Above, purple dots are furthest from other dots while yellow dots are closest to other dots. 
Then we can look at the breakdown between men and women. 
![fantasymen]/img/Fantasymen.png{: .center-block :}
![fantasywomen]/img/Fantasywomen.png{: .center-block :}

Using frequency t tests, I found with a 95% confidence level that:

| Conclusion | p-value|
| :------ |:--- |
|Men do better in author average rating than women in fantasy|0.0002765396339034226| 
|Within Fantasy, author rating count does not show a statistically significant difference along gender lines|N/A| 
|Men do better in book average rating than women in fantasy|0.033266842347338774|
|Men do better in number of book ratings than women in fantasy|1.853099916310632e-05|
