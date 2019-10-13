# Gender-Classification
Calssifiying the gender of humans using Convolutional Neural Networks in Tensorflow using Keras API  

The project contains two different parts:  

### Train Classifier
In this part I trained a CNN on cropped faces of celebrities downloaded from google images and cropped.  
I used **2000** images (1000 in each class) for training and **200** images for validation set.  
I used the ``ImageDataGenerator`` class from **Keras** to load the images.  
The model achieves about **99%** Train accuracy and around **95%** validation accuracy.  
Then I used 20 images which are stored in **Test** folder to test the model.  
  
  
The data I used to train the model can be downloaded from this [link](https://github.com/arunponnusamy/gender-detection-keras/releases/download/v0.1/gender_dataset_face.zip "Download")  
  
  
  
### Classify From Detected
In this part I classified the gender of person in Un-cropped images.  
I used the ``detect_face()`` method from opencv to get the coordinates of the faces that are available in the image.  
Then I used my pre-trained model to classify the gender of each of the faces in the image.  
I drew a bounding box around the faces and labelled them using **CV2**.
The output images are displayed in the console using ``cv2.imshow()`` and also saved in the **output image** folder.
  
  Here is an example of the output files:  
  ![text](https://github.com/Neeraj-Prakash/Gender-Classification/blob/master/Classify%20from%20Detected/output%20image/gender_detection3.jpg "Example of bounding box and label")
  
