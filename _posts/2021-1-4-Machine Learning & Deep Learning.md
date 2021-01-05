---
title: Machine Learning & Deep Learning
format: post
tags:
  - Machine Learning
  - Deep Learning
---



# Machine Learning & Deep Learning

Inspired by two papers recently, I want to implement ML/DL into GW waveform hyperparameter estimation. Before start doing so, let's have a quick walk through of what is Machine Learning and Deep Learning.

## Types

- According to catagory
  - supervised learning
  - unsupervised learning
  - semi-supervised learning
  - enhance learning
- According to task
  - classification
  - regression
  - cluster
  - dimensionality reduction

## Useful packages and libraries

- Traditional ML
  - Scikit-learn
  - AstoML
- Deep Learning frame
  - Tensorflow
  - PyTorch
  - Keras
  - etc
- Other useful ML/DL tools
  - numpy
  - pandas
  - matplotlib
  - seaborn
  - etc

## Supervised learning protocol 

1. Data preparation
2. Feature engineering
3. Model selection
4. Model training 
5. Model evaluation and optimization
6. Deploy your model

Among all of these steps, first step is the most important, there's a saying that 'good data is more important than good model'. And model evaluation is the way you can get some idea about how your model got trained and how well it can perform.

Hereafter a some methods usually used to evaluate models (classification).

## Model evaluation (Classification)

### Confusion matrix

Confusion matrix is a quick view of how good your classification model is.

<img src="{{site.baseurl}}/assets/img/CleanShot 2021-01-05 at 15.16.55@2x.png" alt="Confusion Matrix" style="zoom:50%;" />

Here are several quantities we use in terms of confusion matrix:

- Recall: $\frac{TP}{TP+FN}$  ability to find all relevant instances
- Precision: $\frac{TP}{TP+FP}$  the proportion of the data points that the model says was relevant actually were relevant
- F1 score: harmonic mean of precision and recall $\mathrm{F}_1=2*\frac{\mathrm{precision} * \mathrm{recall}}{\mathrm{precision} + \mathrm{recall}}$ 
- ROC curve: shows how the recall vs precision relationship changes as we vary the threshold for identifying a positive in our model.
  - True positive: $\frac{TP}{TP+FN}$ 
  - False positive: $\frac{FP}{FP+TN}$ 
- AUC: area under curve is a way to measure the performance of model, the higher value means the better performance

<img src="{{site.baseurl}}/assets/img/Notes-4.jpg" alt="Model evaluation" style="zoom:50%;" />

Later I will upload an example using ML/DL to classify quasars and galaxies.

I plan to start a project tracing my learning road to ML/DL, this will be a series posts.

**If I have time and I am not lazy** :-)