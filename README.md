
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
![Network](/Figs/Net.PNG)
The architecture of the proposed network. Different green colors of the conv layers denote different dilations while the smaller
size of the conv layer means the kernel is 1x1. The second row shows the architecture of each EAM.

<p align="center">
  <img width="500" src="https://github.com/saeed-anwar/RIDNet/blob/master/Figs/FeatureAtt.PNG">
</p>
The feature attention mechanism for selecting the essential features.


## Test
### Quick start
1. Download the trained models for our paper and place them in '/TestCode/experiment'.

    The real denoising model can be downloaded from [Google Drive](https://drive.google.com/open?id=1QxO6KFOVxaYYiwxliwngxhw_xCtInSHd) or [here](https://icedrive.net/0/e3Cb4ifYSl). The total size for all models is 5MB.

2. Cd to '/TestCode/code', run the following scripts.

    **You can use the following script to test the algorithm**

    ```bash
    #RIDNET
    CUDA_VISIBLE_DEVICES=0 python main.py --data_test MyImage --noise_g 1 --model RIDNET --n_feats 64 --pre_train ../experiment/ridnet.pt --test_only --save_results --save 'RIDNET_RNI15' --testpath ../LR/LRBI/ --testset RNI15
    ```


## Results
**All the results for RIDNET can be downloaded from GoogleDrive from [SSID](https://drive.google.com/open?id=15peD5EvQ5eQmd-YOtEZLd9_D4oQwWT9e), [RNI15](https://drive.google.com/open?id=1PqLHY6okpD8BRU5mig0wrg-Xhx3i-16C) and [DnD](https://noise.visinf.tu-darmstadt.de/submission-detail). The size of the results is 65MB** 

### Quantitative Results
<p align="center">
  <img width="500" src="https://github.com/saeed-anwar/RIDNet/blob/master/Figs/DnDTable.PNG">
</p>
The performance of state-of-the-art algorithms on widely used publicly available DnD dataset in terms of PSNR (in dB) and SSIM. The best results are highlighted in bold.

<p align="center">
  <img width="500" src="https://github.com/saeed-anwar/RIDNet/blob/master/Figs/SSIDTable.PNG">
</p>
The quantitative results (in PSNR (dB)) for the SSID and Nam datasets.. The best results are presented in bold.

For more information, please refer to our [papar](https://arxiv.org/abs/1904.07396)

### Visual Results
![Visual_PSNR_DnD1](/Figs/DnD.PNG)
A real noisy example from DND dataset for comparison of our method against the state-of-the-art algorithms.

![Visual_PSNR_DnD2](/Figs/DnD2.PNG)
![Visual_PSNR_Dnd3](/Figs/DnD3.PNG)
Comparison on more samples from DnD. The sharpness of the edges on the objects and textures restored by our method is the best.

<p align="center">
  <img width="500" src="https://github.com/saeed-anwar/RIDNet/blob/master/Figs/RNI15.PNG">
</p>
A real high noise example from RNI15 dataset. Our method is able to remove the noise in textured and smooth areas without introducing artifacts

<p align="center">
  <img width="500" src="https://github.com/saeed-anwar/RIDNet/blob/master/Figs/SSID.PNG">
</p>
A challenging example from SSID dataset. Our method can remove noise and restore true colors

![Visual_PSNR_SSIM_BI](/Figs/SSID3.PNG)
![Visual_PSNR_SSIM_BI](/Figs/SSID2.PNG)
Few more examples from SSID dataset.

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
