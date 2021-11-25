Text classification with movie reviews
Binary classification problem since 0 or 1 used as label to represent positive or negative review input

Download imdb dataset - top 10000 most frequent words only
25000 training entries and labels
train_data - array of integers representing words in dictionary, varying lenth of train_data

make key,value pairs for int-to-word using imdb.get_word_index, swap keys for values to get word from int, ignore reserved indices

1/ use one-hot encoding (num_words * num_words in space)
2/ pad arrays of test and training data using pad_sequences() to have same length arrays - 256 (num_words * max_length in space)
Q. Will the test data results be different for the two options?

Decisions to make:
how many layers
how many hidden units

input is 10,000 most frequent words as int

layers:
	embedding - represent words as vectors, semantically similar words have similar vectors. https://www.youtube.com/watch?v=Eku_pbZ3-Mw , https://projector.tensorflow.org/
	global average pooling ID - https://www.quora.com/What-is-global-average-pooling
	dense - applies weights, biases and the activation function which was passed as argument, dimension of output space also passed as argument, https://www.tensorflow.org/api_docs/python/tf/keras/layers/Dense

model.summary() useful to check layers set up correctly

more units, more layers may cause overfitting - unwanted patterns

Binary cross-entropy used as a loss function, it is generally better when dealing with probabilities

Create a validation set from training data (different from test data), used while training to check accuracy on data it hasnt seen before

Training:
	40 epochs, batch of 512 samples, loss and accuracy calculated from validation set

Test on test data

Create a graph of accuracy and loss over time (overfitting visible)