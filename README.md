# Ear-Infection-Identifier

## Contents
 - [Problem Statement](#Problem-Statement)
 - [Executive Summary](#Executive-Summary)
 - [File Directory](#File-Directory)
 - [Data](#Data)
 - [Data Dictionary](#Data-Dictionary)
 - [Conclusions and Recommendations](#Conclusions-and-Recommendations)
 - [Areas for Further Research/Study](#Areas-for-Further-Research/Study)
 - [Sources](#Sources)
 - [Visualizations](#Visualizations)


## Problem Statement
[back to top](#Ear-Infection-Identifier)

Based on picture data from "OtoMatch: Content-based eardrum image retrieval using deep learning", can a machine learning neural networks model correctly identify if a picture of an ear drum is showing signs of an ear infection and indicate if an individual should get their ear checked by a healthcare provider. 



## Executive Summary
[back to top](#Ear-Infection-Identifier)

The goal of this analysis is to see if a neural network model can accurately identify infected eardrum from noninfected eardrums. The metrics being used are accuracy, precision, and recall. These are appropiate since we want to reduce the number false negatives in the model. Initially, I used the dataset from  "OtoMatch: Content-based eardrum image retrieval using deep learning" with their original the categories of effusion, TM tube and normal eardrum images. The models I performed overfit on training data and did not perform as well on testing data. The pretrained models used were MobileNetV2, VGG16, Xception, InceptionV3. These pretrained networks were not successful in improving metric scores either. The most successful model was a neural network model with convolutional layers, augmented data and average pooling. This model had the highest test recall, precision, and accuracy score with recall score of 0.6730, preceision score of 0.6859 and accuracy test score of 0.6855. However, this model was very overfit to training data. Next steps I would like to train a neural network to identify images into these five categories:

1) Effusion: Showing signs of not infected fluid (clear or serous fluid) behind the eardrum
2) Otitis Media: Showing signs of infected eardum (purulent fluid) behind the eardrum
3) TM Tube: Eardrum images with TM tube through eardrum
4) Healthy Eardrum(Normal): No signs of fluid behind eardrum or TM tube
5) Unclear: Images that has been augmented that I could not identifiy


Success for this project would be to accurately indicate:

1) Eardrum is showing signs of non infected fluid behind ear, monitor for any new/worsening symptoms and contact healthcare provider if any worsening symptoms 
2) Eardrum showing signs of infection and individual should contact healthcare provider for evaluation and management
3) Eardrum is not showing signs of infection, monitor for any new/worsening symptoms and contact healthcare provider if any worsening symptoms 
4) Eardrum is showing TM tube in eardrum, monitor for any new/worsening symptoms and contact healthcare provider if any worsening symptoms 
5) Unclear eardrum image(may be cerumen obstruction or otitis media with effusion). May retake image and contact healthcare provider for eval

## File Directory
[back to top](#Ear-Infection-Identifier)

05-Project<br />
|<br />
|__ code<br />
|&nbsp;&nbsp;&nbsp;&nbsp;|__ 00_table_of_contents.ipynb <br />
|&nbsp;&nbsp;&nbsp;&nbsp;|__ 01_data_cleaning_and_eda.ipynb <br />
|&nbsp;&nbsp;&nbsp;&nbsp;|__ 02_preprocessing_and_modelling.ipynb <br />
|&nbsp;&nbsp;&nbsp;&nbsp;|__ 03_production_model.ipynb <br />
|&nbsp;&nbsp;&nbsp;&nbsp;|__ 04_streamlit_app.ipynb <br />
|&nbsp;&nbsp;&nbsp;&nbsp;|__ 05_conclusion.ipynb <br />
|<br />
|__ data <br />
|&nbsp;&nbsp;&nbsp;&nbsp;|__ middle_ear_images <br />
|&nbsp;&nbsp;&nbsp;&nbsp;|__ results_df.csv <br />
|<br />
|__ images <br />

|<br />
|__ models <br />

|<br />
|__ presentation <br />

|<br />
|__ Streamlit <br />

|<br />
|__ README.md <br />
|__ LICENSE <br />


## Data
[back to top](#Ear-Infection-Identifier)

Data downloaded from "OtoMatch: Content-based eardrum image retrieval using deep learning" at https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0232776.

The picture data was placed into three categories already from the download. The three categories are pictures of ears with tympanostomy tubes(TM tubes) with 96 images, healthy(normal) eardrums with 179 images and eardrums with fluid(infected and noninfected fluid)behind the eardrum with 170 images.

The previous authors of the research study had already performed data augmentation by rotating and scaling images. The previous authors had also preprocessed the images to isolate the region of interest.

I split the three categories into test and train set with 30% of images going to test set and 70% for training. I then used 20% of training set for validation. 

I did inital modeling on those categoires and then I resorted the images into 5 different categories:

1) Effusion: Showing signs of not infected fluid (clear or serous fluid) behind the eardrum
2) Otitis Media: Showing signs of infected eardum (purulent fluid) behind the eardrum
3) TM Tube: Eardrum images with TM tube through eardrum
4) Healthy Eardrum(Normal): No signs of fluid behind eardrum or TM tube
5) Unclear: Images that has been augmented that I could not identifiy


## Data Dictionary
[back to top](#Ear-Infection-Identifier)



## Conclusions and Recommendations
[back to top](#Ear-Infection-Identifier)


## Areas for Further Research/Study
[back to top](#Ear-Infection-Identifier)

For future studies, a larger training dataset would help the overall performance of the model. 

Another aspect that should be noted is the quality of the ear drum images. Many images online are very clear. If this application was to be used in real life there may be images that have cerumen obstructing part of the image. Future studies should implement images with slight obstructions and TM ear tubes in training data as well. Images should not be completely obstructed since this could impact proper evaluation of ear drum. 

This model will only be trained to evaluate middle ear infection and will not be trained on otitis externa or outer ear infections. To expand the utility of this model. Images of otitis externa could be trained into the model as another category.

## Sources
[back to top](#Ear-Infection-Identifier)

https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0232776

## Visualizations
[back to top](#Ear-Infection-Identifier)

