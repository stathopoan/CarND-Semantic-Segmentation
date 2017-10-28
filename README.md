# Semantic Segmentation
### Introduction
The goal of this project is to identify safe drivable area on the road in pictures taken from a dashcam image using a Fully Convolutional Network (FCN).

### Architecture

![](https://i.imgur.com/spi1G1g.png)

The architecture is based on the paper [Fully Convolutional Networks for Semantic Segmentation](https://people.eecs.berkeley.edu/~jonlong/long_shelhamer_fcn.pdf "paper"). The FCN is composed of 2 parts:
 

- The encoder that is a series of convolutional layers from VGG16 network. The last convolutional layer was transformed by a 1x1 convolution to maintain spatial information. The goal of the encoder is to extract features from the image.
- The decoder that upscales the output of the encoder resulting in the same size as the original image and eventually in segmentation of each individual pixel in the original image. In this part skip connections has also been applied to enchance results.

### Training 

The training of the FCN has been achieved using AWS in a 3X4large instance on a GPU. The hyperparameters selected are:

learning rate: 0.0001

batch size: 7

epoches: 30

keep_prob: 0.3

### Results
 
The results are located in the `/runs` folder. Some sample images are displayed below:

![sample1](https://i.imgur.com/joE0hiC.png)
![sample2](https://i.imgur.com/56LjFUk.png)
![sample3](https://i.imgur.com/KNlPz5E.png)
![sample4](https://i.imgur.com/CPFoUMq.png)

## Setup
##### Frameworks and Packages
Make sure you have the following is installed:
 - [Python 3](https://www.python.org/)
 - [TensorFlow](https://www.tensorflow.org/)
 - [NumPy](http://www.numpy.org/)
 - [SciPy](https://www.scipy.org/)
##### Dataset
Download the [Kitti Road dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php) from [here](http://www.cvlibs.net/download.php?file=data_road.zip).  Extract the dataset in the `data` folder.  This will create the folder `data_road` with all the training a test images.

### Start
##### Implement
Implement the code in the `main.py` module indicated by the "TODO" comments.
The comments indicated with "OPTIONAL" tag are not required to complete.
##### Run
Run the following command to run the project:
```
python main.py
```
**Note** If running this in Jupyter Notebook system messages, such as those regarding test status, may appear in the terminal rather than the notebook.

### Submission
1. Ensure you've passed all the unit tests.
2. Ensure you pass all points on [the rubric](https://review.udacity.com/#!/rubrics/989/view).
3. Submit the following in a zip file.
 - `helper.py`
 - `main.py`
 - `project_tests.py`
 - Newest inference images from `runs` folder  (**all images from the most recent run**)
 

