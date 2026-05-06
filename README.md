# Scenicness Prediction Using CLIP Embeddings, PCA, and Regression Modeling

This repository contains the full implementation of a GeoAI-based scenicness prediction pipeline. 
The project extracts CLIP embeddings from street-level images, applies Principal Component Analysis (PCA) 
to reduce dimensionality, and trains regression models to predict scenicness scores. The workflow supports 
the analysis and mapping of scenicness across Washington, DC.

The code and notebooks in this repository were developed as part of a Master's thesis in Big Data Analytics & GeoAI.


## Repository Structure

This repository includes the following key components:

- **embeddings/**  
  Directory containing CLIP embeddings for each image (512-dimensional vectors).

- **DC_images/**  
  Folder containing the street-level images used in the analysis (or sample images if full dataset is stored externally).

- **GPT_Scenicness_Score.ipynb**  
  Notebook used to generate scenicness labels using GPT-based scoring.

- **Notebook 01: Extract Embeddings.ipynb**  
  Extracts CLIP embeddings from the image dataset.

- **Notebook 02_PCA_Embeddings.ipynb**  
  Performs PCA on the embeddings and generates reduced-dimensionality features.

- **Notebook 03: Regression Modeling.ipynb**  
  Trains regression models (e.g., Lasso, Ridge, Random Forest) to predict scenicness scores.

- **scenicness_dataset.csv**  
  Raw dataset containing image metadata and scenicness scores.

- **scenicness_dataset_with_pca.csv**  
  Dataset after PCA transformation, used for modeling.



##  Workflow Overview

### **1. Extract CLIP Embeddings**
Run:
- `Notebook 01: Extract Embeddings.ipynb`

This notebook processes each image and generates a 512-dimensional CLIP embedding.

---

### **2. Dimensionality Reduction (PCA)**
Run:
- `Notebook 02_PCA_Embeddings.ipynb`

This notebook:
- Centers the embeddings  
- Computes the covariance matrix  
- Performs PCA  
- Reduces 512 dimensions to 50 components  
- Preserves ~92% of total variance  

---

### **3. Regression Modeling**
Run:
- `Notebook 03: Regression Modeling.ipynb`

This notebook trains multiple regression models to predict scenicness scores using PCA components.

Models include:
- Linear Regression  
- Lasso  
- Ridge  
- Random Forest  

Performance is evaluated using R², RMSE, and cross-validation.


### **4. GPT-Based Scenicness Scoring**
- `GPT_Scenicness_Score.ipynb`  
  Generates scenicness labels using GPT-based evaluation of image content.


### **Scenicness Dataset**
- `scenicness_dataset.csv` — raw dataset  
- `scenicness_dataset_with_pca.csv` — PCA-transformed dataset  

### **Image Dataset (Google Drive)**  
Due to storage constraints, the full image dataset is stored in Google Drive.
Link: https://drive.google.com/drive/folders/1piBn8GWg6552aVoGdpLM5ScekC9OmMa?
usp=sharing

If public:
