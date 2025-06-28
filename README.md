# Image Segmentation with U-Net in TensorFlow

This repository contains my implementation of the U-Net model for semantic image segmentation using TensorFlow and Keras. The project focuses on a common task in computer vision—predicting a class label for every pixel in an image—particularly relevant for autonomous driving applications

The model is trained on the CARLA self-driving car dataset to segment key scene elements such as roads, vehicles, pedestrians, and signs

## Key Features

- U-Net architecture built from scratch using TensorFlow and Keras
- Encoder-decoder structure with skip connections for precise localization
- Pixel-wise multi-class classification using Sparse Categorical Crossentropy loss
- Custom data pipeline built with `tf.data.Dataset`
- Visualization of model predictions against ground truth

## Model Architecture

The U-Net architecture is composed of two main parts:

**Contracting Path (Encoder)**  
This section follows a standard convolutional architecture, using repeated blocks of convolution and max pooling layers to downsample the image and extract high-level features. The number of feature channels increases at each downsampling level

**Expansive Path (Decoder)**  
This section upsamples the feature maps using transposed convolutions, concatenates them with the corresponding encoder features via skip connections, and applies further convolution layers to refine the predictions

Skip connections help preserve spatial details lost during downsampling by merging encoder features with decoder layers at the same level

## Results

The model is capable of producing accurate pixel-level segmentation maps for images from the CARLA dataset. It classifies each pixel into categories such as road, vehicle, and pedestrian, enabling scene understanding for tasks like self-driving

## Source & Acknowledgements

This project is based on a programming assignment from Course 5: Sequence Models in the  
[DeepLearning.AI Deep Learning Specialization](https://www.coursera.org/specializations/deep-learning) on Coursera

All credit for the original problem statement, dataset, and instructional framework goes to DeepLearning.AI and the course instructors

---

> A hands-on deep learning project demonstrating the power of U-Net architecture in solving real-world image segmentation tasks
