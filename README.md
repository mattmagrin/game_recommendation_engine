# game_recommendation_engine
Built to help a future data scientist intern maximize hours of fun and save money on new purchases


## Project Overview

* **Understanding the problem faced by Brazilians:**  A relevant part of the gaming market resides in Brazil, where thousands of fans face high direct conversion values from US Dollars to Brazilian Real, especially considering the value of a AAA game in relation to the minimum wage. Thus, it is evident how the **average Brazilian has no money to spend on games that will not be converted into hours of fun.**

imagem heroku

* **Solution developed:** Thinking about this problem, I created a complete pipeline, from problem formulation to deployment, returning only recommended games and being able to be filtered by platform, all based on data. To do this, we went through several steps: scraping, data processing, modeling, optimization, until reaching the final solution that was hosted on heroku, helping me a lot to decide which games to buy.


## How was this solution developed?
1. First, I formulated the problem and looked for the best site to extract information and carry out my project. The page chosen was Metacritic, which has a lot of information about thousands of games on all platforms, in addition to a vast amount of reviews made by experts and members of its community;
2. With the chosen site, I created a Web Scraper divided into two stages: the site search data collector, which was responsible for listing all games on each platform, and the data collector for each game found. The second part demanded more efforts because it had a lot of information on the page;
3. After collecting the raw data, I processed it to create a consumable dataset to train the machine learning models I would use;
4. To do the modeling later, the labeling was done manually, seeking to balance the number of positive and negative examples. In order to do this in an optimized way, reducing time and resources, the Active Learning methodology was used, in which some classification models were also trained and their performance evaluated via cross-validation;
5. >>With all the data, I created two more models, Random Forest and LightGBM, optimized their hyperparameters to perform a more accurate classification, and merged their results using an ensemble between them;
6. In the final step, I chose to release v1.0 of the solution with the help of streamlit on heroku.

## Main tools used
* pandas
* numpy
* scikit-learn
* beautifulsoup4
* requests
* regex
* scipy
* scikit-optimize
* streamlit
* heroku
