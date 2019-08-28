---
layout: post
title: Data StoryTelling Project!
image: /img/AuthorAveTotalHistograms.png
---

### GoodReads Data

#### Abstract
For my Data Storytelling project, I looked at this dataset from GoodReads of some top books. https://www.kaggle.com/brosen255/goodreads-books I then compared number of book reviews, number of author reviews, author average review, and book average review to get a sense of if male or female authors were more or less popular in a statistically significant way for a given genre. I found that while men won out on all metrics in the overall data and in many individual genres, women won out in all metrics for feminism and romance catagories. In Magical Realism (my personal favorite genre), there was no statistically significant difference in these metrics between the sexes.
#### Methodology
I loaded in the dataset and dropped duplicate books from the data. I only kept the columns I was interested in. During my exploratory phase with the data, I plotted histograms of the book average rating and author average rating, comparing the histogram of men with that of women. I noticed there was some difference in the mean, but couldn't tell without doing a t test if this difference was statistically significant. 

![author](/img/AuthorAveTotalHistograms.png) 

![book](/img/BookTotalAve.png)

