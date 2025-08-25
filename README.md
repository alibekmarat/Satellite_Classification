🛰️ Satellite Image Classification with Machine Learning and Deep Learning

This project focuses on building and comparing machine learning and deep learning models to classify satellite images into land cover types (cloudy, desert, green area, and water). Using high-resolution satellite images from the RSI-CB256 dataset on Kaggle, the models aim to support environmental monitoring through automation and high accuracy.

📁 Project Overview

- Goal: Automate land cover classification from satellite imagery
- Dataset: RSI-CB256 (5631 images)
- Classes: Cloudy, Desert, Green Area, Water
- Tools: Classical ML (SVM, Random Forest, AdaBoost, Decision Tree) and Deep Learning (CNN with MobileNet)
- Results: SVM and MobileNet provided the best results across different metrics

🧠 Techniques Used

**Classical Machine Learning**
- Feature Extraction: Histogram of Oriented Gradients (HOG)
- Models: 
  - Support Vector Machine (SVM)
  - Random Forest
  - Decision Tree
  - AdaBoost (with DecisionTreeClassifier as base)
- Evaluation Metrics:
  - Accuracy, Precision, Recall, F1 Score
  - Confusion Matrix

**Deep Learning**
- Model: MobileNet (pretrained on ImageNet)
- Training:
  - Optimizer: Adam
  - Loss: Categorical Crossentropy
  - Epochs: 5
  - Callbacks: ModelCheckpoint, TensorBoard
- Results:
  - Test Accuracy: 87.34%
  - Training/Validation Accuracy: >99% by epoch 5
  - Consistent low loss and minimal overfitting

📊 Key Results

| Model         | Test Accuracy | Precision | Recall | F1 Score |
|---------------|---------------|-----------|--------|----------|
| SVM           | **99.5%**     | 98.9%     | 98.9%  | 98.9%    |
| Random Forest | 91%           | 91.2%     | 90.5%  | 90.5%    |
| Decision Tree | 74%           | ~76%      | ~76%   | ~76%     |
| AdaBoost      | 84%           | ~83.6%    | ~83.6% | ~83.6%   |
| MobileNet (DL)| 87.34%        | Good across all classes (per confusion matrix) |

📦 Dataset and Preprocessing

- Dataset: RSI-CB256 from Kaggle
- Balanced dataset across classes
- Split: 70% Train / 15% Validation / 15% Test
- Deep Learning: Data was already high-quality — no augmentation needed
- Classical ML: Raw pixel values and HOG used for feature extraction

🛠️ Technologies Used

- Python
- Scikit-learn
- TensorFlow / Keras
- Google Colab
- Pandas, NumPy, Matplotlib
- Kaggle API
- TensorBoard

🚀 How to Run

1. Download the RSI-CB256 dataset from Kaggle
2. Place images into class-specific folders (`cloudy/`, `water/`, etc.)
3. Run the Jupyter notebook:
   - For ML: Extract features, train models, evaluate
   - For DL: Load MobileNet, train on data, evaluate using callbacks

📈 Visual Monitoring

- TensorBoard used to monitor accuracy and loss during CNN training
- Results showed stable training, no overfitting, and fast convergence

🧠 Insights and Conclusion

- SVM performed the best across all metrics
- MobileNet was a strong deep learning alternative, reaching over 87% test accuracy
- Random Forest also showed solid performance and interpretability
- Decision Tree and AdaBoost were useful baselines but less robust
- The combined approach of ML + DL offers both flexibility and performance

📌 Future Work

- Improve deep learning results via data augmentation
- Explore larger architectures (e.g., ResNet, EfficientNet)
- Deploy a web interface (e.g., Streamlit or Gradio) for real-time classification
- Integrate temporal change detection (e.g., time-series classification)

🤝 Contributors

- **Alibek Marat** — Code development, Colab integration  
- **Yuliya Martsinkus** — Documentation and reporting  
- University of Bologna, Digital Transformation Management Program
