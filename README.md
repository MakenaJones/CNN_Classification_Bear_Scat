# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Capstone : Identification of Bear Droppings Using Convulated Neural Networks and Transfer Models

---
## Problem Statement

Hiking and exploring the outdoors is a great recreational activity that is not only beneficial for our physical health, but helps people with their mental health as well. Living in Alberta, Canada, which is home to the Canadian Rockies and some of the best (not to be biased) hiking in the world, I have experienced first hand how beneficial and healing getting outside in the wilderness can be.

With great beauty, however, comes a side of danger. Anyone who has spent time in the mountains can tell you that you should never venture onto the trail without a can of bearspray or without being "bear aware". Bears are amazing creatures, but it is important to respect their habitats and they can be dangerous to humans when startled. 

One of the ways we can identify if a bear has been on a trail is if there is fresh poo on the ground. Identifying bear poo is not a simple task for the average person, especially considering the variety of diets between different bear types and even the fact that poo from the same bear can look different from day to day [source](https://www.nps.gov/yose/blogs/the-scoop-on-bear-poop.htm#:~:text=In%20the%20spring%2C%20bears%20eat,berries%20and%20apple%20pieces%20visible). 

A solution to this problem would be if a hiker could take a picture of the scat, and an application using Convuluted Neural Networking (CNN) could determine if the photo is in fact from a bear or not, without having to consult a bear specialist. This information would be crucial not only for the safety of the hiker but for others using the trail as well as local wildlife biologists and conservationalists monitoring local bear populations.

This capstone aims to develop the best possible binary classification model with the ultimate goal of developping an app that can take an image and determine if it the animal poo comes from  a bear or not. The models will be trained on a custom dataset created from google image searches, and evaluated based on maximizing accuracy and minimizing loss.

---

## Table of Contents

1. [Data Collection](https://github.com/MakenaJones/CNN_Classification_Bear_Scat/blob/main/code/01_data_collection.ipynb) : Mass download images from google of both bear and other animal droppings to sort into classes to use for classification models.

2. [EDA and Null Model](https://github.com/MakenaJones/CNN_Classification_Bear_Scat/blob/main/code/02_EDA_and_Null_Model.ipynb) :  Label and examine image classes using Tensorflow and evaluate the null model. 

3. [CNN Models](https://github.com/MakenaJones/CNN_Classification_Bear_Scat/blob/main/code/03_CNN_model.ipynb) : Run different CNN models using early stopping and dropout to get the best performance, using techniques such as data augmentation since dataset is relatively small.

4. [Transfer Models](https://github.com/MakenaJones/CNN_Classification_Bear_Scat/blob/main/code/04_Transfer_Model.ipynb) : Use transfer model to see if it performs better than the models made from scratch in the previous section.

---

## Data Collection

Used code from [source](https://python.plainenglish.io/how-to-automatically-download-bulk-images-for-your-dataset-using-python-f1efffba7a03) to download and save multiple photos from google images of bear droppings, other animal droppings and miscellaneous photos.

I manually sorted the photos (and deleted irrelevant ones) into two classes, ["bear_scat"](https://github.com/MakenaJones/CNN_Classification_Bear_Scat/tree/main/images/bear_scat) and ["anything_but"](https://github.com/MakenaJones/CNN_Classification_Bear_Scat/tree/main/images/anything_but) to have 524 photos in each class of my custom dataset, for a total of 1048 images to use for the classification models. 

---

## EDA and Null Model

Labelled data into two classes: Bear Scat (1) and Not Bear Scat(2).
![image](https://github.com/MakenaJones/CNN_Classification_Bear_Scat/blob/main/figures/bearpoo_vs_not.png)

Also checked out null model, which has an accuracy of 50% as if we predicted every image was bear poo, we would classify it correctly 50% of the time.
   
---

## Model Evaluation

Used data augmentation to help train the CNN model, which ended up performing decently when it came to accuracy and loss (and data augmenting helped get rid of some of the overfitness of the data). 

Transfer model EfficientNetB0 only performed somewhat better.

--- 
## Going Forward

Since I was able to get decent performance with my simple CNN model trained using a less-than perfect dataset, can assume it would be feasible to develop an application that would take in a photo of animal droppings and identify if the scat was bear poo or not.

Going forward, I would like to :
* Launch a StreamLit app
* Get a better data set to train my model on (collect and label very carefully all different types of bear scat and other animal droppings)
* Expand to identifying different kinds of animals by their poo

---

## System Requirements
Required imports include Tensorflow (version 2.9 for the transfer net), Keras, pandas, matplotlib and numpy. Notebooks 2 through 3 were launched in Google Collab.