# Senior-Project
# Protein EC Number Prediction Pipeline

This project builds a machine learning pipeline to predict the first 2 numbers of a protein's Enzyme Commission (EC) Number. It does this by  utilizing a number of protein features 

## Project Overview

The pipeline includes(The files should be executed in the following order_:
- 1 Querying PDB/UniProt to collect protein IDs and metadata (Initial_Compilation.ipynb)
- 2 Extracting structural and physicochemical features (Feature_Extraction.ipynb)
- 3 Gathering motif signatures using PROSITE API and reducing them via PCA (Motif_Extraction.ipynb)
- 4 Standardizing values, formatting the data better, dropping incomplete instances (DataProcessing&Filtering.ipynb)

- Training models (Random Forest & Neural Network) to predict the EC prefix (first two digits of EC number)
- Predicting EC classes for unlabeled proteins
- MLMs
-   RF_Model.ipynb
-   NeuralNetwork-2.ipynb

---

Project Structure

1. Data Collection
- `initialSet.csv` is created by querying PDB for `PDB_ID` and `UniProt_ID`.
- Feature extraction (`Surface_area`, `sequence_length`, etc.) is appended via API calls.
- Motifs are collected from PROSITE and reduced using PCA (10 components).

2. Filtering and Standardization
- Incomplete or `MISSING` EC# entries are removed.
- Numeric features (columns C–N, Q–W) are standardized.
- Motif PCA columns (PC1–PC10) are added.

3. Training Sets
- `PT4_Training.csv`: used for training models.
- `PT4_Prediction.csv`: used to generate predictions. 
