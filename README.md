# Training-Neural-Nets---Guidelines
This article focusses on the problems that I faced during training of a recurrent neural network. Few of the problems are general for all the neural networks. 
PS - Keras with TensorFlow backend was used to code the RNN

## Table of contents
 
## What batch size should be used to train the network?
     model.fit(load_train, y_train, batch_size=2048, nb_epoch=1000, verbose=1 , validation_split = 0.10)
**Batch size is very small** - 
 1.  Training the neural network takes long time
 2.  The trained model may not be accurate enough
 3.  Training the network using small batch size requires less memory 
 4.  Training loss fluctuates a lot.
     As shown in image below : ![picture alt](http://cs231n.github.io/assets/nn3/loss.jpeg "Fluctuations in training loss") 

**Batch size is very large** - 
 1.  Training the neural network takes long time
 2.  Training the network using large batch size requires more memory and if memory(less RAM) is a constraint then batch size must be small
 
## Interpreting training and validation loss
The training and validation loss for each epoch can be obtained and plotted as shown below -

     hist = model.fit(load_train, y_train, batch_size=2048, nb_epoch=1000, verbose=1 , validation_split = 0.10)
     y = hist.history
     plt.plot(x , y['loss'] , label = 'TRAINING LOSS')
     plt.xlabel('iterations')
     plt.hold(1)
     plt.plot(x , y['val_loss'] , label = 'VALIDATION LOSS')
     plt.legend(loc = 'upper left')
     plt.show()
     
** Training loss <<< Validation loss indicates overfitting **
 1. Model has learnt noise in the data or has learnt some features which ain't in the validation set. 
 2. Decrease your network size OR add dropout layer OR increase dropout value. 
 3. If training data and validation data belong to different distributions or have different features, increase or decrease the  validation split to have similar training and validation sets.
      
** Training loss >>> Validation loss --- underfitting **
 1. Model has learnt features limited to the validation data only and hence performs better on the validation dataset.
 2. Increase the size of your model (either number of layers or the raw number of neurons per layer)
 3. Changing the validation set may help in some scenarios.


     
     

 
   
    


