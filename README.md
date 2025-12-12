[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/vzqInGyc)
[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=21409836)


# Malware Detection from Network Flow Features  
Using pcapML + Custom Feature Engineering + Supervised & Unsupervised Learning


## Overview

This project reproduces and extends the **Malware Detection benchmark** from the  
**pcapML / nPrint suite**, using real network traffic captured as `.pcapng` files.

The goal is to detect whether a network flow is **malicious or benign** using only  
**flow-level statistical features** (no payload inspection), making the approach suitable  
for encrypted or obfuscated traffic.

This repository contains:

- Custom feature extraction script for pcapML flows  
- Flow-level dataset (`traffic_flow_features_binary_custom.csv`)  
- Machine learning experiments  
  - **Unsupervised** (OCSVM)  
  - **Supervised** (Logistic Regression, Random Forest, XGBoost, LightGBM)  
- Evaluation metrics (AUC, balanced accuracy, confusion matrices, ROC curves)  
- Full notebook and report


## Dataset
Two items are provided:

### **1. Flow-Level Feature Dataset**
`traffic_flow_features_binary_custom.csv`

This file contains **498,446 network flows**, each represented by:

- Packet count  
- Total bytes  
- Mean, median, min, max packet sizes  
- Packet size standard deviation  
- Flow duration  
- Inter-arrival time statistics  
- **Binary label**  
  - `1` = malware  
  - `0` = benign  

These features were engineered using a custom extraction pipeline based on pcapML.

### **2. Raw Traffic Data**
`traffic.pcapng_malware.zip`

This ZIP contains the original `traffic.pcapng` file used to generate the flow dataset.


## Dataset Source 

The data originates from the **netML Malware Detection benchmark**:
https://nprint.github.io/benchmarks/malware_detection/netml_malware.html

