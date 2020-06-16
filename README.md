# Gesture-Recognition-Model-for-Smart-TV


Problem Statement
The problem statement is for the data scientist who is working at a home electronics company. He has been asked to develop a cool feature in the smart-TV that can recognise five different gestures performed by the user which will help users control the TV without using a remote.

The gestures are continuously monitored by the webcam mounted on the TV. 
Each gesture corresponds to a specific command:

Thumbs up:  Increase the volume
Thumbs down: Decrease the volume
Left swipe: 'Jump' backwards 10 seconds
Right swipe: 'Jump' forward 10 seconds  
Stop: Pause the movie

The task for the data scientist is to train a model on the 'train' folder (i.e. Training Data) which performs well on the 'val' folder (i.e. Validation Data) as well.

Dataset Information:

The training and validation data consists of a few hundred videos categorised into one of the five classes. Each video (typically 2-3 seconds long) is divided into a sequence of 30 frames(images). All images in a particular video subfolder have the same dimensions but different videos may have different dimensions. 
The videos have two types of dimensions - either 360x360 or 120x160
The data is provided in a zip file. The zip file contains a 'train' and a 'val' folder with two CSV files for the two folders. These folders are in turn divided into subfolders where each subfolder represents a video of a particular gesture. 
Each row of the CSV file represents one video and contains three main pieces of information - the name of the subfolder containing the 30 images of the video, the name of the gesture and the numeric label (between 0-4) of the video.


Approach: 
In this case study I have tried different experiments with different models that we tried to generate. The experimentation is based on tuning different hyperparameters like batch size,number of epochs,image size etc. Given below is a summary table of all models generated and their metrics along with the explanation/remarks. 


Both the .h5 files are also available on google drive link below:

model-00023-0.06841-0.98962-0.32275-0.91667.h5 : https://drive.google.com/open?id=1N5nmzW6bzbVtClFT2S5azw1ucOUQpwTq
model-00039-0.43407-0.86851-0.64222-0.81667.h5 : https://drive.google.com/open?id=1VIIWEaz063OEk_xQrHWhr_G-HAPEcUY

CNN-3D:

The first model gave me training accuracy as 98% and validation accuracy 95% with different values and tune up the hyper parameters as explained in the table above. (see Model 4 results in summary document.)
In this model we have - 
four convolutional layers followed by
two dense layers followed by
softmax layer
In the first three convolutional layers I have used Max pooling layer with pool size of (2,2,2)
Batch normalization is used with every layer in this model. 
Dropouts are used with the dense layers only.
I have used Adam optimizer in this model. Adam is an optimization algorithm for stochastic gradient descent for training deep learning models. It combines the best properties of the AdaGrad and RMSProp algorithms to provide an optimization algorithm that can handle sparse gradients.

CNN -RNN:

This model gave me a training accuracy as 87% and validation accuracy 82% with different values and tune up the hyper parameters as explained in the table above. (see Model 7 results). 
In this model I have - 
four convolutional layers followed by
flatten layers followed by
LSTM followed by
dense layer followed by
softmax layer
In the first three convolutional layers I have used Max pooling layer with pool size of (2,2,2)
Batch normalization is used with every convolution layer in this model. 
Dropouts are used with the LSTM  & dense layers only.
I have used Adam optimizer in this model. Adam is an optimization algorithm for stochastic gradient descent for training deep learning models. It combines the best properties of the AdaGrad and RMSProp algorithms to provide an optimization algorithm that can handle sparse gradients.
