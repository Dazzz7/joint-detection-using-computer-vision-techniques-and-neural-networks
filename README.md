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

## C


Train a machine learning method for object detection. A pre-labeled dataset will be provided, and you can use it to train the model to detect the joints.

https://my.sharepoint.com/:f:/g/personal/jshan_pace_edu/EvPv8dKmH_tOmvkBGNsw-gYB7UwR0WZFBXbR3fHmKoxnlg?e=7H26S6
