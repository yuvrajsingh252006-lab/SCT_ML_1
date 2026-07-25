# SCT_ML_3 — Cat vs Dog Image Classification using SVM

## 📌 Overview
This project implements a **Support Vector Machine (SVM)** to classify images of cats and dogs, using the Kaggle **"Dogs vs. Cats"** dataset. It was completed as **Task 3** of the Machine Learning internship track.

SVMs are powerful classical machine learning models that work by finding the optimal boundary (hyperplane) that best separates classes in feature space. While deep learning (CNNs) is the modern standard for image classification, this project demonstrates that classical ML — paired with the right feature extraction technique — is still a valid and instructive approach to computer vision tasks.

## 🎯 Objective
Build a binary image classifier that can distinguish between images of cats and dogs.

## 🗂️ Dataset
This project is designed for Kaggle's **["Dogs vs. Cats"](https://www.kaggle.com/c/dogs-vs-cats/data)** dataset, which contains 25,000 labeled images of cats and dogs.

To download it:
```bash
kaggle competitions download -c dogs-vs-cats
```
After extraction, the folder structure looks like:
```
train/
  cat.0.jpg, cat.1.jpg, ...
  dog.0.jpg, dog.1.jpg, ...
```

The notebook includes ready-to-use loading code for this exact folder structure — you only need to update the file path. For demonstration purposes without requiring a download, the notebook also includes a synthetic image generator that produces simplified cat-like and dog-like shapes.

## 🛠️ Tools & Libraries
- **Python 3**
- **NumPy** — numerical computations
- **Matplotlib** — visualization
- **OpenCV (cv2)** — image loading, resizing, color conversion
- **scikit-image** — HOG (Histogram of Oriented Gradients) feature extraction
- **scikit-learn** — `SVC` (Support Vector Classifier), scaling, evaluation metrics

## 🔍 Project Workflow
1. **Data Loading** — Load and label cat/dog images.
2. **Preprocessing** — Resize all images to a consistent size (64×64) and convert to grayscale.
3. **Feature Extraction (HOG)** — Extract Histogram of Oriented Gradients features, which capture edge orientation and shape information — far more effective for SVMs than raw pixel values.
4. **Train/Test Split & Scaling** — Split data 80/20 and standardize features.
5. **Model Training** — Train an SVM classifier with an RBF kernel.
6. **Kernel Comparison** — Compare linear, RBF, and polynomial kernels to justify the final model choice.
7. **Evaluation** — Assess performance using accuracy, a full classification report (precision/recall/F1), and a confusion matrix.
8. **Prediction** — Classify a new, unseen image.

## 📊 Results
On the synthetic demonstration data, the model achieves 100% accuracy — however, this is because the placeholder shapes are artificially distinct, not representative of real photo complexity.

**On the real Kaggle dataset**, a classical HOG + SVM approach typically achieves **65–85% accuracy**, which is a realistic and valid benchmark for this method (compared to 95%+ typically achieved by CNN-based deep learning approaches).

## 🚀 How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/SCT_ML_3.git
   cd SCT_ML_3
   ```
2. Download the real dataset from [Kaggle Dogs vs. Cats](https://www.kaggle.com/c/dogs-vs-cats/data) and extract it into the project folder.
3. Open the notebook:
   ```bash
   jupyter notebook svm_cat_dog_classifier.ipynb
   ```
   Or upload it to [Google Colab](https://colab.research.google.com/).
4. Replace the synthetic data cell with the real image-loading code (included and commented in the notebook).
5. Run all cells in order.

## 📁 Project Structure
```
SCT_ML_3/
│
├── svm_cat_dog_classifier.ipynb   # Main notebook
└── README.md                      # Project documentation
```

## 🧠 Key Learnings
- How classical machine learning (non-deep-learning) approaches can still tackle image classification tasks
- Why raw pixel values are a poor feature representation for classical models, and how HOG solves this
- The importance of feature scaling for margin-based classifiers like SVM
- How different SVM kernels (linear, RBF, polynomial) affect performance
- How to evaluate a classifier using more than just accuracy — precision, recall, F1-score, and confusion matrices matter especially when classes could be imbalanced

## 🔮 Future Improvements
- Train and evaluate on the full real Kaggle dataset (25,000 images) for a genuine accuracy benchmark
- Compare against a Convolutional Neural Network (CNN) using TensorFlow/Keras or PyTorch, to see the real gap in accuracy between classical ML and deep learning for image tasks
- Try other feature extraction techniques (SIFT, ORB, color histograms) and compare
- Use `GridSearchCV` to systematically tune `C` and `gamma` hyperparameters

## 📄 License
This project is open-source and available for learning purposes.

## 🙋 Author
Completed as part of a Machine Learning internship task.
