# Intel Image Classification: Vision Transformer vs. Classical ML 🌄🏙️

This repository contains my project for the [Intel Image Classification Challenge on Kaggle](https://www.kaggle.com/datasets/puneet6060/intel-image-classification). The goal of this project is to classify images of natural and urban landscapes into six different categories. 

To solve this, I compared two separate approaches: a modern **Vision Transformer (ViT)** (Deep Learning) and **several classical Machine Learning algorithms**.

## 📊 Dataset Information
The dataset consists of around 25,000 color images (150x150 pixels) divided into the following 6 categories:
* `0` -> Buildings 🏢
* `1` -> Forest 🌲
* `2` -> Glacier 🧊
* `3` -> Mountain ⛰️
* `4` -> Sea 🌊
* `5` -> Street 🛣️

*Note: Due to file size limits, the actual dataset is not included in this repository. You can download it directly from [Kaggle](https://www.kaggle.com/datasets/puneet6060/intel-image-classification).*

## 🧠 Methodology & Architecture

I divided the project into two main parts:

### 1. Deep Learning (Vision Transformer)
Instead of using traditional Convolutional Neural Networks (CNNs), I implemented transfer learning using a pre-trained **Vision Transformer (ViT-B/16)** (ImageNet-1k weights). I froze the feature extraction layers and only trained the final classification head on the 6 new categories. The model was trained using the AdamW optimizer over 20 epochs.

### 2. Classical Machine Learning (ML)
For the traditional ML models, I built a custom feature extraction pipeline. The features were combined from:
* **ResNet-50 (without the classification head):** To extract color and high-level visual information.
* **HOG (Histogram of Oriented Gradients):** To extract edge and texture information.

I then used these combined feature vectors to train three different classical machine learning models:
* Linear Support Vector Machine (Linear SVM)
* RBF Support Vector Machine (RBF-SVM)
* K-Nearest Neighbors (k-NN)
* Random Forest (with 300 trees)

## 🛠️ Tech Stack
* **Python 3**
* **Deep Learning:** PyTorch / Torchvision
* **Machine Learning:** Scikit-Learn (SVC, KNeighborsClassifier, RandomForestClassifier)
* **Image Processing:** Scikit-Image (HOG features, resizing)
* **Data & Visualization:** NumPy, Pandas, Matplotlib, Tqdm

## 📈 Results & Conclusion
Here are the model results on the test dataset:

**Classical Machine Learning (Features via ResNet50 + HOG):**
* Random Forest: 91.70%
* Linear SVM: 90.80%
* k-NN: 92.06% *(However, this had a rather high test loss of 0.74, making its predictions seem a bit uncertain)*

**Deep Learning:**
* **Vision Transformer (ViT-B/16): 92.36%** 🚀

**My Conclusion:**
In the end, the Vision Transformer (ViT) came out on top and delivered the best accuracy. This makes perfect sense for this project: I was working with a dataset of around 15,000 training images. Transformers are extremely data-hungry and can really show their strengths with these kinds of numbers. 

If I had only had a few hundred images available for this project, the results would likely have been different. In that case, the ViT would probably have overfitted quickly, the loss would have increased, and the accuracy would have dropped. For very small datasets, the classical ML models (like SVM or Random Forest) with manual feature extraction would have been the better and more stable choice.


