# Experiment to improve the faulty steel classification

Experiments with Pytorch-based Model that classified Steel plate faults into 7 types using 27 features

## Data

[Kaggle Faulty STeel Plates Data](https://www.kaggle.com/uciml/faulty-steel-plates) / .csv format

Preview head 5 features in 27 features

| Y_Perimeter	| Sum_of_Luminosity	| Minimum_of_Luminosity	| Maximum_of_Luminosity	| Length_of_Conveyer |
|:---:|:---:|:---:|:---:|:---:|
| 44 | 24220 | 76 | 108 | 1687 |

Y_Perimeter	Sum_of_Luminosity	Minimum_of_Luminosity	Maximum_of_Luminosity	Length_of_Conveyer	TypeOfSteel_A300	TypeOfSteel_A400	Steel_Plate_Thickness	Edges_Index	Empty_Index	Square_Index	Outside_X_Index	Edges_X_Index	Edges_Y_Index	Outside_Global_Index	LogOfAreas	Log_X_Index	Log_Y_Index	Orientation_Index	Luminosity_Index	SigmoidOfAreas

## Experiments

- Optimization : **SGD**, **Momentum**, **AdaGrad**, **RMSProp**, **Adam**(Momentum + RMSProp)
- Weight Initialization : **Random**, **Xavier**(+Sigmoid), **He**(+ReLU)
- Activation Function : **Sigmoid**, **Tanh**, **ReLU**,
