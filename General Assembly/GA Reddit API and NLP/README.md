# Project 3: API and NLP with Dating and Relationship Advice

## Table of Contents
[1.0 Directory Structure](#1.0-Directory-Structure)<br>
[2.0 Data Science Problem](#2.0-Data-Science-Problem)<br>
[3.0 Description of Data](#3.0-Description-of-Data)<br>
-[3.1 Size](#3.1-Size)<br>
-[3.2 Source](#3.2-Source)<br>
-[3.3 Data Dictionary](#3.3-Data-Dictionary)<br>
[4.0 Data Visualization](#4.0-Data-Visualization)<br>
[5.0 Conclusion](#5.0-Conclusion)<br>
-[5.1 Next Steps](#5.1-Next-Steps)<br>
[6.0 Outside Sources](#6.0-Outside-Sources)<br>

## 1.0 Directory Structure

```
.
├── project_3
    ├── code
        ├── Project 3 API and NLP Subreddit.ipynb
    ├── datasets
        ├── rel.csv
        ├── dat.csv
        ├── rel_dat.csv
    ├── images
        ├── Top 10 Relationship Advice Words.png
        ├── Top 10 Dating Advice Words.png
        ├── Prediction Probabilities of Logistic Model.png
        ├── Prediction Probabitlities of Multinomial NB.png 
    ├── README.md
    ├── Requirements.txt
    ├── Relationship Advice and Dating Advice Classifier Proposal Executive Summary.docx
    └── Project 3.pdf
```

## 2.0 Data Science Problem

When is an advice considered to be relationship advice or dating advice?

---
## 3.0 Description of Data
There are three files:

rel.csv -- relationship_advice subreddit data grabbed through Push API.

dat.csv -- dating_advice subreddit data grabbed through Push API.

rel_dat.csv -- combination of relationship_advice and dating_advice subreddit with relationship_advice being equaled to 1 while dating_advice being equalted to 0.
    
### 3.1 Size

### 3.2 Source
[here](https://www.reddit.com/r/relationship_advice/)
[here](https://www.reddit.com/r/dating_advice/)

### 3.3 Data Dictionary
[here](https://github.com/pushshift/api)
---
## 4.0 Data Visualization

<img src="images/Top 10 Relationship Advice Words.png">
<img src="images/Top 10 Dating Advice Words.png">
<img src="images/Prediction Probabilities of Logistic Model.png">
<img src="images/Prediction Probabitlities of Multinomial NB.png">

---
## 5.0 Conclusion

-Logistic Regression gave the best score
-Regularization may be needed
-Lemmatizing/Stemming may increase accuracy score                                                                                   
                                                                                         
### 5.1 Next Steps

Improve my models through regularization and adding more stopwords. Also, more time to exploring the data would be helpful.                                                                     
                                                                                         
---
## 6.0 Outside Sources


