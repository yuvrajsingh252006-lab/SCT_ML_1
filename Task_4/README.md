# SCT_ML_4 — Hand Gesture Recognition

## 📌 Overview
This project develops a **hand gesture recognition model** capable of identifying and classifying different hand gestures from image data, with a pathway to real-time video/webcam use for gesture-based human-computer interaction. It was completed as **Task 4** of the Machine Learning internship track.

Hand gesture recognition is a core building block of intuitive, touchless control systems — used in applications ranging from sign language interpretation to controlling smart devices, presentations, and games without physical contact.

## 🎯 Objective
Build a multi-class classifier that can accurately distinguish between different hand gestures (e.g. palm, fist, thumbs up, peace sign, OK sign) from image data, and outline how this can be extended to real-time gesture-based control.

## 🗂️ Dataset
This project is designed for Kaggle's **["LeapGestRecog"](https://www.kaggle.com/datasets/gti-upm/leapgestrecog)** dataset — a near-infrared image dataset containing ~20,000 images across 10 gesture classes, performed by 10 different subjects.

After downloading and extracting, the folder structure looks like:
```
leapGestRecog/
  00/
    01_palm/*.png
    02_l/*.png
    ...
  01/
    01_palm/*.png
    ...
```

The notebook includes ready-to-use loading code for this exact structure. For demonstration purposes without requiring a download, the notebook also includes a synthetic gesture image generator covering 5 representative gesture classes: **palm, fist, thumbs_up, peace, ok**.

## 🛠️ Tools & Libraries
- **Python 3**
- **NumPy** — numerical computations
- **Matplotlib** — visualization
- **OpenCV (cv2)** — image/video loading and processing (including webcam extension)
- **scikit-image** — HOG (Histogram of Oriented Gradients) feature extraction
- **scikit-learn** — `SVC`, `RandomForestClassifier`, `LabelEncoder`, scaling, evaluation metrics

## 🔍 Project Workflow
1. **Data Loading** — Load labeled gesture images across multiple classes.
2. **Preprocessing** — Resize to a consistent size and convert to grayscale.
3. **Feature Extraction (HOG)** — Extract shape/edge-based features suited for classical ML classifiers.
4. **Train/Test Split & Scaling** — Split 80/20 and standardize features.
5. **Model Training & Comparison** — Train both an **SVM** and a **Random Forest** classifier, then select whichever performs better.
6. **Evaluation** — Assess with per-class precision/recall/F1-score and a multi-class confusion matrix.
7. **Prediction** — Classify a new gesture image.
8. **Real-Time Extension** — Full example code for running the trained model on a live webcam feed using OpenCV, enabling true gesture-based control.

## 📊 Results
On the synthetic demonstration data, both models achieve 100% accuracy — an artifact of the artificially distinct placeholder shapes used for demonstration.

**On the real LeapGestRecog dataset**, a HOG + SVM/Random Forest pipeline typically achieves **85–98% accuracy**, since the dataset is captured under controlled, consistent conditions (fixed camera, consistent lighting, plain background) — making it well-suited to classical ML methods.

## 🚀 How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/SCT_ML_4.git
   cd SCT_ML_4
   ```
2. Download the real dataset from [Kaggle LeapGestRecog](https://www.kaggle.com/datasets/gti-upm/leapgestrecog) and extract it into the project folder.
3. Open the notebook:
   ```bash
   jupyter notebook hand_gesture_recognition.ipynb
   ```
   Or upload it to [Google Colab](https://colab.research.google.com/) (note: the real-time webcam section requires a local environment with camera access, not Colab).
4. Replace the synthetic data cell with the real image-loading code (included and commented in the notebook).
5. Run all cells in order.
6. (Optional) Run the real-time webcam demo code locally to see live gesture recognition in action.

## 📁 Project Structure
```
SCT_ML_4/
│
├── hand_gesture_recognition.ipynb   # Main notebook
└── README.md                        # Project documentation
```

## 🧠 Key Learnings
- How to build a multi-class (not just binary) image classification pipeline
- How to compare multiple models (SVM vs Random Forest) and select the best performer objectively
- How HOG features generalize well to hand-shape-based classification tasks
- How to extend a static-image classifier into a real-time, webcam-based recognition system
- Why datasets like LeapGestRecog (controlled conditions) are easier for classical ML than in-the-wild images

## 🔮 Future Improvements
- Train and evaluate on the full real LeapGestRecog dataset for a genuine accuracy benchmark
- Add **MediaPipe Hands** for robust hand detection/cropping before classification, especially for cluttered real-world backgrounds
- Try a CNN or a lightweight deep learning model (e.g. MobileNet) for potentially higher accuracy on messier real-world images
- Expand to all 10 gesture classes in the original LeapGestRecog dataset
- Build a small interactive application (e.g. controlling a slideshow or volume) using the real-time webcam recognition as a proof of concept

## 📄 License
This project is open-source and available for learning purposes.

## 🙋 Author
Completed as part of a Machine Learning internship task.
