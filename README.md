# joint-detection-using-computer-vision-techniques-and-neural-networks

Osteoarthritis (OA), the most common type of arthritis in humans, is a disease occurring in the knees, hips, and hand joints. Screening and classification of hand A are currently performed manually by a trained radiologist, who marks the finger joints on an X-ray image of the hand, then performs measurements to determine the severity of the disease. The manual labeling process is time-consuming; therefore, automatic computer-aided methods are in need.
In this project, your task is to develop an algorithm that can detect the positions of the twelve joints in each hand X-ray image automatically. The input is an image, and the output of the algorithm is the coordinates of the center of the twelve joints. Used computer vision techniques and convolutional neural network to locate the joints. The whole database contains X-rays, the raw images are in the DICOM format. Each image has its text file describing the labeling information.

## Computer Vision Technique:
Developed a computer vision algorithm that detects the joints based on image features. The features could be edges, shapes, intensity ranges, etc. The image were processed using algorithms such as binarization, morphological operations, edge detection, etc., to locate the joints.
Once edges are detected, contour detection is applied to identify continuous shapes and boundaries within the image. Following this, blob detection is used to locate potential joint regions by identifying areas that meet certain size constraints. These detected blobs serve as candidate joint locations. Each detected keypoint is then processed to extract its coordinates, which represent the center of a potential joint. For visualization, bounding boxes are drawn around these detected regions, and red dots are placed at the center of each detected joint to clearly indicate their positions on the image.
1. Image Preprocessing: 
Adjust contrast (alpha)
Adjust brightness (beta)
Apply Gaussian blur

2. Edge Detection: 
Automatic thresholding using median
Canny Edge Detection

3. Contour Detection: 
Extract contours from edge map

5. Blob Detection (Joint Candidates):
Detect circular/region-based structures

6. Joint Localization:
Extract keypoints (x, y coordinates)
Represent potential joint centers

8. Visualization:
Draw bounding boxes around detected joints
Mark joint centers with red dots

## Convolutional Neural Network
This part of the project focuses on classifying different types of finger joints—Metacarpophalangeal (MCP), Proximal Interphalangeal (PIP), and Distal Interphalangeal (DIP)—from hand X-ray images using a Convolutional Neural Network (CNN). Building upon the earlier computer vision-based joint localization approach, this method leverages supervised learning to classify extracted joint regions automatically. The dataset consists of hand X-ray images along with corresponding annotation text files containing joint labels and their coordinates. These annotations are used to extract fixed-size image patches (32×32 pixels) centered around each joint location, which serve as inputs to the CNN model.

The data preprocessing pipeline begins by matching image files with their corresponding annotation files and splitting the dataset into training and testing subsets. For each annotated joint, a 32×32 grayscale patch is cropped around the provided coordinates. Invalid or improperly sized patches are filtered out to ensure consistency in the dataset. The labels (MCP, PIP, DIP) are encoded using label encoding and further converted into one-hot encoded vectors to support multi-class classification. The input images are reshaped to include a channel dimension, making them compatible with CNN input requirements.

The CNN architecture consists of multiple convolutional and max-pooling layers for feature extraction, followed by fully connected dense layers for classification. Specifically, the model includes two convolutional layers with ReLU activation, each followed by max-pooling to reduce spatial dimensions. The extracted features are flattened and passed through dense layers before the final softmax layer, which outputs probabilities for the three joint classes. The model is compiled using categorical cross-entropy loss and the Adam optimizer, and it is trained over multiple epochs with validation on the test dataset.

### Model Architecture (CNN)
- Input: (32, 32, 1) grayscale images
- Layers:
1. Conv2D (32 filters, 4×4, ReLU)
2. MaxPooling (2×2)
3. Conv2D (32 filters, 4×4, ReLU)
4. MaxPooling (2×2)
5. Flatten
6. Dense (128, ReLU)
7. Dense (32, ReLU)
8. Output Layer (3 neurons, Softmax)
   
### Training
- Loss: categorical_crossentropy
- Optimizer: Adam
- Epochs: 20
- Validation: Test dataset

### Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1 Score
  
### Visualization
- Training vs Validation Loss
- Training vs Validation Accuracy

Dataset:
https://my.sharepoint.com/:f:/g/personal/jshan/EvPv8dKmH_tOmvkBGNsw-gYB7UwR0WZFBXbR3fHmKoxnlg?e=7H26S6
