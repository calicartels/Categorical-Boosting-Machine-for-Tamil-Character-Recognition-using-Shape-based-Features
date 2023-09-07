# Categorical-Boosting-Machine-for-Tamil-Character-Recognition-using-Shape-based-Features
Code for the paper presented at the 7th International Conference on Computing, Communication,  Control and Automation  (ICCUBEA-2023), Pune, India.<br>
[Presenter certificate](https://drive.google.com/file/d/1b9na883fqxGDrkjL0EMzbx4I-w3YdRNH/view?usp=sharing)


## Table of Contents
- [Dataset](#dataset)
- [Introduction](#introduction)
- [Problem Statement](#problem-statement)
- [Objectives](#objectives)
- [Methodology](#Methodology)
- [Sample Visualization](#sample-visualization)
- [Results](#Results)
- [Credits](#credits)




### Dataset

[Preprocessed Data](https://www.kaggle.com/datasets/faizalhajamohideen/uthcdtamil-handwritten-database) <br>

## Introduction

- Tamil is one of the oldest surviving languages of the world, which serves as an inspiration for various modern Indian scripts.
- With 84.12 million native speakers, Tamil has the highest prevalence in India. A total of about 89.7 million people worldwide speak Tamil as their mother tongue.
- Despite it being a predominant language, there has been insufficient focus on the development of OCR techniques specifically tailored for Tamil characters.
- This paper focuses on introducing a new Optical Character Recognition-based handwritten character recognition methodology for identifying Tamil vowels and subsequently extending support to the entire alphabet base. 
- The effort focuses on establishing a novel Contour Handwritten Feature Recognition feature detection and classification of the features using prevalent Machine Learning models.

## Problem Statement

- The problem addressed in this research is the limited development of Optical Character Recognition (OCR) techniques for Tamil characters.
- Despite the significance of Tamil as one of the world's earliest surviving languages and its inspiration for modern Indian scripts, there has been minimal attention given to developing effective OCR solutions 
  for Tamil characters.
- The intricate shapes and curves of the Tamil alphabet, comprising 12 vowels, 18 consonants, and special characters, pose challenges for accurate character recognition. 
- The objective of this study is to propose a new model for Tamil vowels-based OCR, utilizing a CHFR feature extraction technique and a CatBoost classifier optimized with Optuna, to achieve improved accuracy in 
  identifying handwritten Tamil characters.
- The research aims to address the gap in OCR technology for Tamil characters and provide a comparative analysis of existing OCR studies across different languages and algorithms.

## Objectives

- The primary focus is to build an effective feature detection approach that aims to find similarities in the shapes of alphabets.
- The secondary aim is to classify the feature vector using widely used classification models. Here, the results are tested using various evaluation metrics, with the primary metric being Accuracy. The rest of 
  the metrics considered include Matthews Correlation Coefficient, Area Under the Curve, and F1 Score.
- The tertiary aim is to optimize the models using hyperparameter optimization frameworks and derive the best possible results.
- The final task is to identify the shortcomings of the entire operation, starting from the Data, the feature extraction process, and the Models used.

## Methodology

- The proposed optical character recognition (OCR) model for the Tamil alphabet comprises three key stages: preprocessing, feature extraction, and model fitting.
- In the preprocessing stage, the text images are transformed into grayscale and subjected to a binarization process to eliminate background noise and facilitate contour generation.
- Redundant contours are filtered out by discarding the contours with lengths less than 10, and morphological operations such as dilation are applied to enhance image clarity.
- The next stage involves feature extraction, where the centroids of the remaining contours are determined, and 20 segments are drawn around each centroid in a clockwise direction.
- The Contour Handwritten Feature Recognition (CHFR) is employed to compute three primary features - length (ρ), angle (θ), and chord-to-arc-ratio (τ) - for each segmented arc of the Tamil vowel contour. These 
  features are combined into a 1 × 60-dimensional feature vector for each vowel.
- The three primary features are explained as follows :
 1. The "length" (ρi) is the distance between the center point of a shape (centroid) and the end of each segment.
 2. The "angle" (θi) is the measurement of the angle formed between a straight line connecting the centroid and the middle point of the segment (chord ρi).
 3. The "smoothness" of the curve of each segment is measured by the "chord-to-arc-ratio" (τi) which calculates the ratio between the length (ρi) and the line connecting two subsequent points of interaction 
     between the contour and the length.

## Sample Visualization

- Sample Visualization of the Tamil letter “ஐ” :
![Proposed Visualization](https://github.com/calicartels/Categorical-Boosting-Machine-for-Tamil-Character-Recognition-using-Shape-based-Features/blob/main/sample%20vis.png)

- Example Visualization in real-time :
![Real-time Visualization](https://github.com/calicartels/Categorical-Boosting-Machine-for-Tamil-Character-Recognition-using-Shape-based-Features/blob/main/in%20real%20time.png)

## Results

- In this study, we divided the dataset into two parts - 70% for training and 30% for testing. The Optuna framework was used to find the best combination of hyperparameters for our model, ensuring optimal 
  performance during training and testing.
- The proposed CHFR feature extraction coupled with the CatBoost model shows improved performance with respect to the other models by achieving an accuracy of 86.36%.
- The analysis reveals that there are certain challenges in accurately recognizing pairs of classes, specifically classes 10 and 9, as well as classes 5 and 11. This difficulty arises due to the similarity in 
  shape between these pairs.
- Another notable factor affecting recognition accuracy is the presence of disjointed contours in certain samples within the dataset. These disjointed contours behave unusually during the feature extraction 
  process. 
- Instead of considering the entire contour, the feature extraction algorithm operates on individual segments of the contour, resulting in reduced model accuracy.

## Credits 

- TM Vishnu Mukundan 
- Isha Nevatia


















 









