# Project-2
**FinTech Group Assessment 2**

IMPORTANT NOTICE - This content is for informational purposes only, you should not construe any such information or other material as investment, financial, or other advice. Nothing contained within this repo constitutes a solicitation, recommendation or endorsement

---

### Table of Contents
- [Group Members](#Group-Members)
- [Introduction](#Introduction)
    * [What is an ETF?](#What-is-an-ETF?)
    * [Who is BlackRock?](#Who-is-BlackRock?)
    * [Why use Machine Learning?](#Why-use-Machine-Learning?)
- [Our Goal](#Our-Goal)
- [Dependencies/Libraries](#Dependencies/Libraries)
- [Data Preparation](#Data-Preparation)
   * [Raw Data](#Raw-Data)
   * [Pre Processing for K-Means](#Pre-Processing-for-K-Mean)
   * [Pre Processing the Data for SMV and Logistic Regression](#Pre-Processing-the-Data-for-SMV-and-Logistic-Regression)
   * [Data Exploration](#Data-Exploration)
- [Unsupervised Model - K-means](#Unsupervised-Model---K-means)
- [Supervised Model- SMV and Logistic Regression](#Supervised-Model--SMV-and-Logistic-Regression)
- [How did the Models Perform?](#How-did-the-Models-Perform?)
- [Future Opportunities Given Time and Resources](#Future-Opportunities-Given-Time-and-Resources)
- [Reference list](#Reference-list)

## Group Members

- Maggie Zhan (L)
- Declan Morandin
- Marc Julies
- Raelyn Sangil

[Back to Table of Contents](#Table-of-Contents)

## Introduction

### What is an ETF?

An exchange-traded fund (ETF) is a type of pooled investment security that operates much like a mutual fund. Typically, ETFs will track a particular index, sector, commodity, or other asset, but unlike mutual funds, ETFs can be purchased or sold on a stock exchange the same way that a regular stock can. An ETF can be structured to track anything from the price of an individual commodity to a large and diverse collection of securities. ETFs can even be structured to track specific investment strategies.[<sup>1</sup>](#reference-list)

### Who is BlackRock?

BlackRock offers a range of solutions for institutions, financial professionals and individuals across the globe. From shop assistants in your local stores to national organisations and non-profits, BlackRock has helped people take control of their financial security.[<sup>2</sup>](#reference-list)

iShares ETFs cover a broad range of asset classes, risk profiles and investment outcomes.[<sup>3</sup>](#reference-list)

### Why use Machine Learning?

Machine learning is the concept that a computer program can learn and adapt to new data without human intervention. Machine learning is a field of artificial intelligence (AI) that keeps a computer’s built-in algorithms current regardless of changes in the worldwide economy.[<sup>4</sup>](#reference-list)

By developing a strong and accurate Machine Learning model, it can assist in making profitable trades that are based off of objective Technical Analysis rather than the biased emotional decisions of a human trader. A Machine Learning model that makes automated trades is also much fasterand efficient than a human trader could ever be. It provides an oppotunity to fine tune the approach.

[Back to Table of Contents](#Table-of-Contents)

## Our Goal

This project will use machine learning to do 2 main actions:

1. Run an unsupervised machine learning model (K-means) to cluster iShares ETFs on https://www.blackrock.com/au/individual/products/investment-funds.
2. Use 2 supervised machine learning models (SMV and Logistic Regression) to run through the pre processed data (data was analyised using algorithmic trading).

[Back to Table of Contents](#Table-of-Contents)

## Dependencies/Libraries
TO be able to implement and use this code there are some dependencies that will first need to be installed. These include:
 - NumPy [https://pypi.org/project/numpy/](https://pypi.org/project/numpy/)
 - pandas [https://pypi.org/project/pandas/](https://pypi.org/project/pandas/)
 - pathlib [https://pypi.org/project/pathlib/](https://pypi.org/project/pathlib/)
 - hvplot [https://pypi.org/project/hvplot/](https://pypi.org/project/hvplot/)
 - sklearn [https://pypi.org/project/scikit-learn/](https://pypi.org/project/scikit-learn/)
 - warnings [https://pypi.org/project/pytest-warnings/](https://pypi.org/project/pytest-warnings/)

 [Back to Table of Contents](#Table-of-Contents)

## Data Preparation 

### Raw Data

Unfortunately we were unable to access an API for the raw data.

The raw data for this project was gathered from https://www.blackrock.com/au/individual/products/investment-funds as a group of 36 excel files. To create the csv needed for this project, we manually merged all the excel files together retaining only the returns data and iShares ETF name. This data was then transposed so that the columns were the dates and the iShares were the rows.

### Pre Processing for K-Means

1. Cleaned the data:
- Create a slice from 30-Jun-2017 to 30-Jun-2022.
- When a row had less than 3 NaNs, the row was still useable. We filled the NaNs of such rows with 0.
- When a row had greater than 3 NaNs, we dropped the row.
2. Create 3 time periods to be reviewed for analysis.The time periods to be reviewed are:
- 1 year (30-Jun-2021 to 30-Jun-2022)
- 3 year (30-Jun-2019 to 30-Jun-2022)
- 5 year (30-Jun-2017 to 30-Jun-2022)
3. Calculate Standard Deviations for each time period and add them to the dataframe for each time period slice.
4. Calculate Return Average for each time period and add them to the dataframe for each time period slice.
5. Save each datafram for the time period slices to .csv for later use.

[Pre Processing](https://github.com/RaelynSangil/Project-2/blob/41ff280da7d0d2be446952b01d7f530fe8061a38/Code/Unsupervised/Unsupervised_Pre_Processing.ipynb)

### Pre Processing the Data for SMV and Logistic Regression

During this part, we analyised the data using Bollinger Band Trading Strategy.[<sup>5</sup>](#reference-list)

[dummy](dummy link)

### Data Exploration

During this process we noticed several curiosities:
- As not all the iShare ETFs were created at the same time, a slice of the recent years was necessary to avoid excessive null values in our dataframe.
- In particular iShares Core Cash ETF had a long run of 0 from 31/1/21 to 31/3/22. This may be due to the ETf being forced to close during this period. The shares inside of the ETF would have been impacted by Covid19 and an alterative would have been made available to customers during this time period.

[Back to Table of Contents](#Table-of-Contents)

## Unsupervised Model - K-means

K-means clustering is one of the simplest and popular unsupervised machine learning algorithms Typically, unsupervised algorithms make inferences from datasets using only input vectors without referring to known, or labelled, outcomes. The objective of K-means is simple: group similar data points together and discover underlying patterns. To achieve this objective, K-means looks for a fixed number (k) of clusters in a dataset.[<sup>6</sup>](#reference-list)

- [1 year K-means](https://github.com/RaelynSangil/Project-2/blob/41ff280da7d0d2be446952b01d7f530fe8061a38/Code/Unsupervised/Unsupervised_1_Year_Model.ipynb)
- [3 year K-means](https://github.com/RaelynSangil/Project-2/blob/41ff280da7d0d2be446952b01d7f530fe8061a38/Code/Unsupervised/Unsupervised_3_Year_Model.ipynb)
- [5 year K-means](https://github.com/RaelynSangil/Project-2/blob/41ff280da7d0d2be446952b01d7f530fe8061a38/Code/Unsupervised/Unsupervised_5_Year_Model.ipynb)

[Back to Table of Contents](#Table-of-Contents)

## Supervised Model- SVM and Logistic Regression

“Support Vector Machine” (SVM) is a supervised machine learning algorithm that can be used for both classification or regression challenges. However,  it is mostly used in classification problems. In the SVM algorithm, we plot each data item as a point in n-dimensional space (where n is a number of features you have) with the value of each feature being the value of a particular coordinate. Then, we perform classification by finding the hyper-plane that differentiates the two classes very well.[<sup>7</sup>](#reference-list)

This type of statistical model (also known as logit model) is often used for classification and predictive analytics. Logistic regression estimates the probability of an event occurring, such as voted or didn’t vote, based on a given dataset of independent variables. Since the outcome is a probability, the dependent variable is bounded between 0 and 1. In logistic regression, a logit transformation is applied on the odds—that is, the probability of success divided by the probability of failure.[<sup>8</sup>](#reference-list)

[dummy](dummy link)
[dummy](dummy link)
[dummy](dummy link)

[Back to Table of Contents](#Table-of-Contents)

## How did the Models Perform?

`<Discuss your findings. Was the model sufficient for the predictive task? If not, why not? What inferences or general conclusions can you draw from your model performance?>`

[Back to Table of Contents](#Table-of-Contents)

## Future Opportunities Given Time and Resources

- The data that the K-means model was run through is simplified. K-means was specifically used to create the clusters to be analysied in a supervised learning model. We understand that K-means should be used for more complex data, however, given the time contraints we were unable to plot the more complex data and therefor used the simplified data.
- Each time the K-means model is run, the names of the clusters changed. The contents remained the same though. Given more time, we would have adjusted this so that the clusters remained fixed.
- Due to the above issue, the selection of the cluster needed to be done manually each time. Given more time, we would have automated the selection of the cluster and controlled that change.

[Back to Table of Contents](#Table-of-Contents)

# Reference list

- [<sup>1</sup> https://www.investopedia.com/terms/e/etf.asp](https://www.investopedia.com/terms/e/etf.asp)
- [<sup>2</sup> https://www.blackrock.com/au/individual/about-us/about-blackrock](https://www.blackrock.com/au/individual/about-us/about-blackrock)
- [<sup>3</sup> https://www.blackrock.com/au](https://www.blackrock.com/au)
- [<sup>4</sup> https://www.investopedia.com/terms/m/machine-learning.asp](https://www.investopedia.com/terms/m/machine-learning.asp)
- [<sup>5</sup> https://www.youtube.com/watch?v=AIDKh55y64A&t=690s](https://www.youtube.com/watch?v=AIDKh55y64A&t=690s)
- [<sup>6</sup> https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1](https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1)
- [<sup>7</sup> https://www.analyticsvidhya.com/blog/2017/09/understaing-support-vector-machine-example-code/](https://www.analyticsvidhya.com/blog/2017/09/understaing-support-vector-machine-example-code/)
- [<sup>8</sup> https://www.ibm.com/au-en/topics/logistic-regression#:~:text=Logistic%20regression%20estimates%20the%20probability,bounded%20between%200%20and%201.](https://www.ibm.com/au-en/topics/logistic-regression#:~:text=Logistic%20regression%20estimates%20the%20probability,bounded%20between%200%20and%201.)

[Back to Table of Contents](#Table-of-Contents)