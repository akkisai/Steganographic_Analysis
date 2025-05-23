# Steganographic Analysis

This project provides a comprehensive framework for the creation, encoding, decoding, and analysis of steganographic datasets using Least Significant Bit (LSB) techniques. It includes tools for dataset generation, message encoding/decoding, and deep learning-based steganalysis.

---

## Features

- **Dataset Creation**: Automatically generates cover and stego image datasets with configurable LSB embedding (1-8 bits).
- **Message Encoding**: Supports flexible message embedding in images, including channel selection, bit depth, and custom delimiters.
- **Message Decoding**: Brute-force LSB decoding to recover hidden messages from images.
- **Deep Learning Steganalysis**: Implements YeNet and SRNet architectures for detecting steganography in images.
- **Training & Evaluation**: Scripts for training and evaluating models on generated datasets.

---

## Directory Structure

```
Steganographic_Analysis/
│
├── data_creation.ipynb      # Dataset generation and metadata creation
├── encoding.ipynb           # Flexible message encoding in images
├── decoder.ipynb            # Brute-force LSB message decoding
├── train.ipynb              # Model definitions, training, and evaluation
├── LICENSE
├── README.md
```

---

## Getting Started

### 1. Dataset Creation

Generate datasets with different LSB embedding depths:

```python
# In data_creation.ipynb
create_dataset('dataset_4', bits=4)  # Example for 4-bit LSB
```

### 2. Message Encoding

Embed a message in an image:

```python
# In encoding.ipynb
encode_message_in_image(
    img_path='input.jpg',
    out_path='encoded.png',
    message='Secret Message',
    channels='RGB',
    num_bits=4,
    delimiter_start='#',
    delimiter_end='#'
)
```

### 3. Message Decoding

Brute-force decode messages from an image:

```python
# In decoder.ipynb
results = decode_lsb('encoded.png')
print(results)
```

### 4. Model Training

Train YeNet or SRNet for steganalysis:

```python
# In train.ipynb
train_loader, val_loader, test_loader = get_data_loaders('dataset_4')
ye_net = YeNet().to(device)
train(ye_net, train_loader, val_loader, ...)
```

---

## Requirements

- Python 3.x
- numpy
- pandas
- torch
- torchvision
- pillow
- tqdm
- matplotlib

Install dependencies with:

```sh
pip install numpy pandas torch torchvision pillow tqdm matplotlib
```

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

---
