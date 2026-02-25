# **Lung Cancer Classification**

### This project dives deep into the world of AI-driven lung cancer diagnosis, using **CT scan data** to classify pulmonary nodules as benign or malignant.  
#### The data comes from the LIDC-IDRI collection — [https://wiki.cancerimagingarchive.net/display/Public/LIDC-IDRI](https://wiki.cancerimagingarchive.net/display/Public/LIDC-IDRI) — one of the most detailed open radiology datasets available.  
#### This will give you access to several files, from CSVs with information about diagnoses, the number of nodules in each patient, and notes about the nodules, to full CT scans.

<br>

## **Our goal**

#### To evaluate how different **machine learning models** and **feature selection techniques** perform when applied to **radiomic features** from medical imaging.  
#### Some of the implemented methods were adapted from **well-established studies** and **previous research** in lung cancer analysis, referenced throughout the report.

<br>

## **Requirements:**

    - Python  
    - Numpy → version ~= 1.26.9  
    - Matplotlib → version ~= 3.9.4 
    - Pandas → version ~= 2.3.2  
    - Pylidc → version ~= 0.2.3  
    - Pydicom → version ~= 2.4.4  
    - Pyradiomics → version ~= 3.1.0  
    - Scikit-image  
    - Scipy  
    - Scikit-learn  
    - Seaborn  
    - SimpleITK   
    - XGBoost  
    - tqdm  
    - shutil  

<br>

## **Image Pre-Processing and Feature Extraction**

Images were pre-processed and standardized to **Hounsfield Units (HU)** before extracting features with **PyRadiomics**.  
We performed both 2D and 3D feature extraction:
- **2D**: For each nodule, a single axial slice was selected based on the region of largest cross-sectional area.
- **3D**: full volumetric segmentation of the nodule.

<br>

## **Models and Results Comparison**

Once we had the features, we tested different models and feature selection methods as follows:

### **Models**
- Support Vector Machine (SVM)  
- Random Forest  
- XGBoost  

### **Feature Selection**
- Without feature selection  
- LASSO (L1 Logistic Regression)  
- Recursive Feature Elimination (RFE)  
- SVM-based selection  

<br>

### **Evaluation and Statistical Analysis**

We applied every feature selection method to each of the proposed models for both 2D and 3D radiomic datasets.  
To understand which configuration performed best, we conducted several statistical comparisons:

- **Between different models (same feature selection)** → ANOVA test + Tukey’s post-hoc comparison  
- **Between different feature selection methods (same model)** → ANOVA test + Tukey’s post-hoc comparison  
- **Between 2D and 3D** → Paired samples *t*-test  

<br>

## **About the repository**

- **LabIACD_20252026_project1.pdf** → Project statement  
- **T1_LabIACD_Project1.pdf** → Additional information about the project  
- **Notebook_Final.pdf** → The project in PDF format  
- **Notebook_Final.ipynb** → The project in Jupyter Notebook format  
- **Implicações éticas e legais no diagnóstico de cancros de pulmão.pdf** → Discussion on the ethical and legal implications of using AI in lung cancer detection  
- **datasets/** → Folder with the created datasets  
- **Filtragem_CT_Scans_Metadata.ipynb** → Script that checks whether a folder contains DICOM files with `Modality = 'CT'`

<br>

## **Link to the course**

This course is part of the **first semester** of the **third year** of the **Bachelor’s Degree in Artificial Intelligence and Data Science** at **FCUP** and **FEUP**, in the academic year **2024/2025**.  

You can find more information about the course at the following link:

<div align="center">
  <a href="https://sigarra.up.pt/fcup/pt/ucurr_geral.ficha_uc_view?pv_ocorrencia_id=529878">
    <img alt="Link to Course" src="https://img.shields.io/badge/Link_to_Course-0077B5?style=for-the-badge&logo=logoColor=white" />
  </a>

  <div style="display: flex; gap: 10px; justify-content: center; margin-top: 10px;">
    <a href="https://sigarra.up.pt/fcup/pt/web_page.inicial">
      <img alt="FCUP" src="https://img.shields.io/badge/FCUP-808080?style=for-the-badge&logo=logoColor=grey" />
    </a>
    <a href="https://sigarra.up.pt/feup/pt/web_page.inicial">
      <img alt="FEUP" src="https://img.shields.io/badge/FEUP-808080?style=for-the-badge&logo=logoColor=grey" />
    </a>
  </div>
</div>
