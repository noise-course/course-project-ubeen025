# Project Title
**netML Malware Detection**

---

## Project Participants
| Name | cnet ID |
|------|----------|
| Youbeen Oh | youbeen2 |

---

## Project Description
This project aims to reproduce and extend the **Malware Detection** benchmark from the **pcapML/nPrint** suite. The goal is to identify **malicious (malware)** and **benign traffic flows** within the dataset using packet-level and flow-level network data.  

This is an important real-world problem because modern malware often hides its activity within encrypted or obfuscated traffic, making it necessary to detect attacks using **metadata and flow features** rather than inspecting payloads directly. Accurate malware detection from network data is critical for preventing data breaches and improving enterprise or ISP-level defenses.

This project aligns closely with the course theme by applying **machine learning to network security**, showing how models can learn from traffic patterns instead of raw content. Related work includes studies leveraging flow-based features such as **Time-To-Live (TTL)** and **packet timing statistics** for intrusion detection, though these often rely too heavily on limited attributes.  

The main goal is to **reproduce the published benchmark** and **extend it by introducing new feature metrics** tailored for malware detection. Ultimately, the project aims to create a **generalizable, open-source model** that can be easily reused and deployed, hosted on GitHub with documentation for other researchers.

---

## Data
The project will use the **netML Malware Detection dataset** provided by the pcapML benchmark collection.  
- Contains labeled raw traffic data (`.pcap` format) representing both **malware-infected** and **benign** network flows.  
- Includes **IPv4 TCP and UDP** flows.  
- Offers **binary (malware vs. benign)** and **multi-class (19 malware types)** versions.  
- Dataset size: **<10 GB (uncompressed)**.  
Additional features may be derived from packet-level data (e.g., byte distributions, inter-arrival times, flow durations, entropy measures).

---

## Machine Learning Approach
Before applying supervised learning, I will explore **unsupervised learning** (e.g., K-means clustering) to understand the data’s underlying patterns and class separability.

1. **Feature Engineering**
   - Apply **network domain knowledge** to construct flow-level features instead of using raw packet data directly.  
   - Incorporate existing feature ideas (packet size histograms, timing, TTL) and propose **new malware-specific metrics** to balance efficiency and accuracy.
   - Incorporate feature importance based on tree based models.

2. **Model Development**
   - Train a range of models from **simple (Logistic Regression, Random Forest, XGBoost)** to **complex deep models (CNN, LSTM)**.  
   - Compare the trade-off between **accuracy and computational efficiency**, identifying an optimal model for real-world deployment.

---

## Evaluation
Model performance will be evaluated primarily using **Balanced Accuracy**, as defined by the benchmark, to handle class imbalance.  
Additional metrics include **Precision**, **Recall**, and **F1-score**, visualized via **confusion matrices**, **ROC curves**, and **precision–recall plots**.  
Because false negatives (undetected malware) are especially costly, I will focus on **Recall** and **F-beta scores** to emphasize detection sensitivity.  
**Cross-validation** will ensure robustness and generalizability across multiple splits.

---

## Deliverables
- **Jupyter Notebook:** Clean, reproducible notebook with data preprocessing, feature extraction, model training, and evaluation.  
- **Feature Engineering Module:** Added malware-specific flow features extending the pcapML baseline.  
- **Trained Models:** Baseline reproductions and improved models with tuned hyperparameters.  
- **Project Report (Sphinx):** Detailed write-up describing approach, experiments, and results.  
- **GitHub Repository:** Public repo with full code, setup guide, and usage instructions.

---
