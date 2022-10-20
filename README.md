# VGAN

## The V-matrix based generative adversarial network (condtional)

Code accompanying the paper "VGAN: Generalizing MSE GAN and WGAN-GP for Robot Fault Diagnosis" by Ziqiang Pu, Diego Cabrera, Chuan Li and José Valente de Oliveira, *IEEE Intelligent Systems*, vol. 37, no. 3, pp. 65-75,2022. 
(Links: https://ieeexplore.ieee.org/abstract/document/9760080) 


-  Tensorflow 2.0 implementation
-  Inspired by Yang $et$ $al$. [Statistical Parametric Speech Synthesis Using Generative Adversarial Networks Under A Multi-task Learning Framework] (https://arxiv.org/pdf/1707.01670.pdf), the mean square error loss set as an additional regularization on GAN's loss. 
-  
-  Vapnik $et$ $al$. [] (), the new thinking about the mean square error estimation. The cassical estimation is given by "" while with rethinking by Vapnik $et$ $al$, the about equation can be given by "" where V(i,j) can be expressed as "V(i,j)=\sum_{k=1}^{d}(c_{k}-max(x_{i}^{k},x{j}^{k}))"  
-  
-  
-  
-  Yang $et$ $al$. [Statistical Parametric Speech Synthesis Using Generative Adversarial Networks Under A Multi-task Learning Framework] (https://arxiv.org/pdf/1707.01670.pdf), the mean square error loss set as an additional regularization on GAN's loss. 


-  The code for SWD is shown in (https://github.com/ishansd/swg).
-  This repository contains reprodce of several experiments mentioned in the paper
-  Both unconditional and conditional SW-CycleGAN were verified with the MNIST handwritting dataset.
-  The implementation for CycleGAN using the MNIST dataset is shown in (https://github.com/MorvanZhou/mnistGANs)


## Requirements

- python 3.7.13
- Tensorflow == 2.8.2
- Numpy == 1.21.6
- Keras == 2.8.0

Note: All experiment were excecuted in Google colab with Tesla P100-PCIE-16GB GPU ![alt text](https://colab.research.google.com/assets/colab-badge.svg)


## File discription
* `--CycleGAN`: THe model we build the CycleGAN. It is a class and based on Keras.
* `--GAN_Utils`: Functions about how to save the model and how to produce synthetic examples.
* `--InstanceNormalization`: Instance Normalization implemetation based on Keras
* `--NN_Utils`:Build model structures include squeeze-and-excitation mechanism, CNN, ResNet, Modified ResNet, the discriminator and 

## Implementation details
- The overall experiments include swd,wd,swd-sem and wd-sem are included in Run Main.ipynb. Directly using this file can get the results. Note that users should change the directory to successfully run this code.
- Hyperparameter settings: The learning rate for the generator is set to 2e-4, while for the discriminator is set to 1e-4. These were selected empirically after some preliminary tests. The Adam optimizer was used with key parameters b1 1⁄4 0:9 and b2 1⁄4 0:9999 in both the discriminator and the generator. A maximum number of K 1⁄4 20; 000 iterations was considered. The V-matrix regularization coefficient g is discussed in the following.  

## Usage
The script with `.ipynb` contains all the experiments (four scenarios: normal/normal_l/mse/mse_l/v/v_l).

## Model description
In this application, both the discriminator and the gen- erator are multilayer perceptrons with a fully con- nected topology. The topology of the generator is 64:1024:128 while that of the discriminator is 128:1024:2048:1. 
## Results on conditional CycleGAN
### t-SNE

<div align=center>
  
|   | wd|swd|
| ------------- | ------------- |------------- |
| t-SNE| <img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/tsne_wd.png" width="320" height="320">|<img src="https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/tsne_swd.png" width="320" height="320"> |

</div>


### MNIST visualization 

The results with swd is shown bellow:
![image](https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/swd.png)

The results with wd is shown bellow:
![image](https://github.com/pzq522362451/SW-CycleGAN/blob/main/Results/wd.png)

### Learning curve

## Ackonwledgements
This work is supported in part by Portuguese funds through FCT—Foundation for Science and Technology, in part by I.P., through IDMEC, under LAETA Project UIDB/50022/2020, in part by the National Natural Sci- ence Foundation of China under Grant 52175080, in part by the Chongqing Natural Science Foundation under Grant cstc2019jcyj-zdxmX0013, in part by the Guangdong Basic and Applied Basic Research Foundation under Grant 2019B1515120095, and in part by the Intelligent Manufacturing PHM Innovation Team Program under Grant 2018KCXTD029. This work has been carried out under the High Performance Computing Chair—a R&D infrastructure based at the University of Evora, endorsed by Hewlett Packard Enterprise (HPE), and involving a consortium of higher education institutions (University of Algarve, University of Evora, New University of Lisbon, and University of Porto), research centers (CIAC, CIDE- HUS, and CHRC), enterprises (HPE, ANIET, ASSIMAGRA, Cluster Portugal Mineral Resources, DECSIS, FastComp- Chem, GeoSense, GEOtek, Health Tech, and Starkdata), and public/private organizations (Alentejo Tourism-ERT and KIPT CoLab).
