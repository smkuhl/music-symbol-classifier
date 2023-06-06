# music-symbol-classifier


Oh no! Sir Jeffrey Bezos can’t read music. Instead of just simply teaching him how to read we must create a machine learning model to identify the handwritten musical symbols in our family’s top secret symphony that has been passed down through generations. 

As a musician, handwritten music is difficult to read and can often cause confusion. If we had a way to classify common symbols we could convert handwritten music into printed music for better readability and accessibility. 

The dataset we used was the Handwritten Online Musical Symbols (HOMUS) dataset that has 6,874 samples, 32 different symbols, collected from 100 different musicians. 

We used resources from these github repositories for our data:

https://github.com/apacha/MusicSymbolClassifier
https://github.com/jenaroaaugusto/HOMUS/tree/master/imagens

For our model, we used a similar technique to the bird species classifier example. First, we randomly split our data into training, validation, and test data based on a 70%, 15%, 15% split. Then we used the pretrained resnet model to train our model with our training data. The hyperparameters that worked best for us were 5 epochs with a learning rate of 0.01. After training our model, we used it to predict our validation and test data and printed their accuracies.

For our results, we ended up with a test accuracy of 94.28%. Our training loss decreased at an exponential decay, with the lowest loss getting down to 0.021.

The main challenges we ran into was adapting our example code to fit our dataset, and hyperparameter tuning the existing model in order to get the lowest loss without overfitting to the train data. 

One further step would be to tune our hyperparameters more to prevent overfitting. The difference in accuracy between our train and test accuracy suggests that we might be overfitting to our train data since our loss when loss was so small. Another next step would be to expand our dataset. The original HOMUS dataset was 15,200 images,  however the pre-generated image dataset we used was only 6,874 images. To get better results we could generate the HOMUS dataset ourselves and retrain our model on this larger dataset. 

One way our approach differed, was that we used a validation and a test set. This allowed us to do more hyperparameter tuning on the validation set. That way we only ran the test set once, meaning our test accuracy is a more accurate representation of how our model would perform on new data. 
