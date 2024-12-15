# NeuralFCA-project

## Dataset: **70k+ Job Applicants Data (Human Resource)**

## Description

The dataset called "Employability Classification of Over 70,000 Job Applicants" (though we will use only 1000 observations for performance reasons) provides a detailed collection of information about job applicants and their employability scores. Based on survey responses, the dataset includes the following columns:
-  Age: The applicant's age, categorized as >35 years or <35 years (categorical)
- EdLevel: The applicant's education level (Undergraduate, Master, PhD, etc.)
(categorical)
-  Gender: The applicant's gender (Man, Woman, or NonBinary) (categorical)
-  MainBranch: Indicates whether the applicant is a professional developer
(categorical)
- YearsCode: The number of years the applicant has been coding (integer)
- YearsCodePro: The number of years the applicant has been coding in a
professional setting (integer)
- PreviousSalary: The applicant's previous job salary (float)
- ComputerSkills: The number of computer skills known by the applicant (integer)
- Employed: The target variable, indicating whether the applicant was hired
(categorical)

## Preprocessing 
- Get 1000 rows 
- Dropped duplicates and rows with missing data
- Removed 'HaveWorkedWith' and 'Country' to avoid excessive features after one-hot encoding
- Binarized numerical features based on the mean value of each column

Then we got 21 result features

## Neural FCA network

The lattice was generated using the Sofia algorithm. The performance of each formal concept was evaluated by calculating the F1-score and Recall score.
The model was built by selecting the 50 best formal concepts (the best results among all numbers) based on their F1- scores. These selected formal concepts were then used to design a Neural Network (NN) architecture, which was visualized in Figure 1. The network was trained with a GELU activation function for a total of 2,500 epochs.

  <img width="738" alt="image" src="https://github.com/user-attachments/assets/00697594-9c66-4f7f-a60e-12b32927dc56" />

  Figure 1 :  Network Visualization of Formal Concepts with Fitted Edge Weights
  
## Results
Model
Accuracy
F1-score
KNeighborsClassifier
0.783
0.782
DecisionTree
0.783
0.781
RandomForest
0.810
0.805
LogisticRegression
0.820
0.818
NeuralFCA
0.823
0.824
<img width="699" alt="image" src="https://github.com/user-attachments/assets/34dfab95-869d-4c2e-baeb-6db740629641" />

## Conclusion 

NeuralFCA achieves the highest performance, with Accuracy of 0.823 and F1-score of 0.824, outperforming a little all other models. But we sholud bear in mind that we construct neural network, bionirised and preprocessed data, whereas for other models we don't do nothing. Also one of important conslusion that NeuralFCA good at working with small and balanced sample like in our case (only 1000 rows).

