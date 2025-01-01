# Fake-News-Detection
# Exploratary Data Analysis
## **Research Question 1**
*Are there significant differences in the distribution of text lengths between Fake and True news?*

![image](https://github.com/user-attachments/assets/50e0ac73-99c2-4029-8a6b-0c0952a7eb58)
Most of the data is concentrated towards the left side of the graph, indicating that many fake news articles have shorter text lengths. So that is called positively skewed.

![image](https://github.com/user-attachments/assets/1d3cecb3-463f-4590-ad82-c9fcdbdc3e71)
Both plots show median lines within their respective boxes; However, it's clear that the median text length for fake news is shorter than that for true.

## **Research Question 2**
*Are there significant differences in the distribution of title lengths between Fake and True news?*

![image](https://github.com/user-attachments/assets/71b32363-f474-499a-901c-558911ae5232)
Fake news title lengths have a moderately positively skewed distribution with a moderate level of kurtosis, indicating that there are some longer titles that contribute to a more peaked shape. True news title lengths also exhibit a positively skewed distribution with positive kurtosis, but the skewness and kurtosis values are lower than those of fake news. This suggests that true news title lengths have a milder rightward skew and a less extreme peaked shape compared to fake news title lengths.

![image](https://github.com/user-attachments/assets/f14b537d-5888-468f-a764-de2f88ca0b9a)
The purple box plot (fake news) has a larger interquartile range compared to the green one (true news). Both plots have outliers, but the fake news dataset has more extreme outliers with title lengths reaching up towards 300. There’s no x-axis label, but it’s implied that it represents the two categories of news: fake and true.

## **Research Question 3**
*Is there any correlation btw title length and text lengths in different news types?*

![image](https://github.com/user-attachments/assets/b2073993-7ca9-4446-8326-35827164f656)
To create each representing the correlation between the length of titles and the length of text in the fake news and true news datasets. The code we provided calculates the Pearson Correlation Coefficient between the length of titles and the length of text for both fake and true news datasets.

## **Research Question 4**
*What is the temporal patterns of fake news over time?*

![image](https://github.com/user-attachments/assets/0205d7e0-a878-4316-862c-386894bfebd7)

##**Research Question 5**
*What is the subject distribution for news?*

![image](https://github.com/user-attachments/assets/f3acd741-0f2d-4080-890b-fe2e5cff25e2)
The dataset was combined after determining whether the subject should be included. The subject data was removed as it was deemed unnecessary. An evaluation was conducted to identify what works and what does not. Before the model was trained, the columns in the dataset were assessed for relevance, as the primary goal was to detect fake news, and the model was to be trained accordingly.

## **Research Quesiton 6**
*What are the most used words in true news?*

![image](https://github.com/user-attachments/assets/0aee15fb-f674-4b3b-b2e0-04c7a994f376)
The top word frequencies in news articles. According to plot, the most used word is "used" however, the least used word is "north".

# Data Cleaning
Analyzes made on the data sets, unnecessary information was cleared. Inconsistencies between subject headings have been resolved, date information has been removed, and the necessary preliminary processes have been completed to analyze features such as text lengths.

# Data Pre-Process
This section details the feature engineering steps used to feed the dataset into machine learning models.
Before training Machine Learning models, separated the last 1000 data of the dataset to later test the best performing model with new data.

# Model Selection
Supervised Learning involves training a model on a labeled dataset, where the algorithm learns from input-output pairs to make predictions or classifications on new, unseen data. The primary rationale behind model selection was to leverage the existing label information in dataset, leads to prefer classification and prediction models.
Trained various machine learning models, including Logistic Regression, Decision Tree Classifier, Random Forest Classifier, and Naive Bayes.

1) **Logistic Regression**: Logistic Regression is a statistical method that is based on a linear model to classify the dependent variable and is used especially for two-class problems.

  ![image](https://github.com/user-attachments/assets/89d5733f-d7f9-4c58-aaef-5e09debf903d)
  ![image](https://github.com/user-attachments/assets/937bd1ed-fa0e-46e7-8d31-ad94960fbb12)
  
  The ROC curve evaluates a model's performance by plotting the true positive rate (sensitivity) against the false positive rate, with 97.61% area under the curve (AUC) indicating better classification ability.

2) **Decision Tree Classifier**: Decision Tree Classifier is an algorithm that creates decision rules by dividing the data into branches and performs classification tasks in a visualizable way.
   
  ![image](https://github.com/user-attachments/assets/113db32e-0150-4ebc-810e-e698daf11c74)
  ![image](https://github.com/user-attachments/assets/a07111ad-57c5-478c-b408-e55efb429e10)

  The ROC curve suggests that the model's performance is worst than logistic regression by plotting the true positive rate (sensitivity) against the false positive rate, with 92.44% area under the curve (AUC).

3) **Random Forest Classifier**: Random Forest Classifier is an ensemble learning method created by combining multiple decision trees and aims to increase classification accuracy.
   
  ![image](https://github.com/user-attachments/assets/9299d5ca-3c41-4456-862f-4cdc99ee8b29)
  ![image](https://github.com/user-attachments/assets/214f1068-29ef-43af-bc51-044b6c73b8a6)
  
  The ROC curve suggests that the model's performance is worst than logistic regression by plotting the true positive rate (sensitivity) against the false positive rate, with 97.45% area under the curve (AUC).

4) **Naive Bayes**: Naive Bayes is a probabilistic classifier that assumes that events are independent of each other and provides fast and effective results, especially in tasks such as text classification.
  ![image](https://github.com/user-attachments/assets/43c38fe6-e4a8-42bc-b84d-313c4edaf580)
  ![image](https://github.com/user-attachments/assets/d77c8fc5-5baa-41b8-bd9e-1ce94dfff5c8)

  The ROC curve suggests that the model's performance is worst than logistic regression by plotting the true positive rate (sensitivity) against the false positive rate, with 93.14% area under the curve (AUC).

![image](https://github.com/user-attachments/assets/796c01a3-82cc-4cbd-91d9-e1ada3420777)
![image](https://github.com/user-attachments/assets/10c67ec7-9606-4b21-9f9b-40ce2b55b4f8)
![image](https://github.com/user-attachments/assets/de49840c-0dd9-4ae9-83e6-3def7462d4e2)
![image](https://github.com/user-attachments/assets/c7d197bd-96d7-46f8-bcb7-60bbbc455841)

Except precision plot, all plot show us the best model is LR. Since the aim of the research is discrimination of fake and true news, the model is selected by accuracy metric.
