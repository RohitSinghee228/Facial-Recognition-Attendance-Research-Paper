# Facial-Recognition-Attendance-Research-Paper
Presenting a lightweight Face detection model for attendance systems in educational and professional organization
Original Paper Link-![Research Paper](Facial%Recognition%attedance%research%Paper.pdf)

# Workflow
The diagram below defines the workflow of the project
![workflow](Images\Workflow.png)

# Haar Cascade Implementation
The Haar-Cascade algorithm (visual representation is shown in the image Fig.2 needs to be trained to detect human faces before the face detection.We have used a Haar cascade model for frontal face to detect faces which can be combined with other haar cascade model to increase accuracy of classifier.The frontal face model contains Haar features trained to detect faces .The features  are nothing but convolutional kernels.Each feature is a value obtained by subtracting pixels sum of black part from white.

![HaarCascade](Images\Haar_Cascade_Implemetation.png)

## Trained Classifier used in our model:
`haarcascade_frontalface_default`
`haarcascade_frontalface_alt`
## Functions Used
`cv::CascadeClassifier::CascadeClassifier(const String & Name of Classifier)`	
`DetectMultiScale(arguments)`
`detector.detectMultiScale(gray,scaleFactor,minNeighbors,minSize, flags=cv2.CASCADE_SCALE_IMAGE)`

# Realtime Attendance with visual feedback to users
c) Facial Recognition:
This phase involved detecting the face and mapping them to their data based on similarity index.
i) Detect faces in frame
The same pipeline as explained in sections 5.2 are used in the face recognition phase also where first the whether a
face is present in the input image is detected and if so is cropped to the region of interest.Next according to previous
input by users at training stage further KNN or LPB model is invoked for facial recognition.The two models working
are described below.
ii) Compare Saved model features using LBP or KNN
At this stage the LBP histogram for trained faces that are already present and the histograms of new detected faces are
compared.The comparison can be done by many ways like Euclidean Distance ,Chi-Square,Absolute value.We have
used Euclidean distance for comparison in our model because of its tested accuracy.This generates a confidence
score(lower score is better) for each stored histogram and the one with lowest score is selected as an match.
Similarly K-nearest neighbours (KNN) algorithm which is a simple supervised machine learning algorithm that is
used here for image classification. The KNN algorithm captures the idea of similarity based on distance, closeness
with mathematics, i.e., distance between the points on a graph. In this algorithm also Euclidean distance has been used
as the distance metric to perform the distance between two points on the graph.Thus in KNN the saved faces as numpy
array values are compared to the new detected faces for matching.

![Recognition Image](Images\Realtime_recognition_Visualization.png)

# Holistic Model Evaluation
The Technical evaluation of our Facial Recognition indexing system parameters as compared to other popular systems being used for Identification.
![Evaluation Image](Images\Holistic_evaluation.png)

# Excel Sheets Ouput
Excel Sheet generated for the administrator 
![Excel Sheet Image](Images\Attendance_Excel_Sheet_Output.png)
