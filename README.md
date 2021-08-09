# Cardiac MRI Segmentation using UNet

This repository contains code and results for segmentation performed on the Cardiac MRI dataset using UNet.

## Description

Cardiac MRI contains 30 3D Mono-modal MRI images of the left atrium. 2D patches are generated using ```medicaltorch```. 110 patches with shape (320,320) are generated and transformations are applied on the patches. THe list of transformations applied on the training set:

* CentreCrop2D
* Elastic Transformation
* Random Affine
* Normalization

After applying these transformations Dataloader is created with batch size of 16. The UNet is then trained untill 30 epochs with intial learning rate of 0.001 and Cosine Annealing Scheduler. Early stopping is also applied with patience of 5 to avoid overfitting.

## Getting Started

### Dependencies

* ```pytorch == 1.7.0```
* ```torchvision == 0.8.0```
* ```medicaltorch```

## Authors

[Rituraj Dutta](riturajdutta400@gmail.com)


## Acknowledgments


* [medicaltorch](https://github.com/perone/medicaltorch)
* [EarlyStopping](https://github.com/Bjarten/early-stopping-pytorch)
* [Dataset](http://medicaldecathlon.com/)
