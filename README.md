# NeuralFCA-project

## Dataset: **70k+ Job Applicants Data (Human Resource)**

## Description

The dataset called "Employability Classification of Over 70,000 Job Applicants" (though we will use only 1000 observations for performance reasons) provides a detailed collection of information about job applicants and their employability scores. Based on survey responses, the dataset includes the following columns:

Age: age of the applicant, >35 years old or <35 years old (categorical)
EdLevel: education level of the applicant (Undergraduate, Master, PhD…) (categorical)
Gender: gender of the applicant, (Man, Woman, or NonBinary) (categorical)
MainBranch: whether the applicant is a profesional developer (categorical)
YearsCode: how long the applicant has been coding (integer)
YearsCodePro: how long the applicant has been coding in a professional context, (integer)
PreviousSalary: the applicant's previous job salary (float)
ComputerSkills: number of computer skills known by the applicant (integer)
Employed: target variable, whether the applicant has been hired (categorical).

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
<img width="421" alt="Снимок экрана 2024-12-15 в 15 19 35" src="https://github.com/user-attachments/assets/c5181b07-340e-4e59-8438-90fc52c458cd" />

NeuralFCA achieves the highest performance, with Accuracy of 0.823 and F1-score of 0.824, outperforming a little all other models. 

## Conclusion 

NeuralFCA achieves the highest performance, with Accuracy of 0.823 and F1-score of 0.824, outperforming a little all other models. But we sholud bear in mind that we construct neural network, bionirised and preprocessed data, whereas for other models we don't do nothing. Also one of important conslusion that NeuralFCA good at working with small and balanced sample like in our case (only 1000 rows).
