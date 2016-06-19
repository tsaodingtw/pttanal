# Introduction
This project uses scikit Bayesian algorithms to determine if a particular PTT article is politics-related.

We first use the Python Jieba library to separate Chinese words (斷詞) , and extract words as ***features*** for Bayesian algorithm. (Each word is a feature.)

Basically, with Bayesian algorithm, we can know that if a feature likely indicates the entire article (which contains a lot of features) is politics-related. For instance, a article containing the word "民進黨" is somewhat likely to be politics-related, even further, if the article also contains words like  "行政院", "立法院", "立委", "法條", it becomes highly likely that the article is politics-related.

We can know the degree of indication of each feature by extracting features and counting them in the training set. In the training set, there are lots of articles already labelled as politics-related or non politics-related. For example, in all politics-related articles in the training set, 90% of them contains "民進黨", then we know that "民進黨" is probably a political word, which means if an un-labelled article contains "民進黨", the article is likely to be politics related. But for words like "你們", it is likely that all articles, whether political or not, have about the same probablity of containing the word "你們", so it is a neutral word, we cannot infer from the word that if the article containing it is political.

# Demo
http://pttrend.nctu.me:3000/
