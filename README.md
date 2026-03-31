# Delivery Risk Prediction

Du an Machine Learning du doan rui ro giao hang tre (late delivery risk) trong chuoi cung ung, ket hop:
- Phase 1: supervised learning de du doan don hang co nguy co giao tre.
- Phase 2: unsupervised learning (clustering) de phan khuc hanh vi van chuyen va ho tro quyet dinh shipping mode.

## Overview

- Bai toan: du doan giao hang tre va tim insight van hanh.
- Dataset: DataCoSupplyChainDataset.csv.
- Quy mo: 180,519 ban ghi, 53 thuoc tinh (theo notebook clustering).
- Thuoc do danh gia: Accuracy, Precision, Recall, F1-score.

## Why This Project

- Giam ti le giao tre bang cach canh bao som don hang rui ro.
- Ho tro doi van hanh lua chon phuong thuc giao hang phu hop hon.
- Ket hop prediction + clustering de vua co hieu qua du doan, vua co insight business.

## Repository Structure

```text
.
├── eda/
│   └── EDA.ipynb
├── preprocessing/
│   └── feature_selection/
│       └── Processing.ipynb
├── model/
│   ├── baseline/
│   │   └── model_phase1.ipynb
│   └── clustering/
│       └── model_phase2.ipynb
├── result/
└── requirements.txt
```

## Workflow

### 1) Exploratory Data Analysis
Notebook: eda/EDA.ipynb

- Kham pha cau truc du lieu va chat luong du lieu.
- Kiem tra missing values.
- Xac dinh cac bien co the anh huong den late delivery.

### 2) Preprocessing + Feature Selection
Notebook: preprocessing/feature_selection/Processing.ipynb

- Lam sach du lieu, ma hoa bien phan loai.
- Chuan hoa du lieu (neu can).
- Chon dac trung bang Chi-square.

### 3) Baseline Modeling (Phase 1)
Notebook: model/baseline/model_phase1.ipynb

- So sanh nhieu mo hinh: Logistic Regression, Decision Tree, Random Forest, Extra Trees, SVM, KNN, MLP, CatBoost.
- Xu ly mat can bang lop (RandomOverSampler, SMOTE, ...).
- Danh gia theo Accuracy, Precision, Recall, F1-score.

### 4) Clustering Analysis (Phase 2)
Notebook: model/clustering/model_phase2.ipynb

- Ap dung KMeans/KMeans++ de phan cum.
- Xac dinh so cum toi uu bang Elbow + KneeLocator.
- Kiem chung bo sung bang Silhouette Score.
- Ket qua trong notebook cho thay k toi uu = 4.

## Dataset

- Ten file: DataCoSupplyChainDataset.csv
- Luu y:
- Dataset hien khong duoc commit trong repo.
- Ban can tu bo sung file CSV va cap nhat duong dan trong notebook.
- Notebook hien co doan dung Google Drive (`drive.mount('/content/drive')`), can chinh lai neu chay local.

## Installation

### Local (Windows PowerShell)

```bash
python -m venv .venv
.venv\Scripts\activate
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### Google Colab

- Upload dataset len Google Drive.
- Cap nhat dung duong dan CSV trong cac notebook.
- Cai them package neu can (`!pip install -r requirements.txt` hoac install theo tung package).

## Quick Start

1. Clone repo.
2. Cai dependency theo requirements.txt.
3. Chay notebook theo thu tu:
- eda/EDA.ipynb
- preprocessing/feature_selection/Processing.ipynb
- model/baseline/model_phase1.ipynb
- model/clustering/model_phase2.ipynb
4. Luu cac bang/plot ket qua vao thu muc result/.

## Main Libraries

- pandas, numpy
- matplotlib, seaborn
- scikit-learn
- imbalanced-learn
- catboost, xgboost
- kneed
- jupyter, notebook

## Current Limitations

- Chua co script train/evaluate dang .py de chay tu dong.
- Chua co CI test cho quality gate.
- Duong dan data trong notebook con phu thuoc moi truong chay (Colab/local).

## Roadmap

- Dong goi pipeline thanh module Python (train.py, predict.py).
- Them requirements-lock va script reproducible.
- Them model explainability (SHAP/LIME).
- Trien khai demo API (FastAPI/Flask).

## Contributing

1. Fork repository.
2. Tao branch moi (`feature/ten-tinh-nang`).
3. Commit thay doi ro rang.
4. Tao pull request.
