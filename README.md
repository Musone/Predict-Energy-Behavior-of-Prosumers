# Predicting the Energy Behavior of Prosumers
CPSC 340/540 Grad-Project.

Resulting Research Paper Link: https://github.com/Musone/Predict-Energy-Behavior-of-Prosumers/blob/master/Results.pdf

Data Link: https://drive.google.com/drive/folders/1TgD14QwrcnvYTQKxg2xDVbDUdWAg_G3T?usp=sharing

Kaggle Link: https://www.kaggle.com/competitions/predict-energy-behavior-of-prosumers/overview

### Preliminary
Eesti Energy is an Estonian public energy company, which allows customers to install solar panels and feed excess power back to the grid.

Customers who choose to do so are referred to as “prosumers” because they are both consumers and producers of power. If a prosumer produces more power than they consume, then they have a net-negative power expenditure and they inject their surplus into the power-grid, thereby contributing to the nation-wide power supplies. However, if they have net-positive power expenditure, they have to pay for power drawn from the power grid to balance out their load.

Eesti Energia has been collecting data from many prosumers over roughly one and a half years, from September 2021 to May 2023, and has made their data publicly available on Kaggle.

### Goal
The advent of the global climate crisis has sparked a shift away from carbon emission towards greater reliance on renewable green energy, produced from sources such as solar panels, for power consumption in homes, offices, and industrial complexes. Pioneers on the forefront of this movement face many challenges such as power load management, estimating their budgets, and projecting the impact of their initiatives on a nation-wide scale. 

Our goal is to analyze and predict both the power expenditure and consumption of buildings in Estonia that belong to customers of Eesti Energia based on provided variables. Predictions are based off of three factors related to the consumer (the county, whether they’re a business or private individual and the type of contract they have with Eesti Energia), a detailed weather forecast (including local temperature, dewpoint, and the cloud coverage), the date, and gas and electrical prices.

In creating our prediction model, we hope to provide detailed insights for companies and individuals looking to explore and contribute to the emergent market of green energy. This, of course, will be a perfect application for our supervised learning methods.

### Why is this relevant?
This data presents a highly stochastic geography, time, and weather based problem. If we can train a model to semi-accurately predict future power consumption from these power grids, it could be generalized and used in transfer-learning problems with similar variables. 

The specific problem we wish to solve will help Eesti Energia determine the amount of excess power generated by prosumers, and thus may allow them to adjust their own power production to be more efficient while maintaining a low risk of blackouts. This sort of information could help decrease costs for taxpayers while increasing overall revenue for the Eesti Energia. 

If a model were to be able to predict this sort of information, there might be other avenues unrelated to energy that could benefit from a prediction method that applies to geographical and weather related data, such as farming. 

### Proposed solutions and methods
Our focus will be on comparing several machine learning algorithms based on their performance on this dataset.

We will start with an exploratory data analysis to visualize, build intuitions, and form hypotheses on the provided data in order to get a sense of how a variety of models may perform. This will also give us an insight into whether or not there are immediate correlations between certain variables. 

Throughout this process, we will clean the data by choosing an appropriate strategy to handle the provided features. Common problems may involve solutions such as imputing missing values, standardizing numeric values, and encoding categorical columns. We will also consider any meaningful feature transformations that come to mind, such as converting dates to days of the week, bucketing dates into seasons, and removing irrelevant features.

A notebook with basic feature cleaning and a straightforward implementation of XGBoost has already been provided. We will use this as a template, but carefully consider the design decisions available and make decisions based on what we feel is most suitable for this data.

The methods we will be evaluating fall into one of three categories: boosted regression trees, simple regression, and neural networks. These will be implemented in scikit-learn, with the exception of the boosted regression tree, which will be done in XGboost.
XGboost is a common and reasonably standard approach in Kaggle competitions. This model will provide us with a baseline performance for our problem.
For basic regression, we will consider linear least squares regression, polynomial regression, and gaussian RBF. We will also combine them with the L0, L1, and L2 regularization penalties that were previously discussed in class. We will be using cross validation to tune the hyperparameters of each of these models.
We will also use a neural network with ReLU activation, using cross validation to try a small handful of different depths and numbers of neurons per layer. If time allows, we will do a PCA using SVD and train the models on the latent factors for a further point of comparison.

Between all these models, we will compare the training errors and the errors on a test set provided by the competition organizers. We intend to enter our best model into the competition, where it will be validated on data collected after the submission date.

### Contribution and conclusion
While a small handful of previous papers have proposed solutions to similar problems, there is no public consensus on which methods are appropriate for determining prosumer energy consumption or production. By competing in the ongoing Kaggle competition, we will help determine how appropriate it is to use AI to address this problem, and we will contribute to the body of work assessing the relative utility of different methods.

Furthermore, there are numerous other similarly structured problems, utilizing weather-dependent, geographic, temporal data to predict an outcome. Here we consider the net usage of prosumers, but the findings in this specific application may provide a starting point for problems such as predicting vehicle emissions, water usage, or crop production. As these problems become increasingly relevant to our society, we hope that AI can provide a useful way forward.
