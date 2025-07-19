# Transfer Learning-Based Poultry Disease Classification System

A deep learning-powered web application for poultry disease detection, leveraging transfer learning to classify images into disease categories. Farmers, veterinarians, and researchers can upload chicken images and receive instant predictions via a modern Flask-based web interface.

---

## 🖼️ Project Preview

<!-- Row 1 -->
<p align="center">
  <img src="static/assests/image1.jpg" alt="Coccidiosis Example" width="45%" style="margin: 10px;" />
  <img src="static/assests/image2.jpg" alt="Chicken Disease Example" width="45%" style="margin: 10px;" />
</p>

<!-- Row 2 -->
<p align="center">
  <img src="static/assests/image3.jpg" alt="Healthy Chicken" width="45%" style="margin: 10px;" />
  <img src="static/assests/image4.jpg" alt="Poultry Farm" width="45%" style="margin: 10px;" />
</p>

---

##  🎥 Live Demo Video

Watch the demo of the Poultry Disease Classification app in action!

[![Poultry Disease Classification Demo]()](https://youtu.be/your-demo-link)

---

## 📌 Features

- 🧠 Built with **Transfer Learning** using EfficientNetB3 (Keras/TensorFlow)
- 🐔 Classifies chicken images into 4 categories:
  - Salmonella
  - New Castle Disease
  - Coccidiosis
  - Healthy
- 🖼️ Upload an image and get predictions instantly
- 📊 Shows classification results with confidence score
- 📄 Model training code available in `chicken-disease.ipynb`
- 💻 Modern UI with navbar, image gallery, and responsive design

---

## 🛠️ Project Development Process

### 1. Dataset Collection & Preparation

- The dataset is divided into four folders: `Salmonella`, `NewCastleDisease`, `Coccidiosis`, and `Healthy`.
- Each folder contains images of chickens in different health states, captured in similar conditions.
- Directory structure allows for **automatic labeling** using Keras `ImageDataGenerator`.

> **Structure:**
> ```
> dataset/
> ├── Salmonella/
> ├── NewCastleDisease/
> ├── Coccidiosis/
> └── Healthy/
> ```

---

### 2. Data Preprocessing

- Images were resized to `(224x224)` to match EfficientNetB3 input requirements.
- Pixel values normalized to `[0, 1]`.
- Data split into **training** and **validation** sets (80:20).
- Data augmentation (rotation, zoom, flips) used to improve generalization and reduce overfitting.

---

### 3. Model Building Using Transfer Learning

- **EfficientNetB3** pre-trained on ImageNet used as the base model.
- Custom classification head added for 4 poultry disease classes.
- Model compiled with:
  - `Adam` optimizer
  - `categorical_crossentropy` loss
  - `accuracy` metric

- Training performed with Keras `model.fit()`, using callbacks like `EarlyStopping` for optimal results.

---

### 4. Model Evaluation

- Training and validation accuracy/loss visualized.
- Classification report generated: precision, recall, F1-score for each class.
- Confusion matrix and sample predictions used to analyze model strengths and weaknesses.

---

### 5. Model Saving

- Trained model saved as `chicken_model.keras` (Keras format).
- Note: Large model files are not uploaded to GitHub due to size restrictions; see repo note.

```python
model.save("model/chicken_model.keras")
```

---

## ⚙️ Installation & Run Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/UshaButi/Transfer-learning-based-poultry-disease-classification-system.git
cd Transfer-learning-based-poultry-disease-classification-system
```

### 2. Setup Python Environment

```bash
python -m venv tfenv
source tfenv/bin/activate        # For Linux/Mac
tfenv\Scripts\activate           # For Windows
```

### 3. Install Required Packages

```bash
pip install -r requirements.txt
```

### 4. Run the Application

```bash
python app.py
```

- Access the app at `http://127.0.0.1:5000/`
- Click "GET STARTED", upload your poultry image, and view prediction results!

---

## 📂 Folder Structure

```
Transfer-learning-based-poultry-disease-classification-system/
│
├── app.py                  # Flask web application
├── chicken-disease.ipynb   # Model training notebook
├── README.md               # Project documentation
│
├── model/
│   ├── chicken_model.keras # Trained model file
│   └── efficientnetb3-Chicken-Disease.h5 # Original model format
│
├── static/
│   ├── style.css           # Custom styles
│   └── assests/            # UI images
│       ├── image1.jpg
│       ├── image2.jpg
│       ├── image3.jpg
│       └── image4.jpg
│
├── templates/
│   └── index.html          # Main HTML template
```

---

## 🏆 Credits

Project developed as part of SmartInternz assignment  
Team Members: Sundara Himaja, Turpati Nikhil Kumar
, Usha, Penumatcha Satya Sai Shivani


---

## 📄 References

- EfficientNetB3 Paper: https://arxiv.org/abs/1905.11946
- Keras Documentation: https://keras.io/
- Flask Documentation: https://flask.palletsprojects.com/
- [Project Demo](https://youtu.be/your-demo-link)
- [GitHub Repository](https://github.com/UshaButi/Transfer-learning-based-poultry-disease-classification-system)
