
# Gender Bias in Coreference Resolution with BERT, CNN and CDA

This repository contains the code for our project on gender bias in coreference resolution. The project evaluates:

- A **rule-based** baseline  
- A **BERT-based** model  
- A **CNN + GloVe** model  

on the **GAP** dataset (and related evaluation sets) with and without **Counterfactual Data Augmentation (CDA)**. 

The notebook computes accuracy/F1 metrics as well as multiple gender bias measures and visualizations.

All experiments are implemented in a single Jupyter notebook intended to run end-to-end in **Google Colab**.

---

## Repository Structure

```text
.
├── README.md
└── CS6120_Project.ipynb      # Main project notebook

```
---

## Dependencies

The notebook is designed to run in **Google Colab** and installs all required Python packages at the top.  
You do **not** need to install anything manually if you use Colab.

Main dependencies (installed automatically inside the notebook):

- `torch`
- `transformers`
- `datasets`
- `evaluate`
- `spacy` (and `en_core_web_sm`)
- `matplotlib`
- `numpy`
- `pandas`

---

## Data

All datasets used in this project are downloaded programmatically inside the notebook.  
No manual dataset download is required.  

The notebook includes code or URLs to download it at runtime.

---

## GloVe Embeddings

The **CNN** model uses **GloVe 6B 100-dimensional embeddings** (`glove.6B.100d.txt`).

You can downlaod it from here: https://drive.google.com/file/d/1H7guLQS3IL6SnEvv-1GszRKnurGne1bG/view?usp=sharing

Before running the notebook:

1. **Download the GloVe file from the drive link**  
   - File: `glove.6B.100d.txt`

2. **Upload the file to your Google Drive root directory**  
   - Place it directly under `My Drive/` (not inside a folder).

3. The notebook expects this file in the root of Google Drive when mounting Drive.  
   - If you change its location, update the file path in the cell that loads GloVe.

---

## How to Run in Google Colab

1. **Open the notebook**

   - Go to [Google Colab](https://colab.research.google.com/).
   - `File` → `Open notebook` → **GitHub** tab.
   - Paste this repository’s URL and open `CS6120_Project.ipynb`.  
     *(Alternatively, download the notebook and upload it manually in Colab.)*

2. **Upload GloVe to Google Drive**

   - Download `glove.6B.100d.txt`
   - Upload it to the **root** of your Google Drive (`My Drive/glove.6B.100d.txt`).

3. **Enable GPU runtime**

   - In Colab: `Runtime` → `Change runtime type` → set **Hardware accelerator** to **GPU** → `Save`.

4. **Run all cells**

   - In Colab: `Runtime` → `Run all`.
   - The notebook will:
     - Install dependencies  
     - Mount Google Drive  
     - Load GloVe embeddings  
     - Download datasets  
     - Train and evaluate:
       - Rule-based model  
       - BERT model (original + CDA)  
       - CNN + GloVe model (original + CDA)  
     - Compute bias metrics and generate plots/tables  

Running all cells with default settings will reproduce the project’s results.

---

