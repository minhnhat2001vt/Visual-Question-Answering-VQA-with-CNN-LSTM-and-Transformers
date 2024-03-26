# Visual-Question-Answering-VQA-with-CNN-LSTM-and-Transformers


Visual Question Answering (VQA) merges Computer Vision and Natural Language Processing to answer questions about images, requiring advanced understanding of both visual content and language context. It's a challenging yet intriguing task in AI.

The goal of this project is to build a VQA model that can take a pair of Image and Question (English) as input, then return the Answer for the Question about the Image.
## Project overview
### 1. Dataset
- This project will use a traffic sign detection dataset that cotains 877 images, each image belong to one class: ’stop’, ’speedlimit’ and ’crosswalk’. Each image also has a bounding box that specify the location of the traffic sign in that image.
### 2. Data pre-processing
- Convert the color space to Grayscale.
- Resize all image to 32x32.
- Extract HOG Features from the image.
- Encode the label (class) of each image with LabelEncoder.
- Split the data into train and test set with 7:3 ratio.
- Normalize the data with StandardScaler.
### 3. Model Training and Evaluating
- Train a SVM model using RBF Kernel
- Evaluate Model performance with accuracy score using the Test set.
- The model achieved 0.978 Accuracy Score on validation (Test) set.
### 4. Object Detection
- Define a sliding window (w, h). Then slide this window through each input pixel of the image from left to right and top to botttom.
- With each slide, input the recorded frame into the sign classification model to determine whether this window contains a traffic sign or not.
- Define a confident thershold, only consider predictions that have at least a prediction probability greater than that thershold. If satisfied, choose the class with the highest probability. If not we skip the current window.
- Visualize all the recorded windows as founded bouding box for the traffic sign.
- Use Non-Maximum Suppression algorithm to eliminate overlapped bouding boxes.
- Return the final bouding box of the traffic sign in the image among with its class.
