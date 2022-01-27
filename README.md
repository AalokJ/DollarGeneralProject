# Attack of the Dollar Generals: A Location Analysis of Dollar General Stores
Author: [Aalok Joshi](https://www.linkedin.com/in/aalokjoshi113/) 
# Background
Dollar stores, also known as variety stores or general stores, have been around in the United States since the early 20th century. Generally speaking, they are retail stores which sell a wide variety of items for discounted or fixed price points. Historically these price points have been five cents, ten cents, or a dollar - leading to their generally accepted name being dollar stores. 
Today dollar stores are ubiquitous throughout the US and much of the world. If you are reading this right now its very likely you have been to a dollar store and that there is one in your hometown. There are three industry leading chains that dominate the dollar store landscape today - namely, Family Dollar, Dollar Tree, and the focus of this project Dollar General. Since its inception in 1955 Dollar General has grown at a breakneck speed. By 1968 Dollar General had roughly 300 stores and went public on the stock exchange, however, this success is nothing compared to what they have done in the past four decades. Today Dollar General stands at almost 18,000 stores spread across 46 states. In an era when retail has been dying a slow death - Dollar General has bucked the trend and not only avoided stagnation but rather has exploded. This begs the obvious question... how do they do it?
Well, Dollar General has been accused of being [predatory](https://slate.com/business/2021/07/dollar-general-food-deserts-grocery-stores.html) in its practices and [bad for the poor](https://www.cnn.com/2019/07/19/business/dollar-general-opposition/index.html). On the other hand it has been lauded as a company that will "go where Walmart won't" by bringing retail to [rural America](https://www.theguardian.com/business/2018/aug/13/dollar-general-walmart-buhler-haven-kansas) and providing much needed jobs. I aim to build a predictive model that can predict whether a town has a Dollar General or not based on income and demographic data. This can also answer/shed light into whether the accusations against Dollar General are true or if the areas that Dollar Generals really do stand to gain from stores being present.

# Overview
My motivation for this project is to investigate how Dollar General has choosen to open its stores throughout the country and to shed light ont the accusations that Dollar General is targetting rural and poor Americans in particular. 

I have choosen Dollar General for a couple reasons:
1. It has over 18,000 stores and is prevalant in almost every state in the country
2. It continues to grow amidst a retail climate that has seen many large players shrink their physical footprint - with plans for 1000 more stores in the next 4 years.
3. Their business has attracted the attention of media houses like CNN, WSJ, NYT, The Guardian, etc. 

# Business Objective
From a business perspective this project has applications for a wide range of roles and industries. The findings apply to Dollar General itself, but also to its competitors who have failed to expand at the pace that Dollar General has. By setting out to categorize counties into those having Dollar Generals or not, this project is able to create a profile of what a Dollar General county looks like compared to a non Dollar General county. Based on the data the two different types of counties can be profiled by demographics, income, income per capita, occupation, occupational industry, gender, and many more features. This can also be insightful for private equity firms, consulting firms, and research firms interested in this space. 


# Data
The data used in this project comes from two main sources. Firstly the Dollar General [data](https://www.scrapehero.com/store/product/dollar-store-locations-in-the-usa/) comes from ScrapeHero a data scraping vendor. To download this data follow the hyperlink in the previous sentence. Secondly, the American Community Survey data was downloaded from a public Kaggle [dataset](https://www.kaggle.com/muonneutrino/us-census-demographic-data?select=acs2017_county_data.csv) that includes demographic, monetary, gender based, and occupational data on a county level.

# Methods
I set the presence of a Dollar General or the absence of a Dollar general as the binary target variable, with 1 indicating the presence of a Dollar General and 0 indicating the absence of a Dollar General in the given county.

After this I built 3 classifier models - Decision Tree, Random Forest, and Logistic Regression. I used grid search to tune hyperparameters and to select the best one. Additionally I used cross validation and scoring to select the best classifier model.

# Results
All three models performed relatively similarly, however, the Random Forest model was the best one. Below are the AUC curves for all three of the models. The most important and insightful metric for an analysis like this is the precision score. The precision score is the ratio of correctly predicted positive observations to the total predicted positive observations. The precision score is insightful because it allows us to see the false positves aka the counties that do NOT have a Dollar General but which our model has incorrectly classified as having a Dollar General. These counties are ripe for expansion and, according to our model, they fit the profile of a Dollar General county. For our three models, Decision Tree, Log Regression, and Random Forest the precision scores are 80.9%, 81.5%, 84.0% respectively. Therefore Random Forest is the best model for this project. 

Decision Tree ROC
![chart1](https://github.com/AalokJ/FlatironFP/blob/main/Images/Decision%20Tree%20AUC.png)

Logisitic Regression ROC
![chart2](./Images/Decision Tree AUC.png)

Random Forest ROC
![chart2](./Images/Random Forest AUC.png)

# Conclusion
In conclusion, the idea that Dollar General is specifically choosing to expand in more rural, low income communities is not without merit. However, this project does not provide consclusive proof either way that Dollar General's expansion strategy is targetting these communities. 

# Future Work
In the future I think there are three main extensions that can be pursued...
1) Use Time Series data to model Dollar General's expansion over time
2) Use Zip Code level data instead of county data as a zip code is a more minute unit of measurement
3) Deploy a Streamlit web app to display data and visualizations

## Repository Structure
```
├── Data                                <- Both sourced externally and generated from code
├── Images                              <- Both sourced externally and generated from code
├── Notebooks                           <- Narrative documentation of analysis in Jupyter notebook
├── Aalok's FINAL NOTEBOOK.ipynb        <- Final Notebook 
├── Capstone_presentation.pdf           <- PDF version of project presentation
└── README.md                           <- The top-level README for reviewers of this project
