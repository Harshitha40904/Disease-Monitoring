Title: EfficientNet-B0 and SVM Based Image Classification System

Overview

This project is designed to classify images using a hybrid model that combines a deep learning feature extractor and a traditional machine learning classifier. The pretrained EfficientNet-B0 model is used as a fixed feature extractor to obtain deep feature representations of images, and a Support Vector Machine (SVM) with an RBF kernel is used as the classifier. The integration of these two models allows for high accuracy even with smaller datasets, leveraging the powerful feature learning ability of deep networks and the strong decision-making capability of SVMs.

Models Used

EfficientNet-B0 Feature Extractor

EfficientNet-B0 is a convolutional neural network pretrained on ImageNet. It accepts input images of size 224 by 224 with three color channels. In this project, the final classification layer is removed, and only the convolutional part of the network is used to extract image features. The final output of the model after global average pooling is a 1280-dimensional feature vector for each image.

The architecture of EfficientNet-B0 contains the following main components:

<img width="334" height="151" alt="image" src="https://github.com/user-attachments/assets/283e3c87-7edf-4069-8073-75dd662eab8d" />

Initial convolution layer with batch normalization and SiLU activation.

Multiple MBConv (mobile inverted bottleneck) blocks with varying expansion ratios.

Squeeze and excitation modules that adaptively recalibrate channel-wise feature responses.

Final 1x1 convolution followed by global average pooling producing a 1x1x1280 tensor per image.

The network outputs 1280 feature values that summarize each image’s texture, shape, and color characteristics. These vectors are then used by the SVM for classification.

Support Vector Machine Classifier

The SVM is a supervised learning algorithm used to find optimal decision boundaries between different classes in the feature space. The RBF kernel is used to handle non-linear separations effectively. The SVM model is trained on the extracted features from EfficientNet-B0. The hyperparameters used are C = 10 and gamma = scale, which provide a balanced trade-off between bias and variance.

<img width="271" height="186" alt="image" src="https://github.com/user-attachments/assets/495fb3e2-812f-47d0-91cb-799bc6eb73a1" />


Workflow or Process Flow:


<img width="433" height="1094" alt="image" src="https://github.com/user-attachments/assets/c17d526c-6a63-43ed-919a-9835ea2481f2" />
Data Loading and Preprocessing
The dataset is organized into training and testing folders with subfolders representing different classes. Each image is resized to 224 by 224, converted into a tensor, and normalized using ImageNet mean and standard deviation values.

Feature Extraction
Images are passed through the pretrained EfficientNet-B0 model in evaluation mode. The output feature maps are pooled into 1280-dimensional feature vectors. These vectors along with their labels are stored as training and testing feature datasets.

Model Training
The SVM classifier is trained using the training features. The model learns to separate the feature vectors of different classes using hyperplanes in the high-dimensional space. Training involves fitting the SVM model to the extracted features and optimizing its parameters to minimize classification error.

Model Testing
The test images undergo the same preprocessing and feature extraction steps. The trained SVM predicts the classes of the test samples. Performance metrics such as accuracy, precision, recall, and F1-score are calculated. A confusion matrix is plotted to visualize the correct and incorrect predictions.

Visualization of Predictions
Sample test images are displayed with their predicted and actual labels to visually verify model performance.

Model Saving
The trained SVM model is saved in a serialized form using joblib. Metadata including model name, accuracy, number of classes, and class names are saved in a JSON file for reference and reproducibility.

Training and Testing Process Summary

Stage: Data Loading
Operation: Read and preprocess all images into normalized tensors.
Model Involved: None
Output: Preprocessed image tensors.

Stage: Feature Extraction
Operation: Generate 1280-dimensional deep features from each image.
Model Involved: EfficientNet-B0
Output: Numerical feature vectors.

Stage: Model Training
Operation: Train SVM on extracted features.
Model Involved: SVM (RBF Kernel)
Output: Trained classifier model.

Stage: Evaluation
Operation: Predict test samples and compute performance metrics.
Model Involved: SVM
Output: Accuracy, F1-score, Confusion Matrix.

Stage: Saving
Operation: Save model and metadata for reuse.
Model Involved: SVM
Output: Saved model file and metadata JSON.

Techniques Used

Transfer learning is applied to leverage pretrained EfficientNet-B0 weights for feature extraction.
Feature extraction converts the deep CNN representations into fixed numerical vectors suitable for classical machine learning models.
An RBF kernel SVM is used for nonlinear decision boundaries.
Normalization ensures consistent data scale for all images.
Confusion matrix and classification report are used for quantitative evaluation.
Joblib and JSON are used for model saving and metadata documentation.

Advantages of the Approach

The model avoids retraining a deep CNN from scratch, saving computation time and resources.
SVM provides a strong generalization capability on small datasets.
Transfer learning enhances model performance using pretrained ImageNet features.
The modular pipeline allows flexibility to replace or upgrade either the feature extractor or classifier independently.

System Flow Diagram

<img width="516" height="477" alt="image" src="https://github.com/user-attachments/assets/1394d36f-d285-49db-a0f4-d685ea352367" />

