
# Team Data
This is the page created for the MLCAS 2021 Crop Yeild Prediction challenge and for the midterm for BE 429 at the University of Arizona.

## Contributors
Cesar Perez<br>
Luis Flores Lozano<br>
Austin Connick<br>
Travis Myers<br>
Raul Manquero-Ochoa

# Description of the project
Given whether data from 150 locations during the growing season (a period of 30 weeks) over a 13 year study , we are goring to buld a model consisting
of 103,365 performance records, we are building a model to predict yearly crop yeild accurately for a specific performance record. The challenge is provided as it has a widespread of applications in plant breeding, crop science research, and agricultural production (as per the website[^1])

## Planning and Obstacles
We approached this challenge first looking at the data and understanding what it represented and what we needed to use in order to get this model working. After cleaning and organizing the data, we identified what needed to be used for the model's predictions. Once the data was configured to the variables we were using, that is how we would then build and train the model. Easier said than done. Some of the biggest obstacles that our group faced was that we had no experience in building or training models, as well as trying to understand and gather what we needed from the dataset to train the model. Technology also was a challenge as the HPC kernels were creashing due to the size of the files. After figuring out the bugs and overcoming obstacles, we trained the model and made sure it ran locally. So after we confirmed that, we would transfer it over to the HPC sto run the complete dataset.

## Explaining the Model
Part of the challenge was to figure out what was going to be used in our model given the dataset. We approched it by first working on a small sample from the whole population in order to know what the desired results were before moving on to the entire dataset. The model we utilized was a Decision Tree Regressor. It is given a record and based off of the record it should have possible outcomes for it. We built a Decision Tree Regessor for each day given in the dataset and then made an input for the given condition on that day. We finally took the mean to get a prediciton given the 214 days for each entry. This is how we utilized the regressor: 
`...
 model = DecisionTreeRegressor()`<br>
 `model.fit(x_train, y_train)`<br>
 `predictions = model.predict(x_train)`<br>
 `predictions = model.predict(x_test)` <br>
 `x_train = pd.DataFrame(x_train)` <br>
 `y_train = pd.DataFrame(y_train)`
 `...`

###### Footnotes
[^1]: https://eval.ai/web/challenges/challenge-page/1251/overview
