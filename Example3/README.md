Regression - Predicting house prices

boston housing dataset from keras - 404 training , 102 test
The training data contains 13 different features:
    Per capita crime rate.
    The proportion of residential land zoned for lots over 25,000 square feet.
    The proportion of non-retail business acres per town.
    Charles River dummy variable (= 1 if tract bounds river; 0 otherwise).
    Nitric oxides concentration (parts per 10 million).
    The average number of rooms per dwelling.
    The proportion of owner-occupied units built before 1940.
    Weighted distances to five Boston employment centers.
    Index of accessibility to radial highways.
    Full-value property-tax rate per $10,000.
    Pupil-teacher ratio by town.
    1000 * (Bk - 0.63) ** 2 where Bk is the proportion of Black people by town.
    Percentage lower status of the population.
The training label is price of house (in thousands)

shuffle training set ( ? )

Normalize training set: Subtract mean, divide by standard deviation for each feature (test data is not used to calculate these, only training. Normalization makes training easier, less dependent on input unit used)

Model with sequential layers:
	- 2 hidden layers, densely connected. ReLU activation function for both
	- 1 output layer with 1 continuous value as output

Model trained using rmsprop: dividing gradient by running average of recent magnitude of gradient http://www.cs.toronto.edu/%7Etijmen/csc321/slides/lecture_slides_lec6.pdf

Model trained and accuracy, loss recorded in 'history' object

Accuracy, Loss visualized to stop training of model when progress stops
Add EarlyStopping to know when to stop training when a monitored quantity has stopped improving. https://www.tensorflow.org/api_docs/python/tf/keras/callbacks/EarlyStopping
(Training stops after nearly 140 epochs)

Plot predication values to check model

- Mean squared error used for regression problems
- evaluation metrics for regression different from classification (MAE)
- Scale each feature differently
- Use smaller network to avoid overfitting
- Use early stopping to prevent overfitting