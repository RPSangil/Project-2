# Project-2
**FinTech Group Assessment 2**

- Maggie Zhan (L)
- Declan Morandin
- Marc Julies
- Raelyn Sangil

## Project Description

### Background Information

An exchange-traded fund (ETF) is a type of pooled investment security that operates much like a mutual fund. Typically, ETFs will track a particular index, sector, commodity, or other asset, but unlike mutual funds, ETFs can be purchased or sold on a stock exchange the same way that a regular stock can. An ETF can be structured to track anything from the price of an individual commodity to a large and diverse collection of securities. ETFs can even be structured to track specific investment strategies.[<sup>1</sup>](#reference-list)

BlackRock offers a range of solutions for institutions, financial professionals and individuals across the globe. From shop assistants in your local stores to national organisations and non-profits, BlackRock has helped people take control of their financial security.[<sup>2</sup>](#reference-list)

iShares ETFs cover a broad range of asset classes, risk profiles and investment outcomes.[<sup>3</sup>](#reference-list)

Machine learning is the concept that a computer program can learn and adapt to new data without human intervention. Machine learning is a field of artificial intelligence (AI) that keeps a computer’s built-in algorithms current regardless of changes in the worldwide economy.[<sup>4</sup>](#reference-list)

### The Scope

This project will use machine learning to do 2 main actions:

1. Run a unsupervised machine learning model to cluster iShares ETFs on https://www.blackrock.com/au/individual/products/investment-funds.
2. Use 2 supervised machine learning models to predict if certain iShares ETFs are worth investing into based on percentage cumulative returns.

## Model - Unsupervised - K-means

K-means clustering is one of the simplest and popular unsupervised machine learning algorithms Typically, unsupervised algorithms make inferences from datasets using only input vectors without referring to known, or labelled, outcomes. The objective of K-means is simple: group similar data points together and discover underlying patterns. To achieve this objective, K-means looks for a fixed number (k) of clusters in a dataset.[<sup>5</sup>](#reference-list)

### Data Preparation 

#### Initial set up

Unfortunately we were unable to access an API for the raw data.

The raw data for this project was gathered from https://www.blackrock.com/au/individual/products/investment-funds as a group of 36 excel files. To create the csv needed for this project, we manually merged all the excel files together retaining only the returns data and iShares ETF name. This data was then transposed so that the columns were the dates and the iShares were the rows.

#### Dependancies

For our Pre Processing, we used the following libraries. Please be sure to pip install them before running `insert perm link to unsupervised pre processing`.

- numpy
- pandas
- pathlib
- matplotlib

#### Pre Processing

As you will see in `insert perm link to unsupervised pre processing`, we sliced the raw data to the last 5 years (30 June 2017 - 30 June 2022). Then we reviewed the data and if any row had less than 3 null values, we willed these values with 0s. Then we dropped the rows that had more than 3 null values.

Standard deviations were calculated for 6 time slices.

- 2017-2022
- 2017-2018
- 2018-2019
- 2019-2020
- 2020-2021
- 2021-2022

3 main dataframes were created (last 5 years, last 3 years, last 1 year) and the appropriate standard deviations were auppended as new columns.

The dataframes were then saved as csv files for the model to run through.

#### Clean-up and Exploration

During this process we noticed several curiosities:
- As not all the iShare ETFs were created at the same time, a slice of the recent years was necessary to avoid excessive null values in our dataframe.
- In particular iShares Core Cash ETF had a long run of 0 from 31/1/21 to 31/3/22. This may be due to `explore reason`

### Running the Model

#### Dependancies

For our Pre Processing, we used the following libraries. Please be sure to pip install them before running `insert perm link to unsupervised pre processing`.

- pandas
- pathlib
- sklearn.cluster
- warnings

#### Exlopring the Results

The model sucessfully clustered the iShare ETFs into 6 different clusters.

## Model - Unsupervised - `insert model type`

### Data Preparation 

#### Dependancies

For our Pre Processing, we used the following libraries. Please be sure to pip install them before running `insert perm link to unsupervised pre processing`.

- pandas
- pathlib
- numpy
- warnings

#### Pre Processing

As you will see in `insert perm link to supervised pre processing`, we calculated the percentage cumulative returns for each iShares ETF and added this value as a column to the exisiting dataframes. Then we made a new column that provided a `True` or `False` values to determine if the target percentage cumulative returns was met for each iShares ETF.

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
- [<sup>4</sup> https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1](https://towardsdatascience.com/understanding-k-means-clustering-in-machine-learning-6a6e67336aa1)