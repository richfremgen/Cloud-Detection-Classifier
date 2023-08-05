# Cloud-Detection-Classifier
Applying various Machine Learning methods to build a cloud detection classifier

## Overview of the project
The goal of this project is the exploration and modeling of cloud detection in the polar regions based on radiance recorded automatically by the MISR sensor abroad the NASA
satellite Terra. You will attempt to build a classi cation model to distinguish the presence of cloud from the absence of clouds in the images using the available signals/features. Your
dataset has *expert labels* that can be used to train your models. When you evaluate your results, imagine that your models will be used to distinguish clouds from non-clouds on a
large number of images that won't have these *exper labels*. 

## 1 Data Collection and Exploration (30 pts)
(a) Write a half-page summary of the paper, including at least the purpose of the study, the data, the collection method, its conclusions and potential impact.
(b) Summarize the data, i.e., % of pixels for the di erent classes. Plot well-labeled beautiful maps using x; y coordinates the expert labels with color of the region based on the expert labels. Do you observe some trend/pattern? Is an i.i.d. assumption for the samples justi ed for this dataset?
(c) Perform a visual and quantitative EDA of the dataset, e.g., summarizing (i) pairwise relationship between the features themselves and (ii) the relationship between the expert labels with the individual features. Do you notice di erences between the

## 2 Preparation (40 pts)
Now that we have done EDA with the data, we now prepare to train our model.

(a) (Data Split) Split the entire data (imagem1.txt, imagem2.txt, imagem3.txt) into three sets: training, validation and test. Think carefully about how to split the data.
Suggest at least two non-trivial different ways of splitting the data which takes into account that the data is not i.i.d.
(b) (Baseline) Report the accuracy of a trivial classi er which sets all labels to -1
(cloud-free) on the validation set and on the test set. In what scenarios will such a
classi er have high average accuracy? Hint: Such a step provides a baseline to ensure
that the classi cation problems at hand is not trivial.
(c) (First order importance) Assuming the expert labels as the truth, and without using
fancy classi cation methods, suggest three of the \best" features, using quantitative
and visual justi cation. De ne your \best" feature criteria clearly. Only the relevant
plots are necessary. Be sure to give this careful consideration, as it relates to subsequent
problems.
(d) Write a generic cross validation (CV) function CVmaster in R that takes a generic
classi er, training features, training labels, number of folds K and a loss function (at
least classi cation accuracy should be there) as inputs and outputs the K-fold CV loss
on the training set. Please remember to put it in your github folder in Section 5.

## 4 Diagnostics (50 pts)

Disclaimer: The questions in this section are open-ended. Be visual and quantitative! The
gold standard arguments would be able to convince National Aeronautics and Space Ad-
ministration (NASA) to use your classification method|in which case Bonus points will be
awarded.
(a) Do an in-depth analysis of a good classi cation model of your choice by showing some
diagnostic plots or information related to convergence or parameter estimation.
(b) For your best classi cation model(s), do you notice any patterns in the misclassi cation
errors? Again, use quantitative and visual methods of analysis. Do you notice problems
in particular regions, or in speci c ranges of feature values?
(c) Based on parts 4(a) and 4(b), can you think of a better classi er? How well do you
think your model will work on future data without expert labels?
(d) Do your results in parts 4(a) and 4(b) change as you modify the way of splitting the
data?
(e) Write a paragraph for your conclusion.

## 5 Reproducibility (10 pts)
In addition to a writeup of the above results, please submit a zip  le containing everything
necessary to reproduce your writeup to Gradescope \PROJ2 code". Speci cally, imagine that
at some point an error is discovered in the three image  les, and a future researcher wants
to check whether your results hold up with the new, corrected image  les. This researcher
should be able to easily re-run all your code and produce all your  gures and tables. This zip
 le should contain:
(i) the raw Latex, Rnw or Word used to generate your report,
(ii) your R code (with CVmaster function in a separate R  le),
(iii) a README.md  le describing, in detail, how to reproduce your paper from scratch
(assume researcher has access to the images)