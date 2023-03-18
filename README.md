# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project: A Chinese NLP Study based on Douban Movie Reviews
# 豆瓣电影评论文本分析

### Background

[Douban](https://www.douban.com/) is a popular movie review website in China, for its credibility and the insights from users. There are however increasingly more issues related to false reviews and "Water Army" nowadays.

### Problem Statement

The objective of the study is two-folds:

#### Proof of concept: 
    
- Is the analysis through NLP able to uncover the linguistic complexity and cultural nuances of Chinese?

#### Insights for potential applications:
    
- The use of Chinese NLP in the field of content review, and content recommendation systems etc. 

The project is approached with the following steps:

## Data Collection
It is noticed that Douben has implemented a guardrail to avoid people from craping more than 520 comments per each movie title. In order to get increase the data size for my study, I have selected two genres with 6 titles each. The genres selected are **Sci-fi Movies** and **Stephen Chow** Movies. Within each genre, the titles are as similar as possible. 

![douban](./img/douban.png)
For each of the titles, I searched it through the Douban homepage, clicked to view its reviews and got the review page URL. By inputting the target page URL into the craper code, I managed to get the first 520 comments for each movie and saved them into individual files in .csv format.

## Data Cleaning & EDA

![scattertext_genre](./img/scattertext_genre.png)
- It is essentially 3 parts we are looking at when reading a scattertext plot:
1. The axises representing two dimensions of the text data. In this case for instance, words are ploted based on genre and frequency;
2. The midline separating the two categories in the centre. This chart is cut in between based on the genre classfication, being "Sci-fi" or "Stephen Chow" movies.
3. The distance between any two words are measured based on the given dimensions. 

## Preprocessing & Modeling

![model_comparison](./img/model_comparison.png)
- Model A outperforms model B for most of the metrics with precision as an exception. 
- Precision is the fraction of true positive predictions (correctly predicted positive instances) among all predicted positive instances. In general, increasing the threshold for predicting a positive class will lead to higher precision but lower recall. This is because when we increase the threshold, we are making the model more conservative in predicting the positive class, which leads to fewer false positives, and hence higher precision.
- In some cases, in a fraud detection task, high precision may be more important to avoid falsely flagging any negative instances. But for the purpose of study, we are not specifically aiming for high precision and hence will pick Model A with a better performance in general.

## Prediction

Examples of misclassified comments:

![misclassified](./img/misclassified.png)
- The comment on the left is way to short for the model to classfy. 
- Whereas the one on the right is long enough, it comes with too many "big words" which are too new for the model to comprehend fully. 

## Conclusion & Recommendation

#### Conclusion:

**Proof of Concept:**

While NLP can certainly be used to analyze the linguistic complexity of Chinese, it is NOT effective in uncovering all of the cultural nuances of the language. This is because:

- Chinese is a tonal language, which means that a single word can have multiple meanings depending on the tone in which it is spoken.
- Cultural references to literature can also be challenging for NLP systems to comprehend.


#### Recommendation for Douban:

**The ratings and languages are very different for reviews of Sci-fi and Stephen Chow movies.**

- Douban may consider the use of NLP model for content review or content recommendation system given its capability in comprehending Chinese text data.
- However, it is important to consider the limitations of NLP and to supplement it with cultural context and human interpretation.

