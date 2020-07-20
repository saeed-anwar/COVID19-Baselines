
# COVID19 detection from Radiographs: Is Deep Learning able to handle the crisis?

This repository is for COVID19 detection from Radiographs introduced in the following paper

[Muhammad Saqib](https://www.uts.edu.au/staff/muhammad.saqib), [Saeed Anwar](https://saeed-anwar.github.io/), Abbas Anwar, Lars Petersson, Nabin Sharma, Michael Blumenstein,  "[COVID19 detection from Radiographs: Is Deep Learning able to handle the crisis?](https://www.preprints.org/manuscript/202006.0189/v1)
", preprint, 2020 

The models are built in PyTorch 1.5.1 and tested on Ubuntu 14.04/16.04 environment (Python3.8, CUDA10.2). 

## Contents
1. [Introduction](#introduction)
2. [Network](#network)
3. [Test](#test)
4. [Results](#results)
5. [Citation](#citation)

## Introduction
The COVID-19 is a highly contagious viral infection which played havoc on everyone's life in many different ways. According to the world health organization and scientists, more testing potentially helps governments and disease control organizations in containing the spread of the virus. The use of chest radiographs is one of the early screening tests to determine the onset of disease, as the infection affects the lungs severely. This study will investigate and automate the process of testing by using state-of-the-art CNN classifiers to detect the COVID19 infection. However, the viral could of many different types; therefore, we only regard for COVID19 while the other viral infection types are treated as non-COVID19 in the radiographs of various viral infections. The classification task is challenging due to the limited number of scans available for COVID19 and the minute variations in the viral infections. We aim to employ current state-of-the-art CNN architectures, compare their results, and determine whether deep learning algorithms can handle the crisis appropriately.

## Network
The network architectures and details are provided in our [paper](https://www.preprints.org/manuscript/202006.0189/v1)

## Test
### Quick start
1. Download the trained models of our paper.

    The models for CT-COVID can be downloaded from [Google Drive](https://drive.google.com/open?id=1QxO6KFOVxaYYiwxliwngxhw_xCtInSHd). The total size for zip is 4.96GB, which includes models, and images. Please cite the respective datasets.
    The models for Xray-COVID can be downloaded from [Google Drive](https://drive.google.com/open?id=1QxO6KFOVxaYYiwxliwngxhw_xCtInSHd). The total size for zip is 5.70GB, which includes models, and images. Please cite the respective datasets.

2. Cd to '/COVIDCT/CNN_methods' or '/COVIDXRAY/CNN_methods', then Cd in to the director of the method you want to test and run the following script.

    **You can use the following script to test the algorithms**

    ```bash
    bash predict_scripts.sh
    ```

## Results
**All the results for attention on the CT images can be downloaded from GoogleDrive from [here](https://drive.google.com/drive/folders/1f0gknwk16up7lrs58aebK351lg15TY2J?usp=sharing), the images of attention for Xray images from [here](https://drive.google.com/drive/folders/1f0gknwk16up7lrs58aebK351lg15TY2J?usp=sharing). The size of the results for CT-COVID19-Attention is about 400KB while for XRAY-COVID19-Attention is about 2.67MB** 

### Visual Results
Representative images of the COVIDCT dataset employed for training and evaluation of algorithms
<p align="center">
  <img width="500" src="https://github.com/saeed-anwar/COVID19-Baselines/blob/master/Figs/CT.png">
</p>

Following are the samples from the COVIDx dataset. The upper row shows the COVID19 infected examples, while the lower row presents
the infection-free images
<p align="center">
  <img width="500" src="https://github.com/saeed-anwar/COVID19-Baselines/blob/master/Figs/Xray.png">
</p>

Next, we present the models on infected and non-infected radiographs. In Figure below, we present the CT images with feature attention where the red color indicates the region where the models have focused. The first three rows contain COVID19 infections, while the remaining two rows in Figure are infection-free.
 
<p align="center">
  <img width="500" src="https://github.com/saeed-anwar/COVID19-Baselines/blob/master/Figs/CT-atten.png">
</p>

Next Figure shows four different COVID19 infection radiographs from four different orientations. ResNet, DenseNet, and GoogleNet presented in the second, third, and fourth columns focused on most of the chest radiographs while the remaining models concentrated on particular regions of the chest. It is challenging for the models to pinpoint exactly the artifacts caused by COVID19, as is obvious from the feature attention mechanism.

<p align="center">
  <img width="500" src="https://github.com/saeed-anwar/COVID19-Baselines/blob/master/Figs/xray-atten.png">
</p>

### Quantitative Results
<p align="center">
  <img width="500" src="https://github.com/saeed-anwar/COVID19-Baselines/blob/master/Figs/CT-atten.png">
</p>
The performance of state-of-the-art algorithms on widely used publicly available DnD dataset in terms of PSNR (in dB) and SSIM. The best results are highlighted in bold.

<p align="center">
  <img width="500" src="https://github.com/saeed-anwar/COVID19-Baselines/blob/master/Figs/xray-atten.png">
</p>

For more information, please refer to our [papar](https://www.preprints.org/manuscript/202006.0189/v1)

## Citation
If you find the code helpful in your resarch or work, please cite the following papers.
```
@article{Anwar2020COVID19Detect,
       title={COVID19 detection from Radiographs: Is Deep Learning able to handle the crisis?},
       author={Saqib, Muhammad and Anwar, Saeed and Anwar, Abbas and Petersson, Lars and Sharma, Nabin and Blumenstein, Michael},  
       journal={Preprints-2020060189},
       year={2020},
}
```
