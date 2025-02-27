## What this repository offer
This repository is about breast density segmentation algorithms developed from my lab using deep convolutional networks on large mammogram dataset included full-field digital screening mammograms of 604 women, which included 1208 mediolateral oblique (MLO) and 1208 craniocaudal (CC) views from University of Pittsburgh Medical Center (UPMC).

The algorithm takes the size of 227 x 227 pixels of mammogram images as input and it returns the segmentation outcome with the size of 227 x 227 pixels.
The segmentation outcome consists of three channel, Red, Green, Blue indicate background, fatty, and dense tissue. 
As anatomical structure of CC and MLO view are different, we developed two models, one for CC-view and another MLO-view. 

For CC-view, it segments dense, fatty, and background. It removes any additional tissue (e.g., belly, axilar), if they are visible in the mammogramm.
The below figure shows the input CC-view and its outcome from our segmentation algorithm.
<p align="center">
<img src="https://github.com/user-attachments/assets/3a704acd-57b1-4862-b30a-c0a4a7528113" width="50%" \>
  <figcaption> Figure 1. Image input, CC-view (left) and its outcome (right) after applying our algorithm.</figcaption>
</p>

For MLO-view, it segments dense, fatty, and background. It removes pectoral muscle and any additional tissue not belong to breast.
The below figure shows the input MLO-view and its outcome from our segmentation algorithm.
<p align="center">
<img src="https://github.com/user-attachments/assets/d6ac5e82-7df0-48d1-bcb6-e8c5aaba9005" width="50%" \>

  <figcaption> Figure 2. Image input, MLO-view (left) and its outcome (right) after applying our algorithm.</figcaption>
</p>

The algorithm developed on MATLAB environment. We used SegNet architecture, trained on 1208 CC and 1208 MLO view of full-field digital screening mammograms of 604 women.

**Currently, the algorithm only works on "For presentation" view of Hologic screening digital mammograms.**

We are continuously working on improving the algorithm. Improved algorithm with better architectures, making it work on synthetic mammograms and non-Hologic images will be available in this repository in the future.
## How to use our algorithm
Download our weights available at: [Mammo-Dense-SegNet Weights](https://drive.google.com/file/d/1iEz8bJjITJo68QC6Pko2ivjQ7zXHSCuD/view?usp=drive_link)

Extract mammogram images from DICOM. For matlab, use dicomread function.
```matlab
dicomimg = dicomread([DICOM File]);
```
Convert dicomimg to 8 bit image using min-max normalization. For matlab, use mat2gray function.
```matlab
img = mat2gray(dicomimg);
```
After that, load the network weight, a target mammogram image, and then apply it using MATLAB function semnaticseg:
```matlab
%% CC view
load SegNet_227x227_CC_v2_e10.mat; % CC view model
img = imread('mammogram_test_CC.jpg');
img = imresize(img,[227 227]);
[~,~,segimg] = semanticseg(img,net); $
% display the segmentation result
figure(1);
subplot(121); imshow(img);
subplot(122); imshow(segimg);
%% MLO view
load SegNet_227x227_MLO_v2_e10.mat; % MLO view model
img = imread('mammogram_test_MLO.png');
img = imresize(img,[227 227]);
[~,~,segimg] = semanticseg(img,net);
% display the segmentation result
figure(2);
subplot(121); imshow(img);
subplot(122); imshow(segimg);
```
<p align="center">
<img src="https://github.com/user-attachments/assets/d0ea4167-ea2b-43e9-9591-b8a00fe10710" width="100%" \>

  <figcaption> Figure 3. Input and Output from the above example.</figcaption>
</p>

## Citation
If you use this code for your research, please cite our papers.
```
@article{lee_automated_2018,
	title = {Automated mammographic breast density estimation using a fully convolutional network},
	volume = {45},
	copyright = {© 2018 American Association of Physicists in Medicine},
	issn = {2473-4209},
	url = {https://aapm.onlinelibrary.wiley.com/doi/abs/10.1002/mp.12763},
	doi = {10.1002/mp.12763},
	language = {en},
	number = {3},
	urldate = {2018-10-18},
	journal = {Medical Physics},
	author = {Lee, Juhun and Nishikawa, Robert M},
	month = mar,
	year = {2018},
	keywords = {segmentation, breast density, mammography, deep learning},
	pages = {1178--1190},
}
```
