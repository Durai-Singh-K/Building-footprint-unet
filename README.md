# 🏢 Building Footprint Extraction Using U-Net Architecture

## 📜 Overview
This project implements **Building Footprint Extraction** from high-resolution satellite imagery using the **U-Net Architecture**, a specialized type of Convolutional Neural Network (CNN). Originally designed for biomedical image segmentation, U-Net’s encoder-decoder structure is well-suited for precise, pixel-level segmentation tasks such as building footprint extraction, making it highly effective for applications in urban planning, disaster management, and Geographic Information Systems (GIS).

## 📂 Dataset

The dataset used in this project is **SpaceNet 8**, curated specifically for building and road segmentation tasks using high-resolution satellite images. The dataset includes imagery from various geographic regions, allowing the model to generalize well across different architectural styles and environments.

### 🗺️ Dataset Description:
- **Resolution**: 0.3 meters per pixel, enabling the detection of individual buildings and road features.
- **Geographic Coverage**: Images from Germany and East Louisiana, capturing a wide range of urban and rural landscapes.
- **Format**: Satellite imagery provided in TIFF format with corresponding annotations in GeoJSON.

## 🛠️ Methodology

### ⚙️ U-Net Architecture
The U-Net architecture consists of two main paths:
- **Encoder (Contracting Path)**: Utilizes convolutional layers followed by max-pooling to capture high-level features and reduce spatial dimensions.
- **Bottleneck**: Serves as the bridge between the encoder and decoder, further abstracting feature representations.
- **Decoder (Expanding Path)**: Restores spatial resolution using up-convolutions and incorporates skip connections from the encoder to ensure precise localization of features.
- **Output Layer**: A final 1x1 convolutional layer maps the feature maps to the binary output, segmenting building footprints.

### 🔄 Data Preprocessing
Data preprocessing steps include:
- **Image Resizing**: All images are resized to 512x512 pixels to maintain consistency.
- **Data Augmentation**: Techniques such as random rotations, flipping, and scaling are applied to improve model generalization.

### 🧠 Model Training
The model is trained in a supervised manner with the following configurations:
- **Loss Function**: Binary Cross-Entropy, ideal for binary segmentation tasks.
- **Optimizer**: Adam Optimizer, chosen for its efficiency in handling sparse gradients.
- **Metrics**: Accuracy, Intersection over Union (IoU), Precision, Recall, and F1-score.
- **Training Data Split**: 
  - 80% of images for training 
  - 10% for validation 
  - Remaining for testing.
- **Epochs**: 10
- **Batch Size**: 2

## 📊 Evaluation Metrics
Model performance is evaluated using:
- **Intersection over Union (IoU)**: Measures the overlap between predicted segmentation and ground truth.
- **Precision**: Ratio of true positive predictions to total positive predictions.
- **Recall**: Measures how many actual positives were captured by the model.
- **F1-score**: The harmonic mean of Precision and Recall.

## 🚀 Results
The U-Net architecture proved highly effective for building footprint extraction:
- **High IoU and accuracy** in segmenting building footprints from satellite imagery.
- Outperforms traditional image processing methods in terms of precision and efficiency.

## 🔮 Future Work
Several improvements and extensions can further enhance this model:
- **Enhanced Data Augmentation**: Applying more advanced techniques such as elastic transformations and color jittering.
- **Multi-Scale Feature Extraction**: Introducing architectures that leverage multi-scale features for detecting buildings of varying sizes.
- **Integration with Additional Data Sources**: Combining satellite imagery with LiDAR or radar data for improved segmentation accuracy.
- **Real-Time Segmentation**: Optimizing the model for real-time applications, such as disaster management, using efficient models like MobileNet or pruning techniques.

## 📝 License
This project is released for academic and non-commercial purposes only.

## 📧 Contact
For any inquiries or contributions, feel free to reach out to the project maintainer at durai_singh@outlook.com.

---

### 🔗 References
- [SpaceNet Dataset](https://spacenet.ai)
- [U-Net Paper](https://arxiv.org/abs/1505.04597)
