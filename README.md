# Project-2
**FinTech Group Assessment 2**

- Maggie Zhan (L)
- Declan Morandin
- Marc Julies
- Raelyn Sangil

## Project Description

An exchange-traded fund (ETF) is a type of pooled investment security that operates much like a mutual fund. Typically, ETFs will track a particular index, sector, commodity, or other asset, but unlike mutual funds, ETFs can be purchased or sold on a stock exchange the same way that a regular stock can. An ETF can be structured to track anything from the price of an individual commodity to a large and diverse collection of securities. ETFs can even be structured to track specific investment strategies.[<sup>1</sup>](#reference-list)

Known as the "Oracle of Omaha," Warren Buffett is one of the most successful investors of all time. He runs Berkshire Hathaway, which owns more than 60 companies, including insurer Geico, battery maker Duracell and restaurant chain Dairy Queen.[<sup>2</sup>](#reference-list) Berkshire Hathaway is a holding company for a multitude of businesses, including GEICO and Fruit of the Loom. It's run by chair and CEO Warren Buffett. Berkshire Hathaway is headquartered in Omaha, Nebraska. Originally, it was a company comprised of a group of textile milling plants.[<sup>3</sup>](#reference-list)

It’s often said that investing in Berkshire Hathaway is like buying into an exchange-traded fund (ETF). Both offer diversification across industry sectors. But while ETFs are often passively invested, seeking to track a benchmark index, Berkshire Hathaway actively buys stocks and businesses.[<sup>4</sup>](#reference-list)

Machine learning is the concept that a computer program can learn and adapt to new data without human intervention. Machine learning is a field of artificial intelligence (AI) that keeps a computer’s built-in algorithms current regardless of changes in the worldwide economy.[<sup>5</sup>](#reference-list)

### The Scope

This project will use machine learning to do 2 main actions:

1. Review the stocks that Berkshire Hathaway invests into on the US Market and use unsupervised machine learning to determine the top `<insert selected stock amount>` performing stocks of that list.
2. Use machine learning to automate the decision making process of when to buy and sell these stocks for optimal returns.

## Model Summary

`<insert information about predictive model used for each action listed above and why it was the best choice for the data>`

## Data Cleaning

### Dependancies

- `<insert list of libraries used and what they were used for>`

### Clean-up and Exploration

`<insert steps taken during data cleaning and APIs used. Note any difficulties>`
- We found that the duration of the ETFs varied
- we found that iShares Core Cash ETF had a long run of 0 from 31/1/21 to 31/3/22.

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
- [<sup>2</sup> https://www.forbes.com/profile/warren-buffett/?sh=615555e04639](https://www.forbes.com/profile/warren-buffett/?sh=615555e04639)
- [<sup>3</sup> https://www.investopedia.com/terms/b/berkshire-hathaway.asp](https://www.investopedia.com/terms/b/berkshire-hathaway.asp)
- [<sup>4</sup> https://smartasset.com/investing/how-to-buy-berkshire-hathaway-stock#:~:text=It's%20often%20said%20that%20investing,actively%20buys%20stocks%20and%20businesses.](https://smartasset.com/investing/how-to-buy-berkshire-hathaway-stock#:~:text=It's%20often%20said%20that%20investing,actively%20buys%20stocks%20and%20businesses.)
- [<sup>5</sup> https://www.investopedia.com/terms/m/machine-learning.asp](https://www.investopedia.com/terms/m/machine-learning.asp)