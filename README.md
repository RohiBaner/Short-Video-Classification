
# Short Video Classification (Python 3) #
Short video applications are becoming more and more popular among the young. In reality, internet companies generally use automatic classification algorithms to process large amounts of short video uploaded by users. Here, I provide a solution to the above stated problem.


## 1. Getting Started ##
Short videos are provided as datasets. A text file is also provided which contains the classes into which the training videos are to be classified. They have 15 labels, namely:

1. Dog
2. Boy selfie
3. Seafood
4. Snack
5. Doll catching
6. Ballroom dance
7. Origami
8. Weave
9. Ceramic art
10. Zheng playing
11. Fitness
12. Parkour
13. Diving
14. Billiards
15. Eye makeup

### 1.1. Data Description ###
The train videos folder contains about 2000 videos while the test video contains about 850 videos.

### 1.2. Prerequisites ###
The following libraries are required to run the code. All of them can be downloaded via conda or pip:

1. pandas
2. numpy
3. os, sys, cv2
4. keras
5. sklearn
6. PIL
7. shutil

Add both the two given video folders and the text file (https://drive.google.com/drive/folders/1wVwr0_jvsvUR-X2gmWj-iBHqURJHUGVd) into the same directory where the code is located.

### 1.3. Running the Code ###
The code can be run Jupyter Notebook.

## 2. Methodology ##
The following steps are followed to find the outliers in the given test image folder:
1. Import all the necessary libraries
2. Get snapshots of images from each of the training videos and testing videos. I have taken only 1 image per video (the frame which comes in the 1/3rd position of the entire video). The training videos are stored in output_dir. The testing videos are kept in test_output_dir. Both these folders are created via the code
3. Append ‘.jpg’ into the filename given in the text file as the images have that extension. Use the label provided in the text file to label the training images.
4. Extract features from every training image via ResNet50. I have used pretrained model only to extract the features of test and train data. The training of the features and predicting the labels are not done using any pretrained models.
5. Scale the features of both test and train features with Standard Scaler.
6. Train the SVC Classifier with the scaled train features and the labels (0-14).
7. Test the data and predict the labels for the test features extracted from the snapshots of the test videos.
8. Write the result in CSV in necessary format (remove the added ‘.jpg’ before appending it)

## 3. Author ##
BANERJEE, Rohini - HKUST MSc BDT (Student ID: 20543577)

## 4. References ##
1. https://blog.keras.io/building-powerful-image-classification-models-using-very-little-data.html
2. https://towardsdatascience.com/ways-to-detect-and-remove-the-outliers-404d16608dba
3. https://www.analyticsvidhya.com/blog/2018/09/deep-learning-video-classification-python/
4. https://github.com/wadhwasahil/Video-Classification-2-Stream-CNN
5. https://blog.coast.ai/five-video-classification-methods-implemented-in-keras-and-tensorflow-99cad29cc0b5
6. https://github.com/sagarvegad/Video-Classification-CNN-and-LSTM-
7. https://stackoverflow.com/questions/39622281/capture-one-frame-from-a-video-file-after-every-10-seconds
