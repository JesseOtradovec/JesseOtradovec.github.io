---
layout: post
title: Data StoryTelling Project!
subtitle: Goodreads Data
image: /img/Fiction (1).png
---

## GoodReads Data

### Abstract

For my Data Storytelling project, I looked at this dataset from GoodReads of some top books. https://www.kaggle.com/brosen255/goodreads-books I then compared number of book reviews, number of author reviews, author average review, and book average review to get a sense of if male or female authors were more or less popular in a statistically significant way for a given genre. I found that while men won out on all metrics in the overall data and in many individual genres, women won out in some metrics for feminism and romance catagories. In Magical Realism (my personal favorite genre), there was no statistically significant difference in these metrics between the sexes. However, Magical Realism is a very small subgenre. 

### Methodology

#### First Comparing Across All Genres

I loaded in the dataset and dropped duplicate books from the data. I only kept the columns I was interested in. During my exploratory phase with the data, I plotted histograms of the book average rating and author average rating, comparing the histogram of men with that of women. I noticed there was some difference in the mean, but couldn't tell without doing a t test if this difference was statistically significant. 

##### Below is a histogram of the author's average rating, broken up by gender:

![author](/img/AuthorAveTotalHistograms.png){: .center-block :}

##### And here is the book's average ratings broken up by author gender:

![book](/img/BookTotalAve.png){: .center-block :}

##### T Tests to determine statistical significance:

Then I did t tests where I looped through each combination of genre and subgenre (listed in the dataset as genre1 and genre2) to find in what genres women were doing better than men by these metrics. When I did that, I only found that men were doing better than women. I didn't like those results, and I didn't trust them exactly, so I changed how I binned the data to further my exploration.

In these tests, I asked it to sort all rows in the dataframe where genre1 _or_ genre 2 contained the genre keyword in either lowercase or uppercase.

##### When I did these t tests, I found that:

| Conclusion | p-value|
| :------ |:--- |
|Men do better in author average rating than women for all genres combined|0.0004366582094875568| 
|Men do better in author rating count than women for all genres combined|5.4896001041356025e-05| 
|Men do better in book average rating than women for all genres combined|3.1790828751819067e-06|
|Men do better in number of book ratings than women for all genres combined|1.4028101661091678e-11|

#### Now looking at individual genres

Here I need to put a note that it matters how you bin data. In particular, the dataset has a "genre_1" and a "genre_2" which seem to basically be main catagory genres and subgenres respectively. First, I just looped through each combinition of genre_1 and genre_2, and found that in each genre combinitaion for which there were actually instances of both male and female authors, men won out on all counts. I was shocked by these findings, as some of those subgenres included "feminism". And it seems intuitive that sexism bias in opinions of writers and publicity writers get would be less impactful for women who write within a genre involving feminsim... but alas... Sexism impacts all aspects of society. But I was very relieved that when I binned the data differrently, and took all instances where genre 1 or 2 contained "feminism" or "Feminism" showed that women who wrote with feminism in some way impacting the genre were actually better off than men in these metrics. 

##### Allow me to summarize my findings with some plots and some charts.

##### Fantasy
![fantasy](/img/Fantasy (1).png){: .center-block :}

Above, purple dots are furthest from other dots while yellow dots are closest to other dots. 
Then we can look at the breakdown between men and women.

![fantasymen](/img/Fantasymen.png){: .center-block :}

![fantasywomen](/img/Fantasywomen.png){: .center-block :}

Using frequency t tests, I found with a 95% confidence level that:

| Conclusion | p-value|
| :------ |:--- |
|Men do better in author average rating than women in Fantasy|0.0002765396339034226| 
|Within Fantasy, author rating count does not show a statistically significant difference along gender lines|N/A| 
|Men do better in book average rating than women in Fantasy|0.033266842347338774|
|Men do better in number of book ratings than women in Fantasy|1.853099916310632e-05|

##### Romance
![romance](/img/Romance (1).png){: .center-block :}

![romancemen](/img/Romancemen.png){: .center-block :}

![romancewomen](/img/Romancewomen.png){: .center-block :}

Using frequency t tests, I found with a 95% confidence level that:

| Conclusion | p-value|
| :------ |:--- |
|Women do better in author average rating than men in Romance|0.0025460544341681266| 
|Within Romance, author rating count does not show a statistically significant difference along gender lines|N/A| 
|Women do better in book average rating than men in Romance|0.002647443921313459|
|Men do better in number of book ratings than women in Romance|0.0013340408057532756|

##### Fiction
![fiction](/img/Fiction (1).png){: .center-block :}

![fictionmen](/img/Fictionmen.png){: .center-block :}

![fictionwomen](/img/Fictionwomen.png){: .center-block :}

Using frequency t tests, I found with a 95% confidence level that:

| Conclusion | p-value|
| :------ |:--- |
|Men do better in author average rating than women in Fiction|3.250456456048012e-05| 
|Within Fiction, men do better than women in author rating count|0.002667064042173123| 
|Men do better in book average rating than women in Fiction|1.5116661033089678e-06|
|There is suprisingly gender equity in number of book ratings in Fiction|N/A|

##### Feminism

|Conclusion| p-value|
| :------ |:--- |
|There is gender equity in author average rating, book average rating, and number of ratings.| N/A|
|Women do better in author rating count than men in all feminism catagories|0.005051166802266278|
| | |

#### Limitations of the data
It is worth noting that we don't know the author's true gender, which is a non-binary value. We just know the apparent gender of the author's pen name. It is well known that it is common for women in most genres to use men's names as pennames when trying to avoid sexism, and it is also common in romance genres for men to use women's pen names. So. *shrug* There's also the interesting question of how various books in various genres are rated and if people are rating within their own or outside thier own genre of interest. 

#### Takeaway

My personal takeaway from this? I sort of had to massage the data to find allocations where women were doing better than men by these metrics. Sexism is alive and well in how we consume books. It is a problem. Read women's books. Review them. Just do it. There's my takeaway. 

Here is my google colab where I did all these tests, for reproducability:
https://colab.research.google.com/drive/1M8NnFTKFHW0dViCzmQIaR1GV4ZCs7PnE
