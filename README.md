# Deepfake Detection with Machine Learning and Neural Networks

## 📌 Project Overview

This project focuses on detecting **deepfake images**—AI-generated media designed to appear real—using various machine learning models. Deepfakes pose serious threats by spreading misinformation, damaging reputations, and facilitating identity-based fraud. Our goal was to evaluate and compare different detection models in terms of **accuracy, training time, and usability**, and to provide a simple **user interface** for hands-on experimentation.

## Team Members

* Abdul Rehman
* Alex Busch
* Ritvik Roy
* Sharath Rigvedi

## Models Used

We trained and tested the following models for binary classification (real vs fake images):

| Model                          | Accuracy   | Time to Fit |
| ------------------------------ | ---------- | ----------- |
| Neural Network (NN)            | **88.55%** | 99s         |
| Support Vector Machine (SVM)   | 72.71%     | 492s        |
| Deep Neural Network (Xception) | 57.76%     | \~600s      |
| Random Forest (RF)             | 82%        | 977s        |

### Summary:

* **Neural Network**: Best balance of speed and performance.
* **Random Forest**: Second-best accuracy but longest training time.
* **SVM**: Simple but not scalable to large data or high dimensions.
* **Xception (DNN)**: Advanced but computationally expensive and impractical in limited-resource settings like Google Colab.

## 📊 Dataset

We used the **CIFAKE dataset** from Kaggle:
🔗 [CIFAKE Dataset on Kaggle](https://www.kaggle.com/datasets/birdy654/cifake-real-and-ai-generated-synthetic-images)

* 120,000 total images (60K real + 60K deepfake)
* Synthetic and clean, requiring minimal preprocessing

## 🔍 Preprocessing Steps

* **Resizing**: All images resized to match model input requirements (e.g., 299x299 for Xception).
* **Minimal Cleaning**: Dataset was already curated.
* **Feature Extraction for SVM**: Extracted color histograms, texture, and edges manually.

## 💻 User Interface

We developed a lightweight **UI in Google Colab** for each model using streamlit. Users can upload an image, classify it as real/fake, and view the model’s confidence score.

### How to Use the UI:

1. Run all cells in the Colab notebook.
2. Use `!wget -O - ipv4.icanhazip.com` to get the IP address (used as the UI password).
3. Click the final cell’s link to open the UI.
4. Input the IP address to access.
5. Upload an image and press **"Classify Image"**.

---

## 🔗 Live Demo Links

| Model                       | Notebook                                                                              | UI                                                                                          |
| --------------------------- | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Neural Network              | [Notebook](https://colab.research.google.com/drive/1i5apqXrQBj2LUBp1xIjvoe0m4GPE0x2G) | [UI](https://colab.research.google.com/drive/1StThylULgIMTUjlrH68oNXT4VmEz03bt)             |
| Neural Network (Pretrained) | [Notebook](https://colab.research.google.com/drive/137AJu_pq2yL5N9Y3jIhkygYyrxiEwP5V) | [UI](https://colab.research.google.com/drive/137AJu_pq2yL5N9Y3jIhkygYyrxiEwP5V?usp=sharing) |
| SVM                         | [Notebook](https://colab.research.google.com/drive/1y_fd9n2D6-4zTTmLliMswRTll3CKj2Am) | [UI](https://colab.research.google.com/drive/1vn5X8s6l0SKVI_lT06ilY8w_7xv_DIaE)             |
| Random Forest               | [Notebook](https://colab.research.google.com/drive/1UmnV4i8xTt2kuGLO4ecJsTVqlyIhPpsk) | [UI](https://colab.research.google.com/drive/16jS6wl_e28P5kN0KMgjid3DtwwmNUHQB?usp=sharing) |
| Xception (DNN)              | [Notebook](https://colab.research.google.com/drive/18O5obxanKjifDqV3kubPD1kdJIk0R8Wf) | [UI](https://colab.research.google.com/drive/1YuSltSS0gFYPW4i3tCmM2AT_ywJgkW3C?usp=sharing) |

---

## 🧩 Future Improvements

* Use **ImageNet** or larger real-world datasets for better generalization.
* Optimize the training process with **TPUs/GPUs**.
* Implement **real-time video deepfake detection**.
* Add ensemble methods or transformers for improved detection.
