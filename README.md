# Comparative Transfer Learning Techniques for Plate Number Recognition

## Table of Contents
  - [About](#about)
  - [Program Description](#program-description)
  - [Datasets Used](#datasets-used)
  - [Method](#method)
  - [Results](#results)
  - [Conclusion](#conclusion)
  - [Contact](#contact)

## About

Monitoring vehicle activity both on the highway and in certain places such as parking lots needs to be done if there is a specific incident. Unexpected events such as accidents or vehicle theft may occur at times. Therefore, tracking through number plate recognition has become an important and hot topic with the various methods used. Previous research used machine learning techniques to recognize characters on number plates. The use of this technique does not produce optimal accuracy. Therefore, we propose using transfer learning techniques to achieve better accuracy results. This research evaluates three transfer learning models, namely the DenseNet121, MobileNetV2, and NASNetMobile models.

## Program Description

This program was created to find and play the best model by comparing three types of transfer learning models, namely DenseNet121, MobileNetV2, and NASNetMobile, which later these models can be used to detect characters on vehicle number plates.

## Datasets Used

- [Dataset](https://www.kaggle.com/datasets/nainikagaur/dataset-characters): The character dataset used in this research was obtained from Kaggle. There were 36 characters with ten numeric
characters and 26 letter characters. The data used was in black and white, with the character color being white and the background black. Example of the dataset :

![image](https://github.com/Rifqiakmals12/AI-Project-Comparative-Transfer-Learning-Techniques-for-Plate-Number-Recognition/assets/72428679/c518e609-84ae-43bd-a089-4c7829b49fea)


## Method
The character recognition system on motorized vehicle license plates starts from the character training stages of letters and numbers. The character dataset was pre-processed first to adjust to the size of the training process using transfer learning techniques. Then, to increase the diversity of the data, we also used data augmentation. The dataset that had been pre-processed was divided into training data and testing data. The next stage was feature extraction using DenseNet121, MobileNetV2, or NASNetMobile. The result of feature extraction was a model used to match the features with the vehicle's character. Then, the vehicle number plate data was obtained from the image at the testing stage. The image data obtained was searched for the number plate area. The detected number plate was segmented using a bounding box. The segmentation results were used for matching with the feature extraction model. The final result was the character on the vehicle plate. Figure shows the stages of the vehicle plate number recognition.

![image](https://github.com/Rifqiakmals12/AI-Project-Comparative-Transfer-Learning-Techniques-for-Plate-Number-Recognition/assets/72428679/7426b2b5-af69-469a-aca7-49b56d544d83)

#### A. Dataset 
The total data used in this research was 37,623 data. Then, for the testing data, we used motor vehicle image data. The image was shot perpendicular to the vehicle object. We used the image of Indonesian vehicle plates in the parking lot.

#### B. Data Pre-Processing
Before being used for the feature extraction stage, the dataset was carried out in a pre-processing stage to adjust to the transfer learning model. The pre-processing stage was done by resizing 224 x 224 to fit the pre-trained transfer learning model. Then, we also used data augmentation to add diversity to the data used in the feature extraction stage. We used the ImageDataGenerator library, provided by the Python programming language for data augmentation. 

#### C. Feature extraction
Traditional feature extraction cannot automatically determine what features are present in an object. When the number of available features is large, the feature extraction method used must also have many parameters to extract these features. Therefore, deep learning provides a breakthrough by automatically extracting features on image objects. The popularity of deep learning continues to grow as large amounts of data become available, namely ImageNet. However, the use of large amounts of data is challenging to obtain. Therefore, there is an alternative called transfer learning. Transfer learning is a training method in which the model has been previously trained, and the results can be used for other case datasets. Many transfer learning models, including MobileNetV2, NASNetMobile, and DenseNet121.

#### D. System Evaluation
The evaluation of the system in this research was done using the image of a vehicle with a number plate. The vehicle image detects the position of the number plate. Then, the detected number plate was executed, not a segmentation process to divide each character on the number plate. The character on the license plate was matched with the feature extraction results of the MobileNetV2, NASNetMobile, or DenseNet121 models. Evaluation was done by counting the correct number of characters divided by the number on the license plate. We used 15 number plate data, so the final
accuracy was obtained from the average accuracy of each number plate. 

## Results
This section discusses the results of making a number plate recognition system using transfer learning. In this
research, the program was created using the Python programming language version 3. The discussion was divided into two stages: the training and testing stages.

#### A. Training Stage
The training stage is the stage of model formation for vehicle number plate recognition. The configuration of the transfer learning method in this research used transfer learning in the feature extraction section or the base model. The classification layer uses the Dense and Dropout layers. This research used a Dropout value of 0.5. Then in the loss function, we used categorical crossentropy with the Adam optimizer. We used the EarlyStopping function to stop the training process so that the resulting graph did not look overfitting. Figure shows a graph of the training results. In both models graphs generated from the training process using MobileNetV2, DenseNet121, and NASNetMobile overfitting did not occur. The training and validation accuracy graphs from epoch five seem to be parallel. Similarly, the training and validation loss graphs were also parallel. 

- MobileNetV2 Training results on accuracy and loss values
![image](https://github.com/Rifqiakmals12/AI-Project-Comparative-Transfer-Learning-Techniques-for-Plate-Number-Recognition/assets/72428679/80bfa91e-3c3e-4a51-8b63-3699ef8dfe13)


- DenseNet121 Training results on accuracy and loss values
![image](https://github.com/Rifqiakmals12/AI-Project-Comparative-Transfer-Learning-Techniques-for-Plate-Number-Recognition/assets/72428679/aedd0f85-ccbb-46fa-8f05-b23e73b82fb0)


- NASNetMobile Training results on accuracy and loss values
![image](https://github.com/Rifqiakmals12/AI-Project-Comparative-Transfer-Learning-Techniques-for-Plate-Number-Recognition/assets/72428679/848dff75-dd59-4ae6-bac0-57b4a7ded868)


The EarlyStopping function that we used monitored the validation loss value with a value of 5 so that if there was no better chance of 5 epochs, the training process would be stopped. Table 1 shows the results of training using the three
models. The DenseNet121 model had the fastest training process because it only had up to 10 epochs. Meanwhile, the NASNetMobile model reached the 22nd epoch. Then the MobileNetV2 model reached the 26th epoch. When compared to the validation loss values of the three models, the results of the MobileNetV2 model were the best. We saved these three models for testing using license plate testing data. The table below shows the result of the validation loss training process:

![image](https://github.com/Rifqiakmals12/AI-Project-Comparative-Transfer-Learning-Techniques-for-Plate-Number-Recognition/assets/72428679/a08de702-807e-4d4b-a2f8-b789c27b7cab)



#### B. Testing Stage
In the testing phase, we used data taken in the parking lot. The testing data consisted of 15 number plates, both car and motorcycle license plates in Indonesia. The detected number plates were matched using the three training models. The table shows the results of the number plate recognition accuracy. The percentage was obtained by counting the correct characters divided by the number of characters on the license plate. Then, the average accuracy is obtained from the average accuracy in each model.

![image](https://github.com/Rifqiakmals12/AI-Project-Comparative-Transfer-Learning-Techniques-for-Plate-Number-Recognition/assets/72428679/c03d6614-b8ce-4947-ad97-01b329aad18b)


The table shows that the DenseNet121 model produced the best average accuracy than the MobileNetV2 and NASNetMobile models. Several characters were detected incorrectly, for example, the letter D with O, and B with the number 8. When
viewed in general, the characters have almost the same shape. The dataset used was also in black and white. No color stood out from each character, resulting in errors when matching. However, overall, the accuracy produced by the DenseNet121 model was better than the use of machine learning techniques. This accuracy result is also due to the influence of the number of parameters on the DenseNet121 model than on the MobileNetV2 and NASNetMobile models. Future research can add datasets with various writing styles to increase the accuracy of results.

## Conclusion
Vehicle number plates need to be identified when unexpected events occur on the streets. Many CCTV cameras have been installed on the road and in the parking lot to monitor driving activities. Previous research used machine
learning techniques to perform number plate recognition. The use of machine learning has not yet produced optimal accuracy. This research used three transfer learning techniques for number plate recognition. The results showed that the DenseNet121 model yielded an accuracy of 96.42%. This research still has shortcomings in recognizing the number plates with a variety of character models. Therefore, it is recommended that future research increase the diversity
of data to increase accuracy. 

## Contact

If you have questions or feedback, feel free to reach out to us at [rifqias1212@gmail.com].

Thank you for exploring our project or portfolio!
