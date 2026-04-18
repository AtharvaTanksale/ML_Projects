# Rice Grain Image Classification 🌾

A straightforward Machine Learning project that classifies images of rice grains (Arborio vs. Basmati) using Python, OpenCV, and K-Nearest Neighbors (KNN).

## 📌 Overview
This script automatically downloads a dataset of rice images, processes them to extract physical shapes (Area, Perimeter, Eccentricity, Compactness), and trains a machine learning model to tell them apart with **97.5% accuracy**.

## ✨ Features
* **Automated Dataset:** Uses `kagglehub` to grab the images for you instantly.
* **Computer Vision:** Uses OpenCV to trace the geometric outline of each grain of rice.
* **Machine Learning:** Uses Scikit-Learn (KNN) to classify the grains without deep learning.
* **Visual Output:** Pops up a side-by-side graphical comparison of its final prediction.

## 🛠️ Setup & Installation
1. Make sure you have Python installed.
2. Install the required libraries by running this command in your terminal:
   ```bash
   pip install opencv-python numpy pandas scikit-learn matplotlib kagglehub
