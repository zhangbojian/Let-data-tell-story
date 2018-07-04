# Let-data-tell-story
CyberSecurityNLP competition

Introduction

Cyber security is an essential issue for the overall security of a country. Cybersecurity is not only about technology, but also about laws and strategies. However, analyzing cybersecurity strategy documents is difficult because it requires knowledge of multiple domains.
With the help of text analytics methods, the documents can be understood more easily, automatically, and efficiently. 
This project conducts machine-learning based text analytics of national cybersecurity strategies. 
The research objects are the cyber security strategies files of 76 countries in the world. 

Problem Statement

Build a tool to analyze the text data of Cybersecurity strategies of different countries to generalize their topics, classify each sentence and assign it with a tag of category.

Data Description

80 pdf documents about Cybersecurity strategic of different countries, given by Unite Ideas in the United Nation’s website.
193 pdf documents of Cyberwellness profiles, downloaded from International Telecommunications Union.
Source Link:  https://www.itu.int/en/ITU-D/Cybersecurity/Pages/Country_Profiles.aspx

Methodology

As the amateurs of Cyber Security, this project uses the methodology on the right pane to detect the hidden values and insights behind the raw text data. That is let the text data tell a story. 

![image](https://github.com/zhangbojian/Let-data-tell-story/blob/master/Picture1.jpg)

Sentence Tokenization
Before sentence tokenization, the tedious text data is removed, including “contents”, “appendix”, table titles, figure titles etc. 
Sentence recognition rules are built. For example, it is regulated that the sentences beginning with numbers, ending with “.”,“;”, and character number less than 50 or the specific value depending on the situation can be regarded as one sentence. 
After the meticulous process, there are 4980 sentences with full and clear meanings are selected. 

Semi-supervised machine learning model
The external text data could not promote the classification process very well.
In order to fully utilize the internal resources, the International Telecommunications Union profiles are adopted to extract the initial dictionary. 
Semi-supervised machine learning algorithm can benefit the text mining procedure by multi-times learning and optimization. 
There are two rules should be satisfied together for the sentence classification according to the probabilities generated by the model:
     (1) Probabilities must larger than 0.5
     (2) Probabilities must larger than 99 percentile

Initial Dictionary

![image](https://github.com/zhangbojian/Let-data-tell-story/blob/master/Picture8.jpg)


Selected Features
The word cloud on the right shows the 65 independent variables put in the semi-supervising machine learning model. 

![image](https://github.com/zhangbojian/Let-data-tell-story/blob/master/Picture9.jpg)

Model Evaluation
Here we create 10 classifier chains. Each classifier chain contains a logistic regression model for each of the 21 labels. The models in each chain are ordered randomly.
We apply Jaccard Similarity Score to evaluate our model.
Score of ensemble model is around 40%, for a multi-label text data classification issue with more than 20 labels, it is an acceptable result.

![image](https://github.com/zhangbojian/Let-data-tell-story/blob/master/Picture2.jpg)

Sample Results

![image](https://github.com/zhangbojian/Let-data-tell-story/blob/master/Picture3.jpg)

Overall Label Results 

There are more than 1000 sentences are labeled from semi-supervised model. In the right bubble chart, the size of the bubbles is the number of the sentences belonging to this category. 
“Standards”, “Regulation and compliance”, “Public sector partnership”, “Intra-state cooperation”, and “Responsible agency” are the top five essential categories. 

![image](https://github.com/zhangbojian/Let-data-tell-story/blob/master/Picture4.jpg)

Label Results Comparison 

In the right bar chart, “0” represents the developing countries and “1” represents the developed country. The value of the bar means the importance of the category.
Comparing to developed countries, developing countries mainly focus on improving the completeness  of standards of Cyber Security requirements. 
Developed countries attach more importance to the supervision upon certification of agencies and the beneficial corporation between states. 

![image](https://github.com/zhangbojian/Let-data-tell-story/blob/master/Picture5.jpg)

“Standard” Category Analysis Based on Countries

In the map on the right pane, the color depth means the number of the sentences belonging to standards. The more deeper the color is, the more important “standard” in this country’s cyber security strategy will be.
US, China, Saudi Arabia, Denmark, and Sweden are applied with darker color. They have advanced and mature cyber security strategies and may set up the standards in the surrounding area. 

![image](https://github.com/zhangbojian/Let-data-tell-story/blob/master/Picture6.jpg)

Topic Modeling Results Comparison
“Defend” is the most important topic in developed country, which may indicate the developed countries are attacked in a high frequency. 
The topic difference in different continents are vague, which can show the cyber security issues happen almost evenly in each continent.

![image](https://github.com/zhangbojian/Let-data-tell-story/blob/master/Picture7.jpg)

Conclusions

This project well produces a sentence classifier machine for the raw text data classification and tagging process without enough professional terminology dictionary. 
“Standard” is the most important category in the labeling process.
The topic modeling results vary a lot in country’s development level but perform similarly in the continental dimension. 

Future Research

1.Sentence Tokenize
Improve the performance of tokenizer through recognizing the complete sentence structure and entities extraction. 
2.Word directory
Through more documents on cybersecurity, we may improve the performance of word directory for classification to make it more precise and complete.
3.Rules optimization
Generate specific contents on rules for each sentence and comparing the cyber security document of each country to the UN cyber security requirements to check its completeness.









