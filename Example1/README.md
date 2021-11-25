Basic Classification
Classify 28x28 black and white pictures into 10 categories

pip install tensorflow
pip install matplotlib

Fashion MNIST dataset
accessible from tensorflow api
60k images to train, 10k to test

images: 28x28 between 0 and 255 - (use .shape to get size)
labels: int between 0 and 9 - (use len() for array size)

class names not in data, used later for plotting


Scale pixel values to between 0 and 1

first layer - flatten pixels into array of 784
second latyer - 128 neurons, ReLU function
third layer - 10 neurons, softmax layer (b/w 0 to 1)

Define loss function, metrics, optimizer (gradient ?)
model.fit() to train the model - epochs is a fancy word for throwing data at the computer
call model.predict() on test images to return list of lists of predictions (int b/w 0 and 9)
Use matplotlib to plot results