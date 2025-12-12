[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/vzqInGyc)
[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=21409836)


# Malware Detection from Network Flow Features

## Overview
This project performs malware detection using flow-level statistical features extracted from network traffic.  
The objective is to classify each network flow as malicious or benign without relying on packet payloads,  
making the approach suitable for encrypted or obfuscated traffic.

All code in the notebook runs directly on the preprocessed dataset included in this repository.  
No PCAP parsing or Ubuntu tools are required to grade the project.


## Dataset Information

### Why the raw data is not included
The original .pcapng file is very large and cannot be uploaded to GitHub.  
Feature extraction was also performed on Ubuntu because pcap parsing tools do not work reliably on Windows.

To ensure reproducibility, the fully processed dataset (CSV) is included in this repository as a ZIP file.

## Included Dataset (Required for Running the Notebook)

File included in this repo:
- `traffic_flow_features_binary_custom.zip`

This ZIP contains the file:
- `traffic_flow_features_binary_custom.csv`

The dataset includes 498,446 network flows with the following features:
- Packet count  
- Total bytes  
- Packet size statistics (mean, median, min, max, std)  
- Flow duration  
- Inter-arrival time (IAT) statistics  
- Binary label  
  - 1 = malware  
  - 0 = benign  

These features were engineered using a custom pipeline based on pcapML.


## Raw PCAP Data

The original traffic capture used to generate the dataset is available here:

Google Drive:  
https://drive.google.com/drive/u/2/folders/13fpctT4XJyIqiH8UE7M5VvAAKfllon73



