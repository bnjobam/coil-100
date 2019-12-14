# coil100
 Detecting the angle at which an object has rotated
The data given are images of some small house items and toys. Detecting the
angle of rotation is quite difficult for the human eye so we want to see if the
computer can be of any help. From a subjective view, humans can detect rotation
if there are markers or positions they can track but 5 degree changes are quite
difficult. With markers, human familiar with the object maybe able to detect
angle of rotation with a 20 degree range.
One can not check rotation of an object without the original in mind, so in our
model we added the zero degree object to all the other objects of the same label.
The data is then partitioned and trained with CNN, transfer learn CNN, xgboost
and transfer learn xgboost while using dimension reduction technique of Principal
Component Analysis (PCA) and Grid search to get the best parameters.
From the folder 'plots and displays' we can see the performances of the trained
models. From there we chose the best models since the models: CNN for
classification and xgboost for regression since the other component for each of  
these models was too poor. The metric for regression used was Mean Square Error
(MSE) which guessing without learning was simply the variance.
With a 20 degree range, we got just 63 which is 6.3% but there were about 11
objects where rotation could not be detected even in the widest change with a
human eye (symmetric objects).
In the folder, 'plots and displays' we can see in the image 'Train data size
VS MSE' that with more data we could have better results. This will be done in
later updates, with this we will transform the data; random cropping, which can
generate a few more images for each training data point. Other methods of data
generation like rotation and reflection can not work due to the type of data we
have.
