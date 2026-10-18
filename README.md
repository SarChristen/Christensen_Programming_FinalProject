# Christensen_Programming_FinalProject

Link to Notebook: https://colab.research.google.com/drive/1z_AGs6T-TL9HR9Rcc_q_BDgWBi0XFlqk?usp=sharing
## Purpose
#### To explore and analyze the Thoracic Surgery Dataset and build and evaluate binary classification models for predicting the survival up to one year post lung surgery.
## Brief description of analysis
The included analysis is an initial exploration of the Thoracic Surgery Dataset and continues with the building and evaluating of binary classification models for predicting the outcome. The analysis focused on the binary Outcome variable of Risk1Yr, which was True if patient died before the year was up and False if the patient survived at least a year after the lung surgery. The hope is that if an accurate prediction model can be built and the variables that have the most affect on this result can be identified, it can help patients survive longer after major lung surgery. 
#### 
## Dataset Source and Provenance
#### Dataset: Thoracic Surgery Data from the UC Irvine Machine Learning Repository, donated on 11/12/2013. The data comes from the Wroclaw Thoracic Surgery Centre and includes 470 patients who had major lung surgeries due to lung cancer between 2007 and 2011. https://archive.ics.uci.edu/dataset/277/thoracic+surgery+data

Access raw data via link above or within this GitHub repository: https://github.com/SarChristen/Christensen_Programming_FinalProject. The raw data file is named ThoraricSurgery.arff, but is within a zip file named thoracic+surgery+data.zip. 

Lubicz, M., Pawelczyk, K., Rzechonek, A., & Kolodziej, J. (2014). Thoracic Surgery Data [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5Z60N.

This dataset is designed for binary classification as the outcome or target variable was restricted to whether or not they survived up to one year after the lung surgery. There are 470 instances, or individual patients, and 16 features.

This dataset has the potential in learning what key variables have a high influence on the outcome, of survival one year post major lung surgery.

The initial 16 features that serve as the predictor variables in this dataset include diagnosis codes, lung capacity measurements including both Forced vital capacity (FVC) and Forced expiration volume in first second (FEV1). Also included are the performance status using the Zubrod scale, the size of the original tumor, and age at the time of the surgery. Other than the target variable of surviving the one year period post surgery, there are many other binary variables including the presence of many symptoms before surgery like, pain, coughing up blood (haemoptysis), shortness of breath (dyspnea), cough, weakness, type 2 diabetes, Myocardial Infarction (MI) up to six months, peripheral arterial disease (PAD), smoking, and asthma. 

## Required Packages, Libraries and versions (when applicable):
### Baseline Notebook, exploratory analysis and data preprocessing environment:
- google.colab import files
- pandas  version: 2.2.3
- numpy   version: 2.1.3
- seaborn version: 0.13.2
- matplotlib.pyplot
- scipy.io import arff
- io import StringIO
- pathlib import Path
- zipfile
- scipy.stats import norm
- math
- phik import resources, report
- phik.report import plot_correlation_matrix
- mpl_toolkits.mplot3d import Axes3D
- scipy.interpolate import griddata
- sklearn.preprocessing import OneHotEncoder, OrdinalEncoder
### For Inferential Statistics:
- scipy import stats
### For the Binary Classification Models
- sklearn.preprocessing import (
    StandardScaler,
    PowerTransformer,
    LabelEncoder
- sklearn.impute import KNNImputer
- sklearn.model_selection import (
    train_test_split,
    StratifiedKFold,
    cross_val_score,
    GridSearchCV
- sklearn.pipeline import Pipeline
- install imbalanced-learn
- imblearn.over_sampling import SMOTE
- imblearn.pipeline import Pipeline as ImbPipeline
- sklearn.linear_model import LogisticRegression
- sklearn.svm import SVC
- sklearn.tree import DecisionTreeClassifier, plot_tree
- sklearn.metrics import (
    confusion_matrix,
    classification_report,
    accuracy_score,
    precision_score,
    recall_score,
    f1_score,
    roc_auc_score,
    roc_curve,
    ConfusionMatrixDisplay
- sklearn.metrics import make_scorer
## Setup and Installation
#### Load the specified libraries and packages. A message will print when completed successfully.
#### Upload the data file that is included in this repository when directed. The second chunk of code is intended for this purpose. A message will print when completed successfully.
## Instructions for executing notebook
#### Go through each chunk of code in order (or select 'Run all' at the beginning.

## Expected Outputs
The expected outputs include the following inferential statistics tests, the Independent two-sample t-test comparing the mean FEV1/FVC ratios between outcome group and the Chi-Square Test, looking at the association between the outcome and the Smoking variable. Both tests did not find significance.
Three binary classification machine learning models were trained and evaluated, then tuned for improving recall and evaluated again to find the best model for predicting the outcome of surviving one year after major lung surgery. These three types of models were Logistic Regression, Support Vector Machine, and Decision Tree classifier. The models were tuned with Hyperparameter Tuning with the GridSearchCV() function from scikit-learn. The models were evaluated with the following metrics, Accuracy, Precision, Recall, F1-score, and ROC-AUC scores for both the training and test sets. 

## Conclusions
The Baseline Logistic Regression model is the best of the tested six models based on having the best Test Recall score, which minimizes the number of harmful False Negatives, while also having the best Test Precision and Test ROC-AUC value, suggesting this model is also has the best rate of False Positives, which may not be the primary metric, is still important, and that it is the best overall model at predicting the outcome variable for this dataset.

## Assumptions and limitations
Assumptions of this analysis include that the population the participants were sampled from has a normal distribution and the variance of the continuous variable, FEV1/FVC Ratio is equal between the outcome groups. Both of these assumptions allow the parametric statistics tests. 
Limitations of this dataset include the unbalanced outcome classes and the missing background information behind some of the variables, like the units for the measurements of the FEV1 and FVC, or the clinical cutoffs for possible measurements of these values. 
It would also have been interesting to have access to other variables including demographics.
