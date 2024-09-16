#Image Retrieval Using ResNet50

This project implements an image retrieval system that uses ResNet50 for feature extraction from images. The system compares the similarity between query images and a gallery of images using cosine similarity. It was developed in Google Colab using Python, TensorFlow, and Keras.

Table of Contents:
Overview
Installation
Project Structure
Dataset
Methodology
Usage
Results
Acknowledgments


**Overview**
The goal of this project is to build an image retrieval system that takes a query image, extracts its features using a pre-trained ResNet50 model, and finds similar images from a gallery by calculating cosine similarity.

The main steps involved are:

Loading images from query and gallery datasets.
Preprocessing the images and extracting features using ResNet50.
Calculating cosine similarity between query and gallery images.
Ranking the gallery images based on similarity to the query.

**Installation**
To run this project in Google Colab or your local environment, follow the steps below:

Mount your Google Drive (if using Google Colab) to access the datasets:
from google.colab import drive
drive.mount('/content/drive')

Install the necessary dependencies:
!pip install --upgrade keras tensorflow opencv-python

Clone this repository to your local machine or Google Colab environment:
git clone https://github.com/yourusername/your-repo-name.git



**Project Structure**

├── competition_data/
│   ├── query/          # Folder containing query images
│   └── gallery/        # Folder containing gallery images
├── main.ipynb          # Jupyter notebook with code for the project
├── README.md           # Project documentation
└── requirements.txt    # List of dependencies

**Dataset**
/competition_data/
    ├── query/
    └── gallery/

**Methodology**

-Feature Extraction:
We use a pre-trained ResNet50 model, removing the top fully connected layers to get a feature vector of each image.
Images are resized to (224, 224) and preprocessed using the preprocess_input function.
-Similarity Calculation:
The cosine similarity between the feature vectors of query and gallery images is computed.
The results are ranked based on similarity scores, where a higher cosine similarity indicates more similarity.

**Usage**
1) Run the Notebook: Execute the Jupyter notebook (main.ipynb) to process the images and retrieve similar images based on the query.

2) Feature Extraction and Similarity Calculation: The notebook will:
       Load images from the /query and /gallery folders.
       Extract features using the ResNet50 model.
       Calculate cosine similarity between the query and gallery images.
      Display the most similar images.
3) Modify for Your Own Data: You can modify the image paths or use a different feature extractor model (e.g., VGG19, Xception).


**Results**
The system outputs the gallery images ranked by their similarity to the query image. The closer the cosine similarity score is to 1, the more similar the images are.

Sample output can look like this:

Query Image >	Similar Image 1, 	Similar Image 2	, Similar Image 3

**Acknowledgments**
The project uses the pre-trained ResNet50 model from the Keras Applications module.
This work was conducted using Google Colab for accessing datasets and training the model.
