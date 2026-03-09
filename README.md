# ICP Detection from Fundus Images using Deep Learning and Explainable AI

## 📌 About the Project

This project implements a **deep learning framework for detecting papilledema from retinal fundus images**. Papilledema refers to swelling of the optic disc caused by increased intracranial pressure (ICP) and can indicate serious neurological conditions.

The proposed system combines **deep learning classification, explainable artificial intelligence (XAI), and language-based interpretation** to improve both diagnostic accuracy and interpretability.

The framework integrates:

- **EfficientNet-B2 deep learning model** for fundus image classification
- **Grad-CAM and LIME** for explainable AI visualization
- **Falcon-7B-Instruct Large Language Model** for generating medical explanations
- **Gradio interface** for interactive predictions

This repository is associated with a **manuscript submitted to the journal *The Visual Computer***.

---

## 📂 Repository Contents

| File | Description |
|-----|-------------|
| `ICP.ipynb` | Main Google Colab notebook implementing the full pipeline |

The notebook contains the complete workflow including:

- Dataset preprocessing
- Model training
- Model evaluation
- Explainable AI visualization
- LLM-based explanation
- Interactive prediction interface

---

## 🔗 Interactive Notebook

Run the notebook directly in **Google Colab**:

https://colab.research.google.com/drive/14fqjZI18ReBJ7swYyw8aYAJ_WTrn5sgn

---

## 📊 Dataset

The dataset consists of **retinal fundus images** categorized into three classes.

| Class | Description |
|------|-------------|
| Normal | Healthy optic disc |
| Papilledema | Optic disc swelling due to raised intracranial pressure |
| Pseudopapilledema | Optic disc anomaly resembling papilledema |

**Dataset Source**

https://github.com/openmedlab/Awesome-Medical-Dataset

---

## ⚙️ Methodology

The proposed framework consists of several stages.

### 1️⃣ Data Preprocessing
- Resize images to **224 × 224 pixels**
- Apply **data augmentation** such as horizontal flipping and rotation
- Split dataset into **Training (70%), Validation (15%), and Test (15%)**

---

### 2️⃣ Deep Learning Model

The classification model is based on **EfficientNet-B2**, a convolutional neural network pretrained on ImageNet.

Modifications include:

- Replacing the final classification layer
- Adding **three output neurons** corresponding to the three classes

Training configuration:

- Optimizer: **Adam**
- Learning rate: **0.0001**
- Epochs: **10**
- Loss function: **Weighted CrossEntropy Loss**

---

### 3️⃣ Model Evaluation

The model performance is evaluated using:

- **Accuracy**
- **Precision**
- **Recall**
- **F1-score**
- **Confusion Matrix**

---

### 4️⃣ Explainable AI (XAI)

Two explainability techniques are used to interpret model predictions.

**Grad-CAM**

- Generates heatmaps highlighting important regions influencing predictions.

**LIME**

- Identifies important superpixel regions contributing to the classification decision.

---

### 5️⃣ LLM-based Explanation

A **4-bit quantized Falcon-7B-Instruct large language model** is used to generate **human-readable medical explanations** based on:

- Model prediction
- Confidence score
- Grad-CAM visualization
- LIME explanation

---

### 6️⃣ Interactive Interface

The system includes a **Gradio interface** that allows users to:

- Upload fundus images
- View prediction results
- See Grad-CAM heatmaps
- View LIME explanations
- Read generated medical interpretations

---

## 🧠 Algorithm

**Step 1:** Extract and organize the retinal fundus image dataset into three classes: Normal, Papilledema, and Pseudopapilledema.

**Step 2:** Split the dataset into **Training (70%)**, **Validation (15%)**, and **Testing (15%)** sets.

**Step 3:** Resize images to **224 × 224 pixels** and apply **data augmentation**.

**Step 4:** Load the pretrained **EfficientNet-B2** model and replace the final layer with a **3-class output layer**.

**Step 5:** Compute **class weights** and use **weighted CrossEntropy loss** to address class imbalance.

**Step 6:** Train the model using the **Adam optimizer** with learning rate **0.0001** for **10 epochs**.

**Step 7:** Validate the model after each epoch and record training metrics.

**Step 8:** Evaluate the trained model on the test dataset using accuracy, precision, recall, F1-score, and confusion matrix.

**Step 9:** Apply **Grad-CAM** to visualize attention regions in fundus images.

**Step 10:** Apply **LIME** to identify important superpixel regions influencing predictions.

**Step 11:** Load **Falcon-7B-Instruct LLM** for explanation generation.

**Step 12:** Generate medical explanations using prediction results and XAI outputs.

**Step 13:** Deploy the system using a **Gradio interface** for real-time prediction and explanation.

---

## 💻 Requirements

The project uses the following libraries:
torch
torchvision
numpy
opencv-python
matplotlib
scikit-learn
pytorch-grad-cam
lime
transformers
bitsandbytes
accelerate
gradio



---

## ▶️ How to Run

1. Open the notebook in **Google Colab**
2. Upload or mount the dataset
3. Run the notebook cells sequentially
4. Train the model
5. Generate Grad-CAM and LIME explanations
6. Launch the **Gradio interface**

---

## 🔬 Reproducibility

This repository provides the **complete experimental pipeline** required to reproduce the results reported in the manuscript, including:

- dataset preprocessing
- model training
- evaluation
- explainable AI visualization
- language-based explanation generation

Researchers can run the notebook to replicate the experiments.

---

## 📖 Citation

This repository is directly related to the manuscript submitted to **The Visual Computer**.

If you use this code or build upon this work, please cite the corresponding paper.
