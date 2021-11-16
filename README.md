# Experiment to improve the faulty steel classification

Experiments with Pytorch-based Model that classified Steel plate faults into 7 types using 27 features

## Data

[Kaggle Faulty STeel Plates Data](https://www.kaggle.com/uciml/faulty-steel-plates) / .csv format

Preview head 5 features in 27 features

| Y_Perimeter	| Sum_of_Luminosity	| Minimum_of_Luminosity	| Maximum_of_Luminosity	| Length_of_Conveyer |
|:---:|:---:|:---:|:---:|:---:|
| 44 | 24220 | 76 | 108 | 1687 |

## Experiments Category

- Activation Function : **Sigmoid**, **Tanh** / **ReLU**, **Swish**
- Weight Initialization : **Random**, **Xavier**(+Sigmoid), **He**(+ReLU)
- Optimization : **SGD**, **Momentum**, **AdaGrad**, **RMSProp**, **Adam**(Momentum + RMSProp)
- Overfitting Prevention : **Batch Normalization**, **Drotout**, **L2-Regularization**(Weight Decay)

## Experimental Results

**Hyphter Parameter Setting**

Epoch = 1200, Learning Rate = lr, Batch Size = 128, Hidden Layer Neuron = 20, Input Size = 27, Output Size = 7

Train Data : Test Data = 1600 : 300, Totla Data = 1900

> Hidden Layer의 크기를 정함에 있어서 가장 흔하게 신뢰되어 지는 것은, 'Hidden Layer의 최적의 크기는 보통 Input과 Output Layer의 크기 사이이다'


| Network | Activation<br>Function | Weight<br>Initialzation | Optimization | Overfitting<br>Prevention | Train Acc<br>Test Acc | Code |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| 2 Layer | Sigmoid | Random / std=0.01 | SGD / lr=0.01 | . | 0.3906<br>0.3958 | . |
| 2 Layer | Sigmoid | Random / std=0.01 | SGD / lr=0.01 | Batch Normalization | 0.5112<br>0.4692 | . |
| 2 Layer | Sigmoid | He | SGD / lr=0.01 | Batch Normalization | 0.51<br>0.5190 | . |
| 2 Layer | Sigmoid | Xavier | SGD / lr=0.01 | Batch Normalization | 0.5031<br>0.5395 | . |
| 2 Layer | Sigmoid | Xavier | Adam / lr=0.001 | Batch Normalization | **0.5731**<br>0.3049 | . |
| 2 Layer | Sigmoid | Xavier | Adam / lr=0.001 | Batch Normalization<br>Drouput ratio=0.15| 0.56<br>0.5571 | . |
| 2 Layer | Sigmoid | Xavier | AdaGrad / lr=0.01 | Batch Normalization | 0.5512<br>**0.5747** | . |
| 3 Layer | Sigmoid | Xavier | SGD / lr=0.01 | Batch Normalization | 0.5056<br>0.4750 | . |
| 2 Layer | ReLU | He | SGD / lr=0.01 | Batch Normalization | 0.5143<br>0.4985 | . |
| 2 Layer | ReLU | He | Adam / lr=0.001 | Batch Normalization | 0.5681<br>0.5131 | . |
| 2 Layer | ReLU | Xavier | Adam / lr=0.001 | Batch Normalization | **0.585**<br>0.5601 | . |
| 3 Layer | ReLU | He | SGD / lr=0.01 | Batch Normalization | 0.5131<br>0.5425 | . |
