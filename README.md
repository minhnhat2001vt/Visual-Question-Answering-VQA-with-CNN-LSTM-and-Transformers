# Visual-Question-Answering-VQA-with-CNN-LSTM-and-Transformers


Visual Question Answering (VQA) merges Computer Vision and Natural Language Processing to answer questions about images, requiring advanced understanding of both visual content and language context. It's a challenging yet intriguing task in AI.

The goal of this project is to build a VQA model that can take a pair of Image and Question (English) as input, then return the Answer for the Question about the Image.
## A. Project overview
### 1. Dataset
- The dataset using in this project is derived from the MS COCO (Microsoft Common Objects in Context) validation set: Papers with Code. (n.d.). COCO. Retrieved from https://paperswithcode.com/dataset/coco
- Contains 11820 pair of Images and Questions with binary (yes/no) Answers. Split into Training set (7846 samples), Validation set (1952 samples) and Test set (2022 samples).
- Dataset download at: https://drive.google.com/file/d/15HaVEgNQ2lB-effZ6snJshO3lja-0SCQ/view?usp=sharing
### 2. CNN + LSTM Model
- Feature extraction: ResNet network pre-trained network is ultilized to extract features from the Image. For the Text (Question and Answer), the features are extracted using a Bi-LSTM network.
- Feature combination: After the extraction phase, these features will be transformed into a 1024-dimensional vector via a fully connected layer. These vectors will then be aggerated via element-wise multiplication, creating a unified representation of both modalities.
- Classification: The combined features pass through layers (fully connected, ReLU, Dropout) and culminate in a final fully connected layer that predicts the answer from predefined classes.
### 3. Transformer Model
- Image extraction with transfer learning: Vision Transformer (ViT) pre-trained model is used to encode images.
- Text extraction with transfer learning: Employs a RoBERTa model to encode text questions.

## B. Result
### CNN + LSTM: achieved 0.55 accuracy on Test set.
### ViT + RoBERTa : achieved 0.67 accuracy on Test set.

## C. References
- He, K., Zhang, X., Ren, S., & Sun, J. (2016). Deep residual learning for image recognition. Proceedings of the IEEE conference on computer vision and pattern recognition (pp. 770-778).
- Graves, A., & Schmidhuber, J. (2005). Framewise phoneme classification with bidirectional LSTM and other neural network architectures. Neural Networks, 18(5-6), 602-610.
- Dosovitskiy, A., Beyer, L., Kolesnikov, A., Weissenborn, D., Zhai, X., Unterthiner, T., ... & Houlsby, N. (2021). An image is worth 16x16 words: Transformers for image recognition at scale. Proceedings of the International Conference on Learning Representations.
- Liu, Y., Ott, M., Goyal, N., Du, J., Joshi, M., Chen, D., Levy, O., Lewis, M., Zettlemoyer, L., & Stoyanov, V. (2019). RoBERTa: A Robustly Optimized BERT Pretraining Approach. arXiv preprint arXiv:1907.11692.
