# Chandu Venkat Sai Narne

**Medical AI & Trustworthy Machine Learning Researcher**
MSc Computer Science with Project Management, University of Bedfordshire (UK) — expected September 2028

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/chanduvenkatsainarne/)
[![Email](https://img.shields.io/badge/Email-Contact-D14836?logo=gmail&logoColor=white)](mailto:chanduvenkatsainarne@gmail.com)

I build reproducible AI methods for clinical problems: **brain imaging** (MRI and CT) and **ECG-based cardiovascular risk prediction**. I care about honest evaluation (patient-level splits, calibration, subgroup performance), so that models work for new patients, not just on benchmarks.

- 🧠 Finished a **multi-task brain tumour model** (segmentation and tumour type) with a paper-style write-up
- 🩸 Training **brain haemorrhage segmentation on head CT** (2D now; 3D models and VR viewing on a second branch)
- 🫀 Starting a supervised research paper on **hidden atrial fibrillation after stroke** from sinus-rhythm ECG (MIMIC-IV)
- 🎓 Background: B.Tech in Computer Science · Data Science internship

---

## Projects

### 🧠 Brain tumour segmentation and classification on MRI
[brain-tumor-multitask](https://github.com/ChanduVenkatSaiNarne/brain-tumor-multitask) · PyTorch · [paper (PDF)](https://github.com/ChanduVenkatSaiNarne/brain-tumor-multitask/blob/main/docs/brain-tumor-multitask_paper.pdf)

One network outlines the tumour **and** predicts its type (meningioma, glioma, pituitary) from a contrast-enhanced MRI slice.

| Held-out test (35 patients, 454 slices) | v1: U-Net from scratch | **v2: U-Net++ / EfficientNet-B3** |
|---|---|---|
| Tumour outline (Dice) | 0.740 | **0.811** |
| Glioma outline (Dice) | 0.590 | **0.707** |
| Tumour-type accuracy | 93.8% | **95.2%** |
| Macro-F1 | 0.923 | **0.938** |

- Split **by patient** (no slices from the same person in both training and test)
- ImageNet-pretrained encoder, strong augmentation, per-slice Dice loss, flip test-time augmentation
- Runs on a free Google Colab T4

### 🩸 Brain haemorrhage (clot) segmentation on head CT
[Brain-Clot-Edema-midlineshift](https://github.com/ChanduVenkatSaiNarne/Brain-Clot-Edema-midlineshift) · PyTorch · MONAI

Finds bleeding on head CT and measures it: **volume in mL, side, slices affected**. Trained on the public **BHSD** dataset (192 expert-labelled scans), split by scan.

- **`master` (2D):** U-Net++ on EfficientNet-B3 with brain, subdural and bone CT windows as input; runs on a Colab T4. Early results: slice sensitivity 0.87 and bleed volume correlation r = 0.83 after 2 epochs; full training in progress
- **`3d` branch:** SegResNet, SwinUNETR and nnU-Net-style 3D models; bleeds exported as 3D models (`.glb`) and viewed in **VR on a Meta Quest** (WebXR) or 3D Slicer
- Edema and midline shift: code ready, awaiting labelled data

### 🫀 Hidden AF after stroke from sinus-rhythm ECG
Predicting **occult atrial fibrillation** in ischaemic stroke patients from a single normal (sinus-rhythm) 12-lead ECG, using **MIMIC-IV** and **MIMIC-IV-ECG**.

- 1D ResNet on raw waveforms vs P-wave and clinical feature baselines
- **Positive-unlabelled learning**, because "no AF" patients were often never monitored long-term
- Calibration and subgroup results by sex, age and race (TRIPOD+AI)
- Status: 🟡 supervisor confirmed · PhysioNet credentialing submitted · target: *PLOS Digital Health*

### 🧠 Gaussian Splatting for brain MRI
Reconstructing high-resolution brain MRI from fewer slices, and checking whether real anatomy (cortical thickness, hippocampal volume) is preserved, on an **8 GB GPU** (with a teammate).
Status: 🟡 early stage

---

## Research interests
`Medical image segmentation` · `Brain MRI & CT` · `3D medical imaging` · `ECG deep learning` · `Label noise & PU learning` · `Calibration & fairness in clinical AI` · `Foundation models (SAM / MedSAM)`

## Tools
![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?logo=pytorch&logoColor=white)
![MONAI](https://img.shields.io/badge/MONAI-3D%20medical%20AI-00A3E0)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)
![Google Colab](https://img.shields.io/badge/Colab-F9AB00?logo=googlecolab&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?logo=git&logoColor=white)
![3D Slicer](https://img.shields.io/badge/3D%20Slicer-1F65A8)
![three.js](https://img.shields.io/badge/three.js-WebXR-000000?logo=threedotjs&logoColor=white)

Also used: segmentation-models-pytorch (U-Net, U-Net++) · nnU-Net · nibabel · OpenCV

## Currently learning
PhysioNet ECG tooling (wfdb) · Google BigQuery for MIMIC · Weights & Biases · LaTeX/Overleaf

---

*Open to research collaborations in medical AI — feel free to reach out.*
