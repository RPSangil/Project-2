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
    * [Our Goal](#Our-Goal)
    * [The Process](#The-Process)
- [How To Use This Project](#How-To-Use-This-Project)
   * [Dependencies/Libraries](#Dependencies/Libraries)
   * [Adjust To Your Needs](#Adjust-To-Your-Needs)
- [Conclusion](#Conclusion)
   * [How Well Did The Model Perform?](#How-Well-Did-The-Model-Perform?)
   * [Things We Could Improve on Given Time](#Things-We-Could-Improve-on-Given-Time)

## Group Members

- Maggie Zhan (L)
- Declan Morandin
- Marc Julies
- Raelyn Sangil

## Introduction

### What is an ETF?

An exchange-traded fund (ETF) is a type of pooled investment security that operates much like a mutual fund. Typically, ETFs will track a particular index, sector, commodity, or other asset, but unlike mutual funds, ETFs can be purchased or sold on a stock exchange the same way that a regular stock can. An ETF can be structured to track anything from the price of an individual commodity to a large and diverse collection of securities. ETFs can even be structured to track specific investment strategies.[<sup>1</sup>](#reference-list)

### Who is BlackRock?

BlackRock offers a range of solutions for institutions, financial professionals and individuals across the globe. From shop assistants in your local stores to national organisations and non-profits, BlackRock has helped people take control of their financial security.[<sup>2</sup>](#reference-list)

iShares ETFs cover a broad range of asset classes, risk profiles and investment outcomes.[<sup>3</sup>](#reference-list)

### Why use Machine Learning?

Machine learning is the concept that a computer program can learn and adapt to new data without human intervention. Machine learning is a field of artificial intelligence (AI) that keeps a computer’s built-in algorithms current regardless of changes in the worldwide economy.[<sup>4</sup>](#reference-list)

By developing a strong and accurate Machine Learning model, it can assist in making profitable trades that are based off of objective Technical Analysis rather than the biased emotional decisions of a human trader. A Machine Learning model that makes automated trades is also much fasterand efficient than a human trader could ever be. It provides an oppotunity to fine tune the approach

## Our Goal

This project will use machine learning to do 2 main actions:

1. Run an unsupervised machine learning model (K-means) to cluster iShares ETFs on https://www.blackrock.com/au/individual/products/investment-funds.
2. Use 2 supervised machine learning models (SMV and Logistic Regression) to run through the pre processed data (data was analyised using algorithmic trading).

## Dependencies/Libraries
TO be able to implement and use this code there are some dependencies that will first need to be installed. These include:
 - NumPy [https://pypi.org/project/numpy/](https://pypi.org/project/numpy/)
 - pandas [https://pypi.org/project/pandas/](https://pypi.org/project/pandas/)
 - pathlib [https://pypi.org/project/pathlib/](https://pypi.org/project/pathlib/)
 - hvplot [https://pypi.org/project/hvplot/](https://pypi.org/project/hvplot/)
 - sklearn [https://pypi.org/project/scikit-learn/](https://pypi.org/project/scikit-learn/)
 - warnings [https://pypi.org/project/pytest-warnings/](https://pypi.org/project/pytest-warnings/)

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

### Pre Processing the Data for SMV and Logistic Regression

### Data Exploration

During this process we noticed several curiosities:
- As not all the iShare ETFs were created at the same time, a slice of the recent years was necessary to avoid excessive null values in our dataframe.
- In particular iShares Core Cash ETF had a long run of 0 from 31/1/21 to 31/3/22. This may be due to the ETf being forced to close during this period. The shares inside of the ETF would have been impacted by Covid19 and an alterative would have been made available to customers during this time period.

## Model - Unsupervised - K-means

K-means clustering is one of the simplest and popular unsupervised machine learning algorithms Typically, unsupervised algorithms make inferences from datasets using only input vectors without referring to known, or labelled, outcomes. The objective of K-means is simple: group similar data points together and discover underlying patterns. To achieve this objective, K-means looks for a fixed number (k) of clusters in a dataset.[<sup>5</sup>](#reference-list)

## Model - Supervised - SMV and Logistic Regression

“Support Vector Machine” (SVM) is a supervised machine learning algorithm that can be used for both classification or regression challenges. However,  it is mostly used in classification problems. In the SVM algorithm, we plot each data item as a point in n-dimensional space (where n is a number of features you have) with the value of each feature being the value of a particular coordinate. Then, we perform classification by finding the hyper-plane that differentiates the two classes very well.[<sup>6</sup>](#reference-list)

### Running the Model

#### Exlopring the Results

The model sucessfully clustered the iShare ETFs into 6 different clusters.

## Model - Unsupervised - `insert model type`

### Running the Model

#### Dependancies

## Model Training

`<Discuss the overall training process and highlight anything of interest with the training process>`

## Model Evaluation

`<insert screenshots of code showing how the model performance was evaluated and discuss the techniques used>`

## Conclusions

`<Discuss your findings. Was the model sufficient for the predictive task? If not, why not? What inferences or general conclusions can you draw from your model performance?>`

## Room for Improvement

### Difficulties

![this is an image of an issue we encountered](this is a link)

- `<insert list of difficulties encountered>`
- step one > pre processing for the unsupervised learning turned out more complex than we had expected
- we could no locate an API for Blackrock so we manually grabbed the excel files and merged them

### Future opportunities

- `<insert list of opportunities or future directions this project could have taken if given more time>`
- talk about other possibilities for the unsupervised learning (different features across different models to check and confirm if this affects our list of "best performers")

# Reference list

- [<sup>1</sup> https://www.investopedia.com/terms/e/etf.asp](https://www.investopedia.com/terms/e/etf.asp)
- [<sup>2</sup> https://www.blackrock.com/au/individual/about-us/about-blackrock](https://www.blackrock.com/au/individual/about-us/about-blackrock)
- [<sup>3</sup> https://www.blackrock.com/au](https://www.blackrock.com/au)
- [<sup>4</sup> https://www.investopedia.com/terms/m/machine-learning.asp](https://www.investopedia.com/terms/m/machine-learning.asp)
- [<sup>5</sup> https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1](https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1)
- - [<sup>6</sup> https://www.analyticsvidhya.com/blog/2017/09/understaing-support-vector-machine-example-code/](https://www.analyticsvidhya.com/blog/2017/09/understaing-support-vector-machine-example-code/)