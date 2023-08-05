---
output:
  pdf_document: default
  html_document: default
---

# README for Cloud Detection Project:

## 1 - Contents of this folder:

 - README.md
 - 1_EDA_Code.Rmd - run this Rmd to walk through the EDA performed
 - 2_Model_Code.Rmd - run this Rmd to reproduce the models developed
 - 521_Proj2_Paper.doc - final report of findings 
 - CVmaster.R - function that outputs the K-fold cross-validation loss for any tidymodel
 - image_data folder - contains the three image data for analysis 
 - Cloud_Paper.pdf - "Daily Arctic Cloud Detection" paper
 - project2.pdf - STA 521 Project 2 Instructions 

##  2 - Getting Started:

The objective of this assignment is to build a classification model to distinguish the presence of clouds from the absence of clouds for three images provided from a MISR sensor on the NASA Terra satellite. The raw data provided for this assignment is located in the image_data folder and contains three .txt files with satellite image data. 

To reproduce the analysis, first open the 1_EDA_Code.Rmd file and set your working directory to the location where the image_data folder is. Next, load the necessary packages in the Rmd and run code chunk 0 to load in the image data and perform some preliminary data cleaning on the variables. The next several code chunks in the Rmd under the header ## 1 - Data Collection and Exploration, contain several attempts to visualize and explore the data (EDA). The steps performed in this section ranged anywhere from creating basic summary tables of the variables of interest, to performing PCA on the predictors. Please note that running all of code chunks in ## 1 is optional and solely for EDA purposes. 

Following, completion of EDA, run the series of code chunks under the ## 2 - Preparation header to modify the dataset in order to partition the data into twelve total blocks and clusters. These partitions will be used in the modeling phase of the analysis to split the data into a training, testing, and validation data set.  

## 3 - Modeling 

Once EDA is complete, open the 2_Model_Code.Rmd file to perform model assessment and selection in order to build a classification model to classify the satellite image data. Code chunks under ## 0 and ## 1 are duplicates from the 1_EDA_Code.Rmd file, as these code chunks are used to load, clean and transform the image data prior to splitting. Running this code is not required, if you have already done so in 1_EDA_Code.Rmd

Use Code Chunks 2A and 2B to split the data into training, testing and validation sets, before writing in the CVmaster function in Code Chunk 2C, which can be used to return the K-fold cross-validation (CV) error for a given model.

The rest of the Rmd is dedicated to fitting different models to the image data set, to determine which model best fit the data. In this Rmd, Logistic Regression, QDA, KNN, and Random Forests were all applied to both the block and cluster data splits. Each model's chunk will return the CV error for each fold from the CVmaster function and then fit the tuned model (if applicable) to the testing data set. The remainder of the Rmd includes code to further tune and explore our selected model (Random Forests), which includes extracting a tree, performing variable importance, and exploring mislabeled data points. 

## 4 - Additional Warnings

For models that take more computational time (KNN and Random Forests), recommend including "doParallel::registerDoParallel()" in your code chunk to speed up the processing time. Using this function, decreased 10-fold CV with a KNN model by 60%. Recommend running a model's entire code chunk at once, since many of the variable names are the same for each fitted model. 

