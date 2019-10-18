# Gender-Classification
Calssifiying the gender of humans using Convolutional Neural Networks in Tensorflow using Keras API  
  
The project contains two different parts:  
  
### Train Classifier
In this part I trained a CNN on cropped faces of celebrities downloaded from google images.  
I used **2000** images (1000 in each class) for training and **200** images for validating the classifier.  
I used the ``ImageDataGenerator`` class from **Keras** to load the images.  
The model achieves about **99%** Train accuracy and around **95%** validation accuracy.  
Then I used 20 images which are stored in **Test** folder to test the model.  
  
  
The data I used to train the model can be downloaded from this [link](https://github.com/arunponnusamy/gender-detection-keras/releases/download/v0.1/gender_dataset_face.zip "Download")  
  
  
  
### Classify From Detected
In this part I classified the gender of person by using face detection from open-cv.  
It contains two files:  
1. Classify from image
2. Classify from cam  

#### Classify from image
I loaded the image and used the ``detect_face()`` method from opencv to get the coordinates of the faces that are available in the image.  
Then I used my pre-trained model to classify the gender of each of the faces in the image.  
I drew bounding box around the faces and labelled them using **CV2**.  
The output images are displayed in the console using ``cv2.imshow()`` and also saved in the **output image** folder.
  
  Here is an example of the output files:  
  
  [![gender-detection3.png](https://i.postimg.cc/bvkCkZJL/gender-detection3.png "Example of bounding box and label")](https://postimg.cc/bGY9jN12)  
    
    
#### Classify from cam
I loaded the pre-trained model for classification.  
Then I loaded the ``markFace()`` function from **"Classify_from_cam.ipynb"**.  
This function takes input as location of faces, image, model and returns an image with marked faces and labels.  
I got **frame by frame** video feed from my webcam using ``VideoCapture()`` from cv2.  
I detected faces from each face and passed them to the ``markFace()`` function along with model.  
Then I plotted each output of the function using ``cv.imshow()``.  
  
I got around **13 fps** output in the video. If you can help me improve the frame rate please let me know.  
  
Here is a demo of the output video:  
  
  ![example-video-from-cam.gif](https://github.com/Neeraj-Prakash/Gender-Classification/blob/master/Classify%20from%20Detected/example%20of%20video%20from%20cam.gif "Example Video from cam")
