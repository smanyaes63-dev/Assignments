# CNN-Based Image Classification using Intel Image Classification Dataset

## Project Overview

This project implements a Convolutional Neural Network (CNN) from scratch to classify natural scene images into six different categories using the Intel Image Classification Dataset.

The model is developed using Python and TensorFlow/Keras. It performs image preprocessing, data augmentation, CNN model training, and performance evaluation.

## Objective

To design, implement, train, and evaluate a CNN model capable of classifying natural scene images into six categories.

## Dataset

**Dataset:** Intel Image Classification Dataset (Kaggle)

The dataset contains natural scene images belonging to six classes:

1. Buildings
2. Forest
3. Glacier
4. Mountain
5. Sea
6. Street

### Dataset Distribution

| Dataset | Number of Images |
|---|---:|
| Training dataset | 14,034 |
| Validation dataset | 2,807 |
| Testing dataset | 3,000 |

The training dataset was divided into 80% training and 20% validation data using stratified splitting.

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Scikit-learn
- Pillow
- Jupyter Notebook


## Data Preprocessing

The following preprocessing techniques were performed:

- Loaded and explored the dataset.
- Converted images into RGB format.
- Resized all images to 150 × 150 pixels.
- Normalized pixel values to the range [0, 1].
- Encoded class labels using LabelEncoder.
- Split the training dataset into training and validation sets.

## Data Augmentation

Image augmentation was applied to improve model generalization and reduce overfitting.

The following techniques were used:

- Rotation (20 degrees)
- Horizontal flipping
- Zooming (0.2)
- Width shifting (0.1)
- Height shifting (0.1)

## CNN Architecture

A Sequential CNN model was developed from scratch using TensorFlow/Keras.

The architecture consists of:

1. Input Layer – 150 × 150 × 3
2. Convolutional Layer – 32 filters
3. Max Pooling Layer
4. Convolutional Layer – 64 filters
5. Max Pooling Layer
6. Convolutional Layer – 128 filters
7. Max Pooling Layer
8. Flatten Layer
9. Fully Connected Dense Layer – 128 neurons
10. Dropout Layer – 0.5
11. Output Layer – 6 neurons with Softmax activation

**Total trainable parameters:** 4,829,126

## Model Training

The model was trained using:

- Optimizer: Adam
- Loss Function: Sparse Categorical Crossentropy
- Evaluation Metric: Accuracy
- Maximum Epochs: 20
- Batch Size: 32
- Early Stopping
- Model Checkpointing

Early stopping was used to prevent unnecessary training and restore the best model weights.

## Model Evaluation

The trained CNN model was evaluated using the separate test dataset containing 3,000 images.

### Test Performance

**Test Accuracy: 84.17%**

**Test Loss: 0.4645**

### Classification Report

| Class | Precision | Recall | F1-Score |
|---|---:|---:|---:|
| Buildings | 0.81 | 0.86 | 0.83 |
| Forest | 0.94 | 0.98 | 0.96 |
| Glacier | 0.83 | 0.78 | 0.80 |
| Mountain | 0.81 | 0.73 | 0.77 |
| Sea | 0.78 | 0.89 | 0.83 |
| Street | 0.88 | 0.84 | 0.86 |

The model achieved its best classification performance on the Forest category, with an F1-score of 0.96.

### Evaluation Techniques

The following evaluation techniques were used:

- Test accuracy and loss
- Precision, Recall, and F1-score
- Confusion Matrix
- Actual vs. Predicted Image Visualization

Ten random test images were visualized to compare their actual labels with the model's predicted labels.

## Model Saving and Loading

The trained model was saved in Keras format:

```text
models/best_cnn_model.keras
```

The saved model can be loaded using:

```python
from tensorflow.keras.models import load_model

loaded_model = load_model('../models/best_cnn_model.keras')
```

## How to Run the Project

### 1. Clone the Repository

```bash
git clone <your-github-repository-link>
```

### 2. Install Dependencies

```bash
pip install tensorflow numpy matplotlib scikit-learn pillow
```

### 3. Download the Dataset

Download the Intel Image Classification Dataset from Kaggle and organize the dataset folders as shown in the project structure.

### 4. Open Jupyter Notebook

Open the project notebook:

```text
notebooks/Intel_CNN_Classification.ipynb
```

### 5. Execute the Notebook

Run the notebook cells sequentially to perform preprocessing, model development, training, and evaluation.

## Conclusion

This project demonstrates the implementation of a CNN-based image classification system using the Intel Image Classification Dataset.

The developed model successfully classifies natural scene images into six categories and achieves **84.17% accuracy** on the test dataset.

The project provided practical experience in deep learning, computer vision, image preprocessing, data augmentation, CNN architecture design, and model evaluation.

## Author

**Smanya E S**

B.Tech – Artificial Intelligence and Data Science
