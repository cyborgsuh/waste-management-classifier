# Waste Classification with ResNet34

This project focuses on classifying waste images into **10 categories** using a fine-tuned **ResNet34** model. The goal is to provide a baseline deep learning solution for waste classification, which can support recycling, waste management, and sustainability efforts.

---

## 📂 Dataset

- Dataset contains **10 classes**: `battery`, `biological`, `cardboard`, `clothes`, `glass`, `metal`, `paper`, `plastic`, `shoes`, `trash`.
- Available at: [Waste Garbage Management Dataset](https://huggingface.co/datasets/omasteam/waste-garbage-management-dataset)  
- The data is split into **80% training** and **20% validation** using `random_split`.

---

## 🧠 Model & Training

- **Architecture**: ResNet34 pretrained on ImageNet. Final layer modified for 10 classes.
- **Loss function**: CrossEntropy with label smoothing (`label_smoothing=0.1`).
- **Optimizer**: AdamW (`lr=1e-3`, `weight_decay=1e-4`).
- **Augmentations**:
  - Resize to 256×256
  - Random horizontal/vertical flips, rotations, affine transforms
  - Color jitter
  - Normalization using ImageNet statistics
- **Batch size**: 64
- **Epochs**: 30
- **Hardware**: GPU provided by [Lightning.AI](https://lightning.ai)

---

## 📊 Results

- Achieved **~91% accuracy** on validation data with strong precision, recall, and F1-score.
- Confusion matrix and classification report can be generated using the included evaluation code.
- Highly encourage experimentation and performance improvement with:
  - Deeper ResNet variants (ResNet50, ResNet101)
  - Test-time augmentation (TTA)
  - EfficientNet for better accuracy/parameter trade-off
  - Real-time waste classification web app with Flask or Streamlit

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/waste-classification.git](https://github.com/cyborgsuh/waste-management-classifier)
   cd waste-classification
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Prepare dataset:

- Structure your data as:

    ```bash
    omr/
    ├── battery/
    ├── biological/
    ├── cardboard/
    ├── clothes/
    ├── glass/
    ├── metal/
    ├── paper/
    ├── plastic/
    ├── shoes/
    └── trash/
    ```
4. Run the Resnet34 Training File 

---

# 📌 License

This project is licensed under the MIT License.

---

# 🙏 Credits

- Dataset: [Omar Abdullah](https://huggingface.co/omasteam)

- GPU resources: [Lightning.AI](https://lightning.ai/)

