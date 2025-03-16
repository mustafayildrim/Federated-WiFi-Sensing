# **Enhancing Data Privacy and Model Performance with Federated Learning in WiFi Sensing Applications**

## **Overview**
This project explores the use of **Federated Learning (FL)** in **WiFi Sensing Applications** to enhance data privacy and model performance. Instead of centralizing data, FL enables clients to collaboratively train a model while keeping their data localized. In this work, **Federated WiFi Sensing** is implemented using **ResNet-18** and compared to a traditional **CNN model** on the **UT-HAR dataset**.

## **Key Features**
- Implements **Federated Learning** for WiFi-based human activity recognition.
- Uses **ResNet-18** and a **Baseline CNN** to compare performance.
- Utilizes **UT-HAR dataset** for training and evaluation.
- Demonstrates FL’s advantage in **privacy-sensitive environments** like smart homes and healthcare.

---

## **Dataset**
The **UT-HAR dataset** is used for human activity recognition based on **WiFi Channel State Information (CSI)**.

### **Dataset Information**
- **Source**: University of Toronto
- **Size**: ~17GB
- **Data Format**: CSI measurements from 3 antennas & 30 subcarriers
- **Collected Activities**:
  - Lying down
  - Falling
  - Walking
  - Running
  - Sitting down
  - Standing up
- **Data Collection Setup**:
  - Commercial WiFi router (transmitter)
  - Laptop with Intel 5300 NIC (receiver)
  - Environment: Indoor office

---

## **Federated Learning Architecture**

### **How Federated Learning Works in WiFi Sensing**
1. **Data Stays on Clients** – Each client trains a model on its own local dataset.
2. **Global Model Initialization** – A central server initializes the model.
3. **Local Training on Clients** – Clients train the model for several epochs.
4. **Model Aggregation** – Clients send updated model weights to the server.
5. **Global Model Update** – The server aggregates updates and refines the model.
6. **Iterative Process** – Steps repeat until convergence.
7. **Final Model Evaluation** – Global model is tested on unseen data.

---

## **Model Implementation**
We compare **ResNet-18** and a **Baseline CNN** in a federated setting.

### **Baseline CNN**
A simple convolutional neural network (CNN) trained for activity recognition.

### **ResNet-18**
- **18-layer deep residual network**
- Uses **skip connections** to prevent vanishing gradients
- More efficient and accurate compared to standard CNNs

#### **Federated Learning with ResNet-18**
- Distributed across multiple clients.
- Aggregated using **FedAvg** algorithm.

---

## **Training Process**
### **Standard Centralized Training**
In this method, the model is trained on a single centralized dataset. The model updates are performed after each batch, with gradients computed using backpropagation. Optimization is done through an optimizer such as Adam or SGD to minimize loss.

### **Federated Training**
Federated learning distributes the training process across multiple client devices. Each client trains the model using its local data for multiple local epochs. Instead of sharing raw data, clients send their model weight updates to a central server, which aggregates them using techniques like FedAvg to create a new global model.

---

## **Results**
- **FL with ResNet-18 outperformed traditional CNNs**.
- **Higher accuracy with minimal training rounds**.
- **Federated Learning was more stable with privacy enhancements**.
- **Impact of Learning Rates**:
  - Higher rates improved initial learning speed.
  - Lower rates led to more stable accuracy.
- **Comparison with Centralized Training**:
  - FL model maintained or improved accuracy without direct data sharing.

---

## **References**
1. **WiFi Sensing Research** – [IEEE Communications Magazine, Vol. 55, No. 10](https://doi.org/10.1109/MCOM.2017.1700082)
2. **Federated Learning Security & Privacy** – [Future Generation Computer Systems, 2021](https://doi.org/10.1016/j.future.2020.10.007)
3. **WiFi Sensing with FL** – [IEEE IoT Journal, 2022](https://doi.org/10.1109/JIOT.2021.3137793)

