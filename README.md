# Melanoma-Assignment
# Multiclass Classification model for Melanoma Detection

## Problem Statement
In this assignment, we built a multiclass classification model using a Custom CNN in TensorFlow. 

 

#### Problem statement: To build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution which can evaluate images and alert the dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.


The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging Collaboration (ISIC). All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of images, with the exception of melanomas and moles, whose images are slightly dominant.
The data set contains the following diseases:

1. Actinic keratosis
2. Basal cell carcinoma
3. Dermatofibroma
4. Melanoma
5. Nevus
6. Pigmented benign keratosis
7. Seborrheic keratosis
8. Squamous cell carcinoma
9. Vascular lesion
 

NOTE: We didn't use any pre-trained model using Transfer learning. All the model building process is based on a custom model.

 

#### Project Pipeline
- Data Reading/Data Understanding → Defining the path for train and test images 
- Dataset Creation→ Create train & validation dataset from the train directory with a batch size of 32. Also, make sure to resize the images to 180*180.
- Dataset visualisation → Create a code to visualize one instance of all the nine classes present in the dataset 
- Model Building & training : 
    Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model rescale images to normalize pixel values between (0,1).
- Choose an appropriate optimiser and loss function for model training
- Train the model for ~20 epochs
Observations:
From the above patterns, it is observed that Training Accuracy got improved to 81.66% and Training Loss got reduced to as low as 0.5064. These, metrics seems to be good.

However, Validation Accuracy and Validation Loss were obtained to be 54.69% and 2.2259 which are not so good.

Hence, we can observe the Overfitting with this model. Further, by using data augmentation techniques such as Image Rotation, Image flip, Image Zoom, etc., we can get better results.


- Choose an appropriate data augmentation strategy to resolve underfitting/overfitting 
**Model Building & training on the augmented data :**
  - Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model rescale images to normalize pixel values between (0,1).
  - Choose an appropriate optimiser and loss function for model training
  - Train the model for ~20 epochs
  - Observations:
From the above patterns, it is observed that Training Accuracy obtained as 55.07% and Training Loss obtained to be 1.27. These, metrics seems to be average.

Further, Validation Accuracy and Validation Loss were obtained to be 54.91% and 1.34.

Hence, we can accept that Overfitting problem is solved.

However, there is still more scope for improving the Accuracy of the model. This can be done by doing class Balancing and Data Normalization.



**Class distribution: **
  - Examine the current class distribution in the training dataset 
  - Which class has the least number of samples?
  - Which classes dominate the data in terms of the proportionate number of samples?
**Handling class imbalances:** 
  - Rectify class imbalances present in the training dataset with Augmentor library.
**Model Building & training on the rectified class imbalance data:**
  - Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model rescale images to normalize pixel values between (0,1).
  - Choose an appropriate optimiser and loss function for model training
  - Train the model for ~30 epochs
  - Final Observations:
Overfitting was observed with Initial Model. This means the training accuracy was high, but the validation accuracy was significantly lower, indicating Overfitting. This might have happened due to non-usage of Data Generator provisions such as Class Balancing, Data Augmentation, etc.

After the execution of Class Imbalancing rectification using Data Augmentation and Batch Normalization, it is observed that both Training Accuracy & Validation Accuracy got improved. Hence, we can say that Overfitting is improved.

Also, we can observe that, patterns for Accuracy and Loss for both Training and Validation data sets got converged with each other from the graphs generated above.

Reasons for Improved Performance:
Class Balancing:
class balancing technique enhanced the performance and reliability of machine learning models by ensuring better accuracy by reducing bias leading to learn more effectively from each & every class with reduced bias towards majority classes.

Batch Normalization:
It is observed that Batch Normalization enhanced the training of deep neural networks by improving training stability, reducing overfitting, accelerating convergence, and simplifying the optimization process. These benefits have contributed to convergence of patterns corresponding to Accuracy and Loss for both Training and Validation data sets.

Dropout:
Droupout layers were introduced inorder to randomly drop few units thereby preventing Overfitting.

ImageDataGenerator:
Further, it is believed that features such as rotation, flipping, etc., of ImageDataGenerator contributed for better test accuracy as well as validation accuracy and lessened overfitting. 

 

The model training may take time to train. Hence, Google colab was used.



