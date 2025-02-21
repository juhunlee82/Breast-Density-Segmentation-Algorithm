## What this repository offer
This repository is about breast density segmentation algorithms developed from my lab using deep convolutional networks on large mammogram dataset included full-field digital screening mammograms of 604 women, which included 1208 mediolateral oblique (MLO) and 1208 craniocaudal (CC) views from University of Pittsburgh Medical Center (UPMC).

The algorithm takes the size of 227 x 227 pixels of mammogram images as input and it returns the segmentation outcome with the size of 227 x 227 pixels.
The segmentation outcome consists of three channel, Red, Green, Blue indicate background, fatty, and dense tissue. 
As anatomical structure of CC and MLO view are different, we developed two models, one for CC-view and another MLO-view. 

The algorithm developed on MATLAB environment. We used SegNet architecture, trained on 1208 CC and 1208 MLO view of full-field digital screening mammograms of 604 women.

## How to use our algorithm
Download our weights available at: [Mammo-Dense-SegNet Weights]()

Load the network weight:
```matlab
load 
```
After having the Lesion simulator and Lesion Remover processed patches ready, 
```matlab
/Test_on_Mammograms/LS_LR_assisted_training.m
```
