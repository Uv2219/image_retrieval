# image_retrieval
🖼️ Optimized AI-Based CBIR for Colour Image Retrieval

📄 Overview
It proposes an AI-optimized Content-Based Image Retrieval (CBIR) system that addresses key limitations of traditional and deep learning approaches, such as:
* Semantic gap problem
* Feature redundancy
* Inefficient feature fusion
The system integrates multi-color space features, deep learning, feature fusion, and efficient indexing  to improve retrieval accuracy and efficiency.

🎯 Key Contributions:-
✔️ Multi-color space representation (RGB, HSV, LAB)
✔️ Deep semantic feature extraction using CNN (MobileNetV2)
✔️ Hybrid feature fusion using attention mechanism
✔️ Feature optimization to reduce redundancy
✔️ Fast similarity search using FAISS

🧠 Proposed Methodology

1. Multi-Color Space Feature Extraction
* RGB → basic color composition
* HSV → perceptual color representation
* LAB → perceptual uniformity
Final color feature:
ColorFeature = HRGB + HHSV + HLAB

2. Deep Feature Extraction
* CNN model: **MobileNetV2**
* Extracts:
  * Object structure
  * Shape
  * Semantic patterns

3. Attention-Based Feature Fusion
Combines low-level and high-level features:
Attention = wc * ColorFeature + wd * DeepFeature
Final fused representation: FusedFeature = [Attention × Color, Attention × Deep]
✔️ Improves both visual + semantic similarity

4. Deep Hashing (Optimization)
* Converts features → binary codes
* Reduces dimensionality
* Improves retrieval speed
Example:
[0.8, -0.2, 1.3, -0.6] → [1, 0, 1, 0]


5. FAISS-Based Similarity Search
* Efficient nearest neighbor search
* Handles large-scale datasets
* Uses:
  * Cosine similarity
  * Inner product


🏗️ System Architecture

OFFLINE PHASE:
Dataset → Preprocessing → Feature Extraction → Fusion → FAISS Index
ONLINE PHASE:
Query Image → Preprocessing → Feature Extraction → Similarity Search → Top-K Results


📊 Dataset & Evaluation

* Dataset: **Caltech-101**
* ~9000 images across 101 categories
* Includes:
  * Airplanes
  * Faces
  * Motorbikes
  * Animals

⚙️ Tech Stack
* Python
* TensorFlow / Keras
* OpenCV
* FAISS
* NumPy, Matplotlib

🚀 Applications
* Image search engines
* Medical image retrieval
* Surveillance systems
* E-commerce product search
* Multimedia databases
