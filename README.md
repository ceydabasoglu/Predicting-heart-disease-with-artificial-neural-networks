# Predicting-heart-disease-with-artificial-neural-networks

In this project, I developed an artificial neural network model for heart disease diagnosis. My goal is to optimize the model's hyperparameters to achieve the best performance.

The create_model function constructs a Keras model with various hyperparameters (optimizer, weight initialization). The model consists of three layers:

First layer: 16 neurons, ReLU activation function, and 50% dropout
Second layer: 32 neurons, ReLU activation function, and 50% dropout
Output layer: 1 neuron, sigmoid activation function (for binary classification)
The model is compiled with a binary cross-entropy loss function and various optimizer options (adam, SGD, RMSprop).

Early stopping halts the training process if the validation loss (val_loss) does not improve, helping to prevent overfitting. Model checkpoints save the model to 'best_model.h5' when the validation loss is at its lowest.

We create a grid for hyperparameter search, including batch size, number of epochs, optimizer type, and weight initialization strategies.

The hyperparameter_search function tries all parameter combinations to find the model with the best validation loss. It trains the model for each combination and saves the one with the lowest validation loss.

By running the hyperparameter search function, we identify the best parameters. Using these parameters, we recreate the model and evaluate training results based on validation loss.

We then build a new model with the best parameters and load the previously saved best weights. This ensures we achieve the best performance encountered during the training process.

I evaluated my model on the test set and analyzed its performance using metrics such as accuracy, confusion matrix, and classification report.
