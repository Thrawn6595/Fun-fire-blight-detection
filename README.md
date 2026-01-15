# Potato disease detection using deep learning


## Motivation

Most of my work involves building ML models from tabular data, but many interesting problems require working with image data. I want to understand what makes the combination of convolutional architectures and neural networks effective at image classification and apply it to an actual business problem, in this case agricultural disease detection in potato plants.

I have chosen the PlantVillage dataset for this project as it provides pre-labelled images of healthy and diseased plants across various vegetables, making it a good starting point for understanding the full pipeline from raw image ingestion and processing to feature extraction and disease classification.

Beyond just building a working model, I wanted to explore the architectural decisions that matter in production: how pooling layers reduce computational cost whilst preserving spatial features, how data augmentation addresses the challenge of limited training data, and how model architecture choices affect deployment constraints like inference speed and memory footprint.

### Situation

Small-scale farmers often lack the resources for early disease intervention, yet timely detection can mean the difference between a productive season and crop failure. Similarly, amateur backyard gardeners could benefit from accessible tools that help identify plant health issues before they spread. A mobile application that accepts a plant photo and returns a disease classification could democratise access to agricultural expertise.

### Solution

A convolutional neural network trained on the PlantVillage dataset to classify potato leaf images into three categories: healthy, early blight, and late blight. The model architecture balances accuracy with deployment constraints, considering inference speed and memory requirements for potential mobile deployment.

The project explores both training approaches from scratch and leveraging pre-trained models to understand the trade-offs between custom architectures and transfer learning. Success means achieving classification accuracy that would be  useful for farmers whilst maintaining fast enough inference for real-time mobile use.


## Dataset Classes

This project classifies potato leaf images into three categories:

![Disease Comparison](docs/images/disease_comparison.png)

### Disease Types

| Class | Pathogen | Symptoms |
|-------|----------|----------|
| **Healthy** | None | Green, vibrant leaves with no visible disease |
| **Early Blight** | *Alternaria solani* | Brown spots with concentric rings (target pattern) |
| **Late Blight** | *Phytophthora infestans* | Water-soaked lesions, potential white mold on leaf undersides |

## Dataset Overview

- **Total Images**: ~2,112
- **Training Set**: 1,728 images (80%)
- **Validation Set**: 384 images (20%)
- **Image Size**: 256×256 pixels
- **Classes**: 3 (Healthy, Early Blight, Late Blight)
- **Batch Size**: 32
- **Random Seed**: 78 (for reproducibility)

## Project Structure
```
Fun-fire-blight-detection/
├── 00_data/              # Dataset storage (not in version control)
│   ├── raw/              # Original images organized by class
│   └── processed/        # Preprocessed data
├── 01_notebooks/         # Jupyter notebooks for exploration
│   └── 01_data_loading.ipynb
├── 02_outputs/           # Model outputs and predictions
│   ├── models/           # Trained model checkpoints
│   └── predictions/      # Prediction results
├── docs/                 # Documentation and images
│   └── images/           # Visual assets for README
├── src/                  # Source code (Python package)
│   ├── data/             # Data processing modules
│   ├── models/           # Model architectures
│   └── utils/            # Helper functions
├── scripts/              # Executable training/inference scripts
├── requirements.txt      # Python dependencies
└── README.md            # This file
```



## License

MIT License - see [LICENSE](LICENSE) file for details

## Author

**Adama Abanteriba Richards**
- GitHub: [@Thrawn6595](https://github.com/Thrawn6595)
- Project: [Fun-fire-blight-detection](https://github.com/Thrawn6595/Fun-fire-blight-detection)

## Acknowledgments

- Dataset: PlantVillage Dataset
- Inspired by agricultural AI applications for disease detection

---
