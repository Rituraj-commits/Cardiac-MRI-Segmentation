# Cardiac MRI Segmentation using UNet

This repository contains code and results for segmentation performed on the Cardiac MRI dataset using UNet.

## Description

Cardiac MRI contains 30 3D Mono-modal MRI images of the left atrium. 2D patches are generated using ```medicaltorch```. 110 patches with shape ```(320,320)``` are generated and transformations are applied on the patches. The list of transformations applied on the training set:

* ```CentreCrop2D```
* ```Elastic Transformation```
* ```Random Affine```
* ```Normalization```

After applying these transformations Dataloader is created with batch size of ```16```. The UNet is then trained untill ```30 epochs``` with intial learning rate of ```0.001 ```and ```Cosine Annealing Scheduler```. Early stopping is also applied with patience of ```5``` to avoid overfitting.

## Getting Started

### Dependencies

* ```pytorch == 1.7.0```
* ```torchvision == 0.8.0```
* ```medicaltorch```

## Results
![Dice Loss](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/Dice_Loss.png)

![Accuracy](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/Training%20Accuracy.png)

## Segmentations

### Input Images
![](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/heart.png)   ![](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/heart2.png)   ![](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/heart3.png)   ![](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/heart4.png)

### Predictions
![](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/pred1.png)  ![](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/pred2.png)  ![](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/pred3.png)  ![](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/pred4.png)

### Ground Truth
![](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/gt1.png)  ![](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/gt2.png)  ![](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/gt3.png)  ![](https://github.com/Rituraj-commits/Cardiac-MRI-Segmentation/blob/main/image/gt4.png)



## Authors

[Rituraj Dutta](riturajdutta400@gmail.com)


## Acknowledgments


* [medicaltorch](https://github.com/perone/medicaltorch)
* [EarlyStopping](https://github.com/Bjarten/early-stopping-pytorch)
* [Dataset](http://medicaldecathlon.com/)
