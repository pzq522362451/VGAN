# VGAN

## The V-matrix based generative adversarial network (condtional)

Code accompanying the paper "VGAN: Generalizing MSE GAN and WGAN-GP for Robot Fault Diagnosis" by Ziqiang Pu, Diego Cabrera, Chuan Li and José Valente de Oliveira, *IEEE Intelligent Systems*, vol. 37, no. 3, pp. 65-75,2022. 
(Links: https://ieeexplore.ieee.org/abstract/document/9760080) 

-  Tensorflow 2.0 implementation
-  Inspired by Yang $et$ $al$. [Statistical Parametric Speech Synthesis Using Generative Adversarial Networks Under A Multi-task Learning Framework] (https://arxiv.org/pdf/1707.01670.pdf), the mean square error loss set as an additional regularization on GAN's loss.  
-  Vapnik $et$ $al$. [] (), the new thinking about the mean square error estimation. The cassical estimation is given by "" while with rethinking by Vapnik $et$ $al$, the about equation can be given by "" where V(i,j) can be expressed as "V(i,j)=\sum_{k=1}^{d}(c_{k}-max(x_{i}^{k},x{j}^{k}))"  
-  Yang $et$ $al$. [Statistical Parametric Speech Synthesis Using Generative Adversarial Networks Under A Multi-task Learning Framework] (https://arxiv.org/pdf/1707.01670.pdf), the mean square error loss set as an additional regularization on GAN's loss. 

-  This repository contains reprodce of several experiments mentioned in the paper
-  The VGAN was verified with the MNIST handwritting data set.
-  The implementation for WGAN using the MNIST dataset is shown in (https://github.com/MorvanZhou/mnistGANs)


## Requirements

- python 3.7.13
- Tensorflow == 2.8.2
- Numpy == 1.21.6
- Keras == 2.8.0

Note: All experiment were excecuted in Google colab with Tesla P100-PCIE-16GB GPU ![alt text](https://colab.research.google.com/assets/colab-badge.svg)


## File discription
* `--MSEGAN_MNIST`: GAN with additional regularization of MSE.
* `--VGAN_MNIST`: GAN with V-matrix regularization.
* `--WGAN_MNIST`: WGAN.
Note: all models are evaluate with MNIST data set.

## Implementation details
- The overall experiments are included in theses three '.ipynb' files. Directly using this file can get the results. Note that users should change the directory to successfully run this code.
- Hyperparameter settings: The learning rate for the generator is set to 2e-4, while for the discriminator is set to 1e-4. These were selected empirically after some preliminary tests. The Adam optimizer was used with key parameters b1=0.9 and b2=0.9999 in both the discriminator and the generator. A maximum number of ietration iterations is 20000.

## Usage
The script with `.ipynb` contains all the experiments (four scenarios: normal/normal_l/mse/mse_l/v/v_l).

## Model description
In this application, both the discriminator and the gen- erator are multilayer perceptrons with a fully connected topology. The topology of the generator is 64:1024:128 while that of the discriminator is 128:1024:2048:1. 

## Ackonwledgements
This work is supported in part by Portuguese funds through FCT—Foundation for Science and Technology, in part by I.P., through IDMEC, under LAETA Project UIDB/50022/2020, in part by the National Natural Sci- ence Foundation of China under Grant 52175080, in part by the Chongqing Natural Science Foundation under Grant cstc2019jcyj-zdxmX0013, in part by the Guangdong Basic and Applied Basic Research Foundation under Grant 2019B1515120095, and in part by the Intelligent Manufacturing PHM Innovation Team Program under Grant 2018KCXTD029. 
