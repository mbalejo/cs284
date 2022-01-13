
# CS284 Mini-Project: Unconstrained Ear Recognition through SOTA Machine Learning Models: A Survey

#### Marwin B. Alejo - 2020-2022 | January 2022
This paper presented a preliminary result of the performance of selected known and new state-of-the-art machine learning networks on ear biometrics tasks. Provided a straightforward deep learning pipeline, this paper determined the performance of ResNets, ResNeXt, ViT and its known new variants, and ResMLP and MLP-Mixer for ear recognition. Results show that ResNets achieve optimal performance while Transformer-based, particularly the vanilla Vision Transformer, achieve greater performance over its variants and MLP-centric networks on ear recognition or biometrics.

## Deep Learning Pipeline
The deep learning pipeline of this paper consisted of four stages as shown in the image below.

![deep learning pipeline](https://github.com/mbalejo/CS284/blob/main/MiniProject/images/fig13.png)

## Tools and Library
1. Google Colab GPU
2. [PyTorch Image Model (TIMM)](https://github.com/rwightman/pytorch-image-models/tree/master/timm/models) 

## Raw EarVN1.0 Dataset may be downloaded from:
1. [Mendeley Data](https://data.mendeley.com/datasets/yws3v3mwx3/4) or
2. [Google Drive Folder](https://drive.google.com/drive/folders/1YzVIXU5WyfIWh3NMnhp4Mp9vNxk_CULy?usp=sharing)

## Processed EarVN1.0 Dataset (Trimmed and Partitioned into Train and Test) may be acquired from:
1. [Train folder](https://drive.google.com/drive/folders/1KWCf8URgn9RAhQ_sBEqZvM9G6ChkzCr2?usp=sharing)
2. [Test folder](https://drive.google.com/drive/folders/19vPcrdLYW7pddNxPO-ntYDzyovOkq-RE?usp=sharing)

## Notebook and Codes
The codes written in the following notebooks are straightforward when executed. Simply alter the Train path (location of training dataset), Test path (location of testing dataset), and Model path (location where trained models will be saved). Moreover, the Rough Notebook contain similar codes to the [first two notebooks below](https://colab.research.google.com/drive/1kJ4e52HmVwdEGbSk2QTn22ANNGcgly5X?usp=sharing) but contain execution results. These notebooks may be downloaded in the following links:
1. [Google Colab](https://colab.research.google.com/drive/1kJ4e52HmVwdEGbSk2QTn22ANNGcgly5X?usp=sharing)
2. [GitHub](https://github.com/mbalejo/CS284/blob/main/MiniProject/Unconstrained_Ear_Recognition_through_SOTA_Machine_Learning_Models_Marwin_Alejo_202020221.ipynb)
3. [Rough Notebook with Execution Results](https://colab.research.google.com/drive/141bKNrPtKnraKSpJXNjUvJjOG6Gpl3Ij?usp=sharing)

## Results
This paper trained the ear biometrics models on selected ResNet, ResNeXt, Transformer-based, and Transformer-inspired networks on 20 epochs with a batch size of 32, a learning rate of 0.00002, and the Adam optimizer. Considering the modeling constraints of this study, the fine-tuned ResNets of this paper took 16 minutes to 1.5 hours to develop an ear biometric model out of the EarVN1.0 dataset and achieved recognition rates of 79.57% for ResNet18, 81% for ResNet50, and 61.42% for ResNet152, and with a memory utilization of up to 2.40GB as shown in Table 2. It is observable from these ResNet results that ResNet50 is the most optimal ResNet network depth for the currently used ear biometrics dataset and configuration. It also implies that as the depth of ResNet becomes deeper than ResNet50, the network suffers from generalization loss thus, lowering the accuracy. Furthermore, the ResNeXt50 model also achieved a comparable result to ResNet18 in terms of recognition accuracy and ResNet50 in terms of memory utilization, implying that the inception-like block of ResNeXt allows the model to generalize further even on deeper network depth as compared with the standard ResNet block.

![](https://github.com/mbalejo/CS284/tree/main/MiniProject/images/fig15.png)

The fine-tuned Transformer-based models of this paper achieved greater recognition accuracy and lower memory utilization as compared with those of ResNets. The fine-tuned ViT of this paper achieved recognition accuracy of 97.36% with a memory utilization of 2.36GB although it took four hours of modeling. The DeiT, ConViT, and PiT achieved recognition accuracy of 95% to 97% with memory utilization of up to three gigabytes and took of up to four hours of modeling time. The XCiT, CaiT, Swin Transformer, and CrossViT achieved recognition accuracy of 75% to 89% with memory utilization of up to 2.8GB. Moreover, notable of these Transformer-based networks is the modeling time of XCiT, due to its XCA module that works like ConvNet, is on par with the performance of CNN-based models. Table 3 below shows the summary of the performance of these Transformer-based models.

![](https://github.com/mbalejo/CS284/tree/main/MiniProject/images/fig16.png)

The fine-tuned Transformer-inspired models of this paper achieved lesser recognition accuracy as compared with the ResNets and the Transformer-based models. The fine-tuned ResMLP12, ResMLP24, and ResMLP36 achieved recognition accuracy of up to 52% on 20 epochs with memory utilization of up to 2.3GB which is of equivalent to the memory used by XCiT, CaiT, Swin Transformer, and ViT. The fine-tuned MLP-Mixer model of this study achieved recognition accuracy of up to 40% with a memory utilization of 2.18GB. These results imply that these transformer-inspired networks suffer greatly in the task of Ear Biometrics considering the present configuration of the experiment. These results also mean that the statistics of the currently used ear datasets, as well as the data augmentation processes, do not suffice these models to generalize and generate on par results to Transformer-based models and ResNets. Table 4 shows the summary results of these Transformer-inspired models on Ear biometrics.

![](https://github.com/mbalejo/CS284/tree/main/MiniProject/images/fig17.png)
