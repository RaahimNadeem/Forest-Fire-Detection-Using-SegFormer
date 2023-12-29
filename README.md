# Forest Fire Detection Using SegFormer
 <img width="1080" alt="image" src="https://github.com/RaahimNadeem/Forest-Fire-Detection-Using-SegFormer/assets/114340940/0d100eda-c9b0-4d6d-8202-5518f9aca660">

## Introduction
This repository contains a TensorFlow-based implementation of the SegFormer Transformer model tailored for forest fire detection. The model inputs an image mask and a hand-annotated true mask, outputting a predicted mask that highlights areas affected by forest fires.

## Setup and Requirements
To begin, ensure that the necessary libraries are installed. This project requires transformers and evaluate, which can be installed using pip:
```bash
pip install transformers
pip install evaluate
```
# Data Preparation
Data is an essential aspect of this project. The script expects data to be in a specific format and stored in Google Drive. After mounting the Google Drive, the dataset is extracted and organized into appropriate directories for processing:
1. RGB images are moved to /content/dataset/rgb
2. Corresponding mask images are moved to /content/dataset/masks

# Dataset Splitting
The dataset is divided into training, validation, and test sets with the respective ratios of 70%, 20%, and 10%. The script automatically handles this splitting and organizes the data into separate folders for each set.

# Data Processing
The following steps are involved in data processing:
1. Loading and Normalization: Images and masks are loaded, resized to 256x256 pixels, and normalized.
2. Data Pipeline: A tf.data.Dataset pipeline is created for efficient data handling and processing during training.

# Model Training
The model used for this project is the TFSegformerForSemanticSegmentation from Hugging Face's transformers library. The model is fine-tuned for the specific task of segmenting the provided dataset.

#Training Process
Training involves the following steps:
1. Setting up hyperparameters like learning rate and epochs.
2.Defining callbacks for visualization after each epoch.
3. Running the training loop with the specified number of epochs and monitoring the validation loss.

# Evaluation and Visualization
After training, the model's performance is evaluated using F1 score metrics. Predictions are visualized alongside the ground truth for qualitative assessment. The script also includes a custom function to calculate the F1 score.

# Conclusion
This project demonstrates the capability of Transformer-based models in the field of image segmentation, providing a strong foundation for further exploration and development in this area. The high F1 scores achieved reaffirm the model's proficiency in accurately segmenting and identifying areas of interest within images.
```
F1 Score Using PyTorch:  0.9167134761810303
F1 Score Using Custom Function:  0.9167134968150267
```




