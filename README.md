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
	file = {Full Text PDF:/Users/juhunlee/Zotero/storage/QIGXQFQM/Lee and Nishikawa - 2018 - Automated mammographic breast density estimation u.pdf:application/pdf;Snapshot:/Users/juhunlee/Zotero/storage/ZE8SANY8/mp.html:text/html},
}
```
