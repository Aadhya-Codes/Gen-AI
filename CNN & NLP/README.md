# 1) CNN Image Classification using MNIST

## 📌 Project Overview

This project implements a **Convolutional Neural Network (CNN)** using PyTorch to classify handwritten digits from the **MNIST dataset**.

The model learns patterns such as edges, shapes, and textures in images to accurately predict digits from **0 to 9**.

---

## 📂 Dataset

We use the **MNIST dataset**, which contains:

* 60,000 training images
* 10,000 testing images
* Grayscale images of size **28×28 pixels**
* 10 classes (digits 0–9)

---

## ⚙️ Features Implemented

✅ Data loading and preprocessing
✅ CNN model with:

* 2 Convolutional layers
* ReLU activation
* Max Pooling
* Dropout regularization
* Fully connected layers


---

## 🧠 Model Architecture

```
Input (1 × 28 × 28)
   ↓
Conv2D (32 filters) + ReLU
   ↓
MaxPooling
   ↓
Conv2D (64 filters) + ReLU
   ↓
MaxPooling
   ↓
Flatten
   ↓
Fully Connected Layer (128 neurons)
   ↓
Dropout
   ↓
Output Layer (10 classes)
```

---

## 🚀 Google Colab Notebook 
https://colab.research.google.com/drive/1q4tH_OR_hSnfnI2Y1iwVk6IIWk6H2Tej#scrollTo=0OvwkCmkpyhL

---

## 📊 Training

The model is trained using:

* Loss Function: CrossEntropyLoss
* Optimizer: Adam
* Learning Rate: 0.001 (tunable)
* Epochs: 5

---

## 📈 Results

Typical performance:

* Training Accuracy: ~98–99%
* Test Accuracy: ~97–99%

(Results may vary based on hyperparameters)

---

## 📉 Confusion Matrix

A confusion matrix is generated to evaluate predictions across all classes.

It helps identify:

* Misclassified digits
* Model weaknesses

---

## 🔧 Hyperparameter Tuning

You can improve performance by modifying:

| Parameter         | Effect                                                   |
| ----------------- | -------------------------------------------------------- |
| Number of filters | More filters → better feature extraction but higher cost |
| Kernel size       | Larger kernels capture broader features                  |
| Dropout           | Reduces overfitting                                      |
| Learning rate     | Controls training speed                                  |

---

## ❓ Key Concepts

### Why CNN instead of Fully Connected?

CNNs preserve spatial relationships in images and require fewer parameters, making them more efficient and accurate.

### Role of Pooling

Pooling reduces feature map size and keeps important information, improving efficiency.

### Increasing Filters

More filters allow the model to learn more features but increase computation and risk of overfitting.

### Dropout

Dropout randomly disables neurons during training, preventing overfitting and improving generalization.

---

## 🧪 Future Improvements

* Use CIFAR-10 dataset (color images)
* Add more convolution layers
* Use Batch Normalization
* Try different optimizers (SGD, RMSprop)
* Data augmentation

---

## 📌 Conclusion

This project demonstrates how CNNs effectively classify images by learning hierarchical features. It provides a strong foundation for more advanced deep learning models.

---

# 2) Sentiment Analysis using NLP

This project builds a **Sentiment Analysis model** that classifies text into:
- 😊 Positive  
- 😐 Neutral  
- 😡 Negative  

It uses both **Machine Learning** and **Deep Learning (LSTM)** approaches.

---

## 🚀 Project Overview

This project covers the full NLP pipeline:
- Text preprocessing
- Feature extraction (BoW, TF-IDF)
- Model training (ML + DL)
- Evaluation and visualization

---

## 📁 Dataset

Dataset used: **Twitter Sentiment Dataset (HuggingFace)**

Labels:
- `0 → Negative`
- `1 → Neutral`
- `2 → Positive`

---
## Google Colab Notebook
https://colab.research.google.com/drive/1giShfKpKxcDk8YumheiSp08H4PZXXRG9#scrollTo=OyKn7_-3ujMI

## ⚙️ Workflow

### 1. 🧹 Text Preprocessing
- Convert to lowercase
- Remove URLs, mentions, hashtags
- Remove punctuation & numbers
- Tokenization
- Stopword removal
- Lemmatization

---

### 2. 🔢 Feature Extraction

#### ✔ Bag of Words (BoW)
- Converts text into frequency vectors

#### ✔ TF-IDF
- Weighs words based on importance

#### ⭐ Deep Learning Input
- Tokenization + Padding

---

### 3. 🤖 Models Used

#### Machine Learning:
- Logistic Regression
- Naive Bayes

#### Deep Learning:
- LSTM (Long Short-Term Memory)

---

### 4. 📈 Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

---

## 📊 Visualizations

- 🌥 Word Cloud (most frequent words)
- 🔥 Confusion Matrix
- 📉 Training graphs (LSTM)

---


## 🛠 Tech Stack

- Python
- Pandas, NumPy
- NLTK
- Scikit-learn
- TensorFlow / Keras
- Matplotlib, Seaborn
- WordCloud

---

## 📜 License

This project is open-source and free to use for educational purposes.
