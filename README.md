# Training-Neural-Nets---Guidelines
This article focusses on the problems that I faced during training of a recurrent neural network. Few of the problems are general for all the neural networks. 
PS - Keras with TensorFlow backend was used to code the RNN

# Let's get start 
# What batch size should be used to train the network?
    model.fit(load_train, y_train, batch_size=2048, nb_epoch=1000, verbose=1 , validation_split = 0.10)
    __Batch size is very small -__  
    Training the neural network takes long time
    very large - less time, more memory
    --- If batch size is too small - training error fluctuates A LOT!!




