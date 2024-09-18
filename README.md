<h1 style="font-size: 36px;">Image Caption Generator Using Transformers</h1>

This project demonstrates the use of Transformer models for image captioning, a task that merges computer vision and natural language processing to generate accurate textual descriptions from images. The notebook serves as a detailed guide for building and understanding Transformer models, walking through each step of constructing the model and applying it to image captioning. It provides a practical resource for individuals looking to explore or deepen their knowledge in the intersection of deep learning, vision, and language modeling.

## DATASET

The original dataset used in this project consists of approximately 31,000 images. However, due to upload limitations, only 50 sample images have been included in this repository for demonstration purposes. Despite the smaller subset, the project retains its focus on illustrating the application of Transformer models for image captioning, and the steps can easily be scaled for larger datasets.

## METHODOLOGY

- **Data and Pre-processing:**
The Flickr30k dataset is used in this project. Pre-processing steps include caption normalization, length filtering, and dataset splitting. For image processing, functions like decoding and resizing are implemented. The dataset is further prepared using TensorFlow’s data pipeline functions such as shuffling, mapping, batching, and prefetching for optimal parallelization.

- **Model Architecture:**
The model utilizes a pre-trained EfficientNetB0 CNN for image feature extraction. These features are normalized and passed through dense layers to match the encoder's dimensional requirements. The encoder includes multi-head attention and layer normalization. The decoder takes in the target captions and the encoder’s output, applying positional embeddings, masked multi-head attention, cross-attention, layer normalization, and feed-forward layers. A final dense layer with softmax activation serves as the output layer for generating captions.

- **Training:**
The model is trained using images as inputs for the encoder and their corresponding captions (excluding the <end> token) as inputs for the decoder. Target captions are shifted by one position (excluding the <start> token). The goal is to update model weights and minimize the loss during training.
  
- **Inference:**
For validation, Sparse Categorical Crossentropy loss is applied, while caption generation during inference uses a Greedy algorithm. The BLEU score is utilized to evaluate caption quality on the test set.

## RESULT
  ![image](https://github.com/MeetJhaveri/Image-Caption-Generator/blob/main/Screenshot%202024-09-17%20at%2010.36.10%20PM.png)
  
