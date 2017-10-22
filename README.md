# Feature extraction using Viola Jones Face detection Algorithm and OpenCV2

We can modify the Viola Jones Algorithm within a python script to scan for all the face-like portions of an image - 

Whether it is a single face in an image 

![](https://github.com/tomtillo/FaceDetection/blob/master/orig_image_24.jpg)

Or a group of faces
![](https://github.com/tomtillo/FaceDetection/blob/master/orig_image_631_local_input.jpg)


## Understanding the order in which faces are detected
The following gif image shows the order in which images are detected. ( From left to right and from top to bottom )

![](https://github.com/tomtillo/FaceDetection/blob/master/cropped_group_face.gif)

But if you observe closely, there are some faces that are read after the first pass is done.

## Detecting if the image is a closeup
1. Compare the area occupied by the face in the image to that of the original image ( get the ratio or apply any other metric - like the height of face to height of image)
2. Apply heuristics based on several training images - after manually classifying those training images  ( eg: use a multi-nomial logistic regression model to predict based on features like 
* height of area bound by face 
* area of rectangle outlining the face 
* height or area of original image
* number of faces detected

Challenges 
1. Some faces do not get recognized ( see the image above - the face at the bottom right was not successfully detected )

