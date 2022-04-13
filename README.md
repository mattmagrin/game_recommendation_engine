# game_recommendation_engine
Built to help gamers maximize hours of fun and save money on new purchases

• If you want to use the deployed model v1.0 [Click here](https://recomendacaojogosb.herokuapp.com/) 

## Project Overview

* **Understanding the problem faced by many Brazilians:**  A relevant part of the gaming market resides in Brazil, where thousands of fans face high direct conversion values from US Dollars to Brazilian Real, especially on AAA titles. Therefore, it is safe to say that the **average Brazilian has no money to spend on games that will not be converted into hours of fun.**

![GIF](https://s7.gifyu.com/images/ezgif.com-gif-maker8765646b5bd8d8cb.gif)

* **Solution developed:** Thinking about this problem, that I also include myself, i created a complete pipeline, from problem formulation to deployment, returning only recommended games with high probability of relevance and being also able to be filtered by platform, with the help of some machine learning models.

* To do this, we went through several steps: scraping, data processing, modeling, optimization, until reaching the final solution that was hosted on heroku, helping me a lot to decide which games to buy.


## How was this solution developed?
1. First, I formulated the problem and looked for the best site to extract information and carry out my project. The page chosen was [Metacritic](https://www.metacritic.com/), which has a lot of information about thousands of games on all platforms, in addition to a vast amount of reviews made by experts and members of its community;

2. With the chosen site, I created a Web Scraper divided into two stages: the [site search data collector](https://github.com/mattmagrin/game_recommendation_engine/blob/main/Extraction%20and%20modeling/1_collector_search.ipynb), which was responsible for listing all games on each platform, and the [data collector for each game found](https://github.com/mattmagrin/game_recommendation_engine/blob/main/Extraction%20and%20modeling/2_data_collection_games.ipynb). The second part demanded more efforts because it had a lot of information on the page;

3. After collecting the raw data, I processed it to create a [consumable dataset to train the machine learning models I would use](https://github.com/mattmagrin/game_recommendation_engine/blob/main/Extraction%20and%20modeling/3_data_treatment%20.ipynb);

4. To do the modeling, the labeling was done manually, seeking to balance the number of positive and negative examples. In order to do this in an optimized way, reducing time and resources, [the Active Learning methodology was used, in which some classification models were also trained and their performance evaluated](https://github.com/mattmagrin/game_recommendation_engine/blob/main/Extraction%20and%20modeling/4_modeling___active_learning.ipynb) 

5. I chose to release [v1.0 of the solution with the help of streamlit on heroku](https://recomendacaojogosb.herokuapp.com/).

6. After the first version i continued studying, learned the basics about k folds and Bayesian optimization and decided to try to apply it. [In this additional step, I created two more models, Random Forest and LightGBM, optimizing their hyperparameters with bayes](https://github.com/mattmagrin/game_recommendation_engine/blob/main/Extraction%20and%20modeling/5_bayesian_optimization_w_kfold.ipynb) to perform a more robust classification, and merged their results using an ensemble between them;

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
