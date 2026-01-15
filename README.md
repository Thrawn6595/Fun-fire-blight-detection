# Potato disease detection using deep learning


### Motivation

Most of my work involves building ML models from tabular data, but many real-world problems are fundamentally visual. I want to understand how image data changes the modelling approach, particularly what makes convolutional architectures effective where traditional neural networks struggle.

Agricultural disease detection is interesting to me because it combines accessible data with genuine impact. Small-scale farmers often lack the resources for early disease intervention, yet timely detection can mean the difference between a productive season and crop failure. The PlantVillage dataset provides pre-labelled images of healthy and diseased plants across various vegetables, making it a good starting point for understanding the full pipeline from raw images to a deployed classification system as a POC from scratch.

Beyond just building a working model, I wanted to explore the architectural decisions that matter in production: how pooling layers reduce computational cost whilst preserving spatial features, how data augmentation addresses the challenge of limited training data, and how model architecture choices affect deployment constraints like inference speed and memory footprint.

This project again follows the ML development cycle from problem framing through to deployment considerations, treating image classification not just as a technical exercise but as a practical system that needs to work reliably in real agricultural contexts. ML lifecycle [Deign, Model, Deploy]


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

**Adama Abanteriba**
- GitHub: [@Thrawn6595](https://github.com/Thrawn6595)
- Project: [Fun-fire-blight-detection](https://github.com/Thrawn6595/Fun-fire-blight-detection)

## Acknowledgments

- Dataset: PlantVillage Dataset
- Inspired by agricultural AI applications for disease detection

---
