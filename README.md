# Clash Royale Player Trophy Prediction
<img src="https://1000logos.net/wp-content/uploads/2021/04/Clash-Royale-logo.png" alt="Clash Logo" width="50%">

## Goal ##
Predict a player's trophy count based on player data such as cards, achievements, badges, total games, total donations, etc. 

## Resources ##
[Clash Royale API](https://developer.clashroyale.com/#/) : Player data for approximately 10,000 random players was pulled from the Clash Royale API. 

## Analysis ##
### Initial Data Exploration ### 
* Clash Royale removed their API endpoint listing all player tags, so a list of random player tags was generated and used to request player data from the Clash Royale API.
* All JSON files containing player data were then combined and normalized.

### Databases ### 
* Separate dataframes were created for the following columns, using player tag as the primary key:

  * Achievements
  * Arena
  * Badges
  * Cards 
  * Best Path of Legend Season Result
  * Current Path of Legend Season Result
  * Last Path of Legend Season Result
* The dataframes were then exported to CSVs.

### Machine Learning ###
* Sklearn's RandomForestRegressor was used to train and test three models. 70% of the data was allocated to training, while 30% was for testing.
  * __Model 1:__ n_estimators = 100, random_state = 42 
  * __Model 2:__ n_estimators = 150, random_state = 42 
  * __Model 3:__ n_estimators = 50, random_state = 42 

### Results ###
* __Model 1:__
  * Mean Squared Error: 9850.06
  * R-squared: 0.9978
* __Model 2:__
  * Mean Squared Error: 9910.42
  * R-squared: 0.9978
* __Model 3:__
  * Mean Squared Error: 10152.49
  * R-squared: 0.9977

### Next Steps ###
* Increase processing power and time.
* Perform cross-validation to estimate the models performance and predictive power. 
* Examine feature importance scores to identify the most influential features and underlying relationships in the data.
* Run the model using RandomizedSearchCV with parameters.
* Run the model using GridSearchCV and even more parameters.
  
## References ##
Clash Royale API (2024). Supercell. [https://api.clashroyale.com/v1/players/{}]

