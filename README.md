# Training-Neural-Nets---Guidelines
This article focusses on the problems that I faced during training of a recurrent neural network. Few of the problems are general for all the neural networks. 
PS - Keras with TensorFlow backend was used to code the RNN

## Table of contents
 
### What batch size should be used to train the network?
    model.fit(load_train, y_train, batch_size=2048, nb_epoch=1000, verbose=1 , validation_split = 0.10)
**Batch size is very small** - 
 1.  Training the neural network takes long time
 2.  The trained model may not be accurate enough
 3.  Training the network using small batch size requires less memory 
 4.  Training loss fluctuates a lot.
     ![picture alt](http://cs231n.github.io/assets/nn3/loss.jpeg "Fluctuations in training loss") 

**Batch size is very large** - 
 1.  Training the neural network takes long time
 2.  Training the network using large batch size requires more memory and if memory(less RAM) is a constraint then batch size must be small
 
 
   
    


